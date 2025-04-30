# Minishell

## Overview

`Minishell` is a simplified Unix `shell` written in `C`, developed as part of the 42 School common core curriculum. It aims to replicate the behavior of the `Bash shell` by implementing core features such as command execution, redirections, pipelines, and environment variable expansion.  

This project served as an in-depth exploration of low-level `system programming`, `process management`, and `parsing` logic. While the submitted version was evaluated at 100% completion, a few edge cases remain to be refined for full Bash parity.  

--- 

## Features

🔄 Command Execution: Supports built-in and external commands   
📤 Redirections: Handles `>`, `>>`, `<`, and `<<` (heredoc)   
🔗 Pipes: Allows pipelining commands with `|` 
🌍 Environment Variables: Includes variable expansion with `$VAR`   
📁 Path Resolution: Locates executables using `PATH`   
📑 Quote Handling: Manages single and double quotes correctly   
❌ Error Handling: Basic handling of invalid commands and syntax errors   
📜 Signal Handling: Custom signal handling for `CTRL+C`, `CTRL+D`, etc.   
🔧 Built-ins Implemented:   
•	`cd`  
•	`echo`  
•	`pwd`  
•	`env`  
•	`export`   
•	`unset`   
•	`exit`   

#### Known Issues (To be fixed)

✅ ./ls executes ls, while Bash returns an error if ls is not in the current directory.   
❌ echo "$?" does not expand the exit status inside double quotes as expected.   
🔒 echo something > file_with_no_access_rights does not return a “permission denied” error properly.   

These issues are minor and do not affect the core functionality of the shell but are important for full Bash compatibility.  

--- 

## Tech Stack

| Category | Technologies |
|----------|--------------|
| Language | C (POSIX-compliant) |
| Build Tool | Makefile |
| OS | Linux / Unix |
| Libraries | readline, stdlib.h, unistd.h, fcntl.h, signal.h, etc. |
| Signal Handling | SIGINT, SIGQUIT, etc. |
| Process Management | fork(), execve(), waitpid() |
| Parsing | Lexical analysis, syntax tree construction |
| Error Handling | errno, perror() |
| Debugging | gdb, valgrind |
| Testing | Unit tests, integration tests |

--- 

## File Structure

```plaintext
Minishell/
│
├── src/                    # Core shell logic and command execution
├── includes/               # Header files for all modules
├── builtins/               # Built-in command implementations
├── parser/                 # Input parsing and tokenization
├── utils/                  # Helper functions
├── Makefile                # Project build instructions
└── README.md               # Project documentation
```

---

## Lessons Learned

This project significantly improved our understanding of:   

•	Process creation and management using fork, execve, waitpid   
•	File descriptors, pipes, and redirections in Unix systems   
•	Lexical analysis, token parsing, and command syntax   
•	Memory management and error handling in C   
•	Writing modular, maintainable, and testable code in a low-level environment   
•	Team collaboration and debugging complex concurrency and parsing issues   


## Try it out!

#### Prerequisites   

•	Unix-based OS (Linux or macOS)   
•	GCC compiler   
•	readline library installed   

#### Installation

```bash
# Clone the repo
git clone https://github.com/svvoii/Minishell.git

# Go into the project directory
cd Minishell

# Build the shell
make

# Run the shell
./minishell
```

## Usage

### Example session

```bash
$ echo hello
hello

$ export VAR=test
$ echo $VAR
test

$ ls | grep minishell
minishell.c
```

---

## Contributors

@svvoii  
@SharkidFincher

---
