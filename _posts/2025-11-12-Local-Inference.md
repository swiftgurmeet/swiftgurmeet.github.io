---
layout: post
tags: update
title: "Jupyter AI with local Inference using Ollama"
summary: "Setup Ollama on debian and use it with Jupyter AI or other chat"
pagination: 
  enabled: true
---

## Building AI Chatbot with Local Inference using Ollama on a debian machine

More details here on ollama installation: [Ollama on Linux](https://docs.ollama.com/linux)


Create an installation directory, for example, `~/local`

￼
```
mkdir -p ~/local
```

To install Ollama locally on Debian as a non-root user for a csh shell, follow these steps

￼
```
curl -fsSL https://ollama.com/download/ollama-linux-amd64.tgz | sudo tar zx -C ~/local
```

Add the ollama executable to your PATH


￼
````
echo 'set path = (~/local/bin $path)' >> ~/.cshrc
````

Source the cshrc file

￼
```
source ~/.cshrc
```

Set up the Ollama server to run in the background as a service


Create this file with the requisite needed directories:



    `~/.config/systemd/user/ollama.service`

And add this text into it (replace /home/user with home directory):


```
[Unit]
Description=Ollama LLM Server
After=network.target

[Service]
ExecStart=/home/user/local/bin/ollama serve
Restart=always
RestartSec=3

[Install]
WantedBy=default.target
```

Start the service with:

```
systemctl --user start ollama.service
```

Enable the service to start at boot up:

```
systemctl --user enable ollama.service
```

Check the status of the service:

```
systemctl --user status ollama.service
```

Check the Ollama version to confirm it's running:
￼
```
ollama -v
```

You can now download and enable use of a model:
￼
```
ollama pull llama3

ollama pull deepseek-coder

ollama pull deepseek-coder:6.7b

ollama pull qwen2
```

The models are downloaded in this directory:

```
~/.ollama
```

List currently available/downloaded models:


```
ollama list
```

Print ollama activity:

```
ollama ps
```

Create a virtual environment for python:

```
python3 -m venv jaienv
```

(Replace jaienv with your desired environment name).  

Activate the virtual environment (in csh):

```
source jaienv/bin/activate.csh
```

Once activated, your shell prompt should change to indicate the active environment (e.g., (jaienv)).
Install JupyterLab and Jupyter AI:

```
pip install jupyterlab~=4.0
pip install "jupyter-ai[all]"
```

Register the environment as a Jupyter kernel:
This step makes your new virtual environment and its installed packages available as a selectable kernel within the Jupyter notebook interface.

```
python3 -m ipykernel install --user --name=jaienv --display-name "Jupyter AI Environment"
```

Start JupyterLab:

```
jupyter lab
```

Alternately, use your own chat script:

```
import requests
import json
import os
import sys
import uuid

# Configuration
OLLAMA_API_URL = "http://localhost:11434/api/chat"
# The MODEL_NAME is now set via command line argument or defaults
MODEL_NAME = "deepseek-coder:1.3b" 

# System message to define the model's behavior
SYSTEM_PROMPT = "You are a helpful assistant running on a local machine."

# List to maintain conversation history
history = []

def chat_with_ollama(user_input):
    """Sends the current conversation history to Ollama and gets a response."""
    global history, MODEL_NAME

    # Add the user's message to the history
    history.append({"role": "user", "content": user_input})

    data = {
        "model": MODEL_NAME, # This uses the dynamically set model name
        "messages": history,
        "stream": False,
        "timeout": 360000
    }

    try:
        response = requests.post(OLLAMA_API_URL, json=data, timeout=600)
        response.raise_for_status() 
        
        result = response.json()
        message = result['message']
        
        # Add the assistant's message to the history
        history.append(message)
        
        return message['content']

    except requests.exceptions.RequestException as e:
        print(f"\nError communicating with Ollama: {e}")
        print(f"Please ensure Ollama is installed, running, and the model '{MODEL_NAME}' is pulled.")
        sys.exit(1)

def save_output_to_file(content):
    """Saves the last assistant response to a text file."""

    uid = uuid.uuid4().hex
    filename = f"chat_output_{uid}.txt"
    print("filename="+filename)
    try:
        with open(filename, "a") as f:
            f.write("-" * 40 + "\n")
            f.write(f"Model Used: {MODEL_NAME}\n")
            f.write(f"User Prompt: {history[-2]['content']}\n")
            f.write(f"Assistant Response:\n{content}\n")
            f.write("-" * 40 + "\n\n")
        print(f"[System] Successfully saved the last response to '{filename}'.")
    except IOError as e:
        print(f"[System] Error saving file: {e}")

def main():
    """Main loop for the chat interface."""
    global MODEL_NAME, history

    # Check for command line argument for model name
    if len(sys.argv) > 1:
        MODEL_NAME = sys.argv[1]
    
    # Initialize history with system prompt after model name is set
    history.append({"role": "system", "content": SYSTEM_PROMPT})

    print(f"--- Simple Ollama Chat Interface (Model: {MODEL_NAME}) ---")
    print("Type 'exit' or 'quit' to end the chat.")
    print("Type 'save' to save the last assistant response to a file.")
    print("------------------------------------------------------------------")

    while True:
        try:
            user_input = input("\nYou: ")
            
            if user_input.strip().lower() in ['exit', 'quit']:
                print("\nGoodbye!")
                break
            
            if user_input.strip().lower() == 'save':
                if len(history) >= 2:
                    save_output_to_file(history[-1]['content'])
                else:
                    print("[System] No response to save yet. Start chatting first.")
                continue

            if not user_input.strip():
                continue

            print(f"Ollama ({MODEL_NAME}): ", end='', flush=True)
            response_text = chat_with_ollama(user_input)
            print(response_text)
            
        except (KeyboardInterrupt, EOFError):
            print("\nExiting chat.")
            break

if __name__ == "__main__":
    main()
```
