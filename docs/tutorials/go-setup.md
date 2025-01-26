# Setting up a dev container for Go

* Primary author: Lucille Moore (https://github.com/lmoore36)

* Reviewer: [Falisha Khokhar] (https://github.com/falishakhokhar)

## Go Tutorial
This tutorial will cover how to set up a Go Development Container and create a GitHub repository. We will demonstrate these tasks with a simple "Hello World!" program example.

The tutorial will follow three main sections:

1. Initializing a local and remote git repository.
2. Setting up a development container for Go.
3. Writing a simple hello world program.

## Prerequisites

- [Visual Studio Code](https://code.visualstudio.com/)
- [Docker](https://www.docker.com/)
- [Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
- [GitHub Account](https://github.com/)

## Part 1: Creating a Local Directory and Initializing Git

1. Open your terminal or command prompt.
2. Create a new directory for your project:
'''
mkdir go-tutorial
cd go-tutorial
'''

### 2. Initialize Git
git init

## Part 2: Setting Up the Development Environment

### Step 1: Add Development Container Configuration

1. Open the go-tutorial directory in VS Code (File > Open Folder).
2. Install the Dev Containers extension in VS Code.
3. Create a .devcontainer directory and add the devcontainer.json file:

```
mkdir .devcontainer
touch .devcontainer/devcontainer.json
```
4. Add the following content to devcontainer.json:
```
{
  "name": "Go Dev Environment",
  "image": "mcr.microsoft.com/devcontainers/go:0-1.20",
  "customizations": {
    "vscode": {
      "extensions": ["golang.go"]
    }
  }
}
```

Explanation:

- name: Descriptive name for your dev container.
- image: Specifies the Go development environment Docker image.
- customizations: Installs the Go VS Code extension for your container.
- postCreateCommand: Confirms Go is properly installed in the container.

### Step 2: Reopen the Project in a Dev Container
Press Ctrl+Shift+P (or Cmd+Shift+P on Mac), type "Dev Containers: Reopen in Container," and select the option.
Wait for the container to set up (this may take a few minutes).

## Part 3: Getting Started with Go
### Step 1: Instal the Go language.

Follow the steps from the Go website to download and install Go. 

[Installation Instructions](https://go.dev/doc/install)

Check ``` go version``` to verify instalation.

### Step 2: Initialize a Go Mod File
```
go mod init hello-world
```
### Step 3: Create a hello.go file and paste the following code into it.
```
package main

import "fmt"

func main() {
    fmt.Println("Hello, World!")
}
```

This is your Go code. In this code, you:

- Declare a main package (a package is a way to group functions, and it's made up of all the files in the same directory).
- Import the popular fmt package, which contains functions for formatting text, including printing to the console. This package is one of the standard library packages you got when you installed Go.
- Implement a main function to print a message to the console. A main function executes by default when you run the main package.
 
### Step 4: Run your code in the command line.

```
$ go run .
Hello, World!
```

## Congratulations!
### You've now run your first program in the Go language, complete with a git repository and development container.