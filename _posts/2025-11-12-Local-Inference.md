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
