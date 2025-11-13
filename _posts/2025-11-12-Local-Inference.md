---
layout: post
tags: update
title: "Local Inference using Ollama"
date: 2025-11-12 11:30:00 +0000
summary: "Setup Ollama on debian and use it with a chatbot"
pagination: 
  enabled: true
---

   
   
 
### Building AI Chatbot with Local Inference using Ollama on a debian machine

More details here: https://docs.ollama.com/linux

Choose a directory within your user's home directory, for example, ~/local and create a new directory for it.  
￼
    ```mkdir -p ~/local```

To install Ollama locally on Debian as a non-root user for a tcsh shell, follow these steps: 
￼
    ```curl -fsSL https://ollama.com/download/ollama-linux-amd64.tgz | sudo tar zx -C ~/local```

Add the ollama executable to your PATH.  
￼
    ```echo 'set path = (~/local/bin $path)' >> ~/.tcshrc```

Source the tcshrc file.  
￼
    ```source ~/.tcshrc```

Set up the Ollama server to run in the background as a service  

Create this file with requisite needed directories:  

```~/.config/systemd/user/ollama.service```

And add this text into it (replace /home/user with home directory:  

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

    `systemctl --user start ollama.service`

Enable the service to start at boot up:

    `systemctl --user enable ollama.service`

Check the status of the service:

    `systemctl --user status ollama.service`


Check the Ollama version to confirm it's running:
￼
    `ollama -v`

You can now download and enable use of a model, for example, llama3:
￼
    `ollama pull llama3`
    `ollama pull deepseek-coder`
    `ollama pull deepseek-coder:6.7b`
    `ollama pull qwen2`

List currently available/downloaded models:

    `ollama list`

Print ollama activity:

    `ollama ps`

