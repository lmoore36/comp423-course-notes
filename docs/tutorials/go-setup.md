# Setting up a dev container for Go

* Primary author: [Lucille Moore](https://github.com/lmoore36)

* Reviewer: [Falisha Khokhar](https://github.com/falishakhokhar)

## Go Tutorial
This tutorial will cover how to set up a Go Development Container and create a GitHub repository. We will demonstrate these tasks with a simple "Hello World!" program example.

The tutorial will follow three main sections:

1. Initializing a local git repository.
2. Setting up a development container for Go.
3. Writing a simple hello world program.

>Parts One and Two of this tutorial are adapted from Kris Jordan's [Starting a Static Website Project with MkDocs](https://comp423-25s.github.io/resources/MkDocs/tutorial/) tutorial, with modifications to support Go development.

## Prerequisites

Download the following necessary tools for this project!
- [Visual Studio Code](https://code.visualstudio.com/)
- [Docker](https://www.docker.com/)
- [Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)

## Part 1: Creating a Local Directory and Initializing Git

1. Open VS Code, and open the terminal. Make sure you're at the root of wherever you want the project to be housed.
2. Create a new directory for your project using the terminal command ```mkdir go-tutorial ``` then enter the new directory with ``` cd go-tutorial ```.
3. Once you're inside the project directory, initialize an empty git repository with ```git init```. This will create a place to store version control data on your local machine.
4. Create a README file to start your project documentation. ``` echo "# Go Starter Project" > README.md  ```
5. Add your changes to the git repo and commit them with an inital commit message.
```
git add README.md
git commit -m "Initial commit with README"
```
#### You've now set up the directory and version control for your project!

## Part 2: Setting Up the Development Environment

### Step 1: Add Development Container Configuration

1. Open the **go-tutorial** directory that you just created in VS Code. Either via File > Open Folder or ```cd path-to-directory``` in the terminal. Ensure your terminal is in the correct directory before proceeding.
2. Install the Dev Containers extension in VS Code. You can do this via the extensions widget in the left hand tool bar.
3. Inside your go-tutorial directory, create a folder titled **.devcontainer** and create a file titled **devcontainer.json** inside that folder.
4. Add the following content to devcontainer.json:
```
{
  "name": "Go Dev Environment",
  "image": "mcr.microsoft.com/devcontainers/go:latest",
  "customizations": {
    "vscode": {
      "extensions": ["golang.go"]
    }
  }
}
```

Explanations:

- `name`: Descriptive name for your dev container.
- `image`: Specifies the Go development environment Docker image.
- `customizations`: Installs the Go VS Code extension for your container.


### Step 2: Reopen the Project in a Dev Container
Press `Ctrl+Shift+P` (or `Cmd+Shift+P` on Mac), type "Dev Containers: Reopen in Container," and select the option.
Wait for the container to set up (this may take a few minutes).

> **WARNING:** Make sure Docker is running before reopening the project in a dev container. Without Docker running, the container won't initialize.

## Part 3: Getting Started with Go

>Before creating your first Go program, check to see that your installation was successful with the ```go version``` command.

### Step 1: Initialize a Go Mod File
```
go mod init hello-comp423
```
### Step 2: Create a new **hello.go** file and paste the following code into it.

```
package main

import "fmt"

func main() {
    fmt.Println("Hello COMP423")
}
```

This is your Go code. In this code, you:

- *Declare a main package* (a way to group functions, made up of all files in the main directory).
- *Import the fmt package*, this contains functions for formatting text. It's one of the standard library packages that comes with installing Go.
- *Implement a main function* to print "Hello, World!" to the console. The main function executes by default when you run the main package.

### Step 3: Run your code in the command line.

There are two options to run your code now that the program is written. First, you can use the ```go run``` command. This command compiles and runs the program in a single step.
```
$ go run .
```

The second option is to use ```go build```. This command compiles the Go program into binary, creating an executable file that can run independently. With that file, you can use the ```./hello``` command to run the executable.

```
$ go build -o hello
$ ./hello
```

## Congratulations!
### You've now run your first program in the Go language, complete with a git repository and development container.