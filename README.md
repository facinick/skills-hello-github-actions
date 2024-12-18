### Shell (Program)

A `shell` is a program that runs commands and manages its own `environment`, including variables and functions. These settings are specific to the `shell` process and disappear once the `shell` is closed.

### **Binary** (Compiled Program):

You installed a binary. Binary is stored somewhere on your system. You have to tell this program(shell) that where this binary is on your system when you type it’s name to run it. You can do that by adding to a variable known as PATH of this program by doing 

`export PATH="/test/path:$PATH"`  

Now when you run the command, this program scans all paths in it’s PATH variable for this stupid binary, if found executes it.

### Script (Source Code):

You installed a scripted program like nvm but there is no binary.. it’s source code that needs to run through your program. Every-time you need this source code, you run it through your program.. It often contains commands that modify the `shell` environment (e.g., `export`, aliases, or functions). You can tell your program where this source code is by doing something like 

`source /path/to/script.sh`

### What Happens When the Shell Closes?

As soon as your terminal closes, all these references to where binaries are stored, or where scripts are sourced from, are lost

### So what to do?

What to do? Every time the `shell` program starts, it runs an initialization file (like `~/.bashrc`, `~/.zshrc`, etc.) depending on the shell you're using. What if you write in this file, how to find the path to your binary, and/or also source to your scripts for you? Then Every-time your shell program opens, voila it automatically knows everything.

### **In Summary**

- A `shell`, also known as the program, manages its own `environment`. Changes are temporary and only last for the duration of the shell session unless made persistent. These changes do not carry over to other shell sessions.
- Add binary paths to `PATH` or source scripts in the shell's configuration file to ensure they are always available.
