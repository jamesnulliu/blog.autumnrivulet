---
title: "VSCode: Debug Python"
date: 2024-10-09T10:40:00+08:00
lastmod: 2024-10-09T12:41:00+08:00
draft: false
author: ["jamesnulliu"]
keywords: 
    - debugging
    - python
    - vscode
categories:
    - programming
tags:
    - vscode
    - python
    - debugging
description: How to configure launch.json in VSCode for debugging Python
summary: This post shows how to configure launch.json in VSCode for debugging Python.
comments: true
images: 
cover:
    image: ""
    caption: ""
    alt: ""
    relative: true
    hidden: true
---


First, add the following code to "./.vscode/launch.json" (create the file if it does not exist):

```json
{
    "version": "0.2.0",
    "configurations": [
        // Other configurations...,
        {
            "name": "Python Debugger: Current File",
            "type": "debugpy",
            "request": "launch",
            // Path to the Python file to debug;
            // If set to "${file}", the debugger will run the currently open 
            // file
            "program": "${file}",
            "console": "integratedTerminal",
            // Environment variables
            "env": {
                "YOUR_ENV_VAR": "VALUE"
            },
            // Arguments to pass to the program
            "args": [
                "arg1",
                "arg2",
                // ...
            ]
        },
        // Other configurations...,
    ]
}
```

Next, click on the "Run and Debug" icon on the left sidebar, choose the configuration with the name you specified in "launch.json", then click on the green play button to start debugging.