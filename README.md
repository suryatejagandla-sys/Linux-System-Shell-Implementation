# Linux System Shell Implementation (C)

A minimal, high-performance command-line interpreter built in C to explore Unix system internals and process management.

## Technical Objectives
- **Process Lifecycle:** Utilizing `fork()`, `exec()`, and `wait()` system calls to manage process creation and synchronization.
- **Memory Management:** Implementing dynamic memory allocation and buffer management for command parsing.
- **Built-in Commands:** Development of internal shell commands (cd, help, exit) to understand shell execution flow.

## Systems Programming Concepts
- **Child & Parent Processes:** Handling concurrent execution and process IDs (PID).
- **Tokenization:** Implementing a custom parser to handle user input strings.
- **System Calls:** Direct interaction with the Linux kernel via standard C libraries.

## Relevance to C-DAC
Understanding the underlying mechanisms of an Operating System is critical for High-Performance Computing (HPC) and system-level R&D at C-DAC.LSH
===

It is a simple implementation of a shell in C, and it is the subject of a
tutorial on [my website][1].  It demonstrates the basics of how a shell works.
That is: read, parse, fork, exec, and wait.  Since its purpose is demonstration
(not feature completeness or even fitness for casual use), it has many
limitations, including:

* Commands must be on a single line.
* Arguments must be separated by whitespace.
* No quoting arguments or escaping whitespace.
* No piping or redirection.
* Only builtins are: `cd`, `help`, `exit`.

Running
-------

Use `gcc -o lsh src/main.c` to compile, and then `./lsh` to run. If you would
like to use the standard-library based implementation of `lsh_read_line()`, then
you can do: `gcc -DLSH_USE_STD_GETLINE -o lsh src/main.c`.

Contributing
------------

Since this is the subject of a tutorial, I'm not looking to extend it with
additional features at this time.  So I won't be accepting any pull requests
that aren't related to bug fixes (and I'm sure there are still bugs in the
code!).

However, that doesn't mean that you shouldn't play with the code, make changes,
and explore new features!  That's the whole point of this project!  It's just
that other people are doing the same thing, and this project is merely a
starting point for your own exploration.

On that note, I would be just tickled if you dropped me a line (see my website
for contact info) to show me the cool new features you've added!

License
-------

This code is in the public domain (see [UNLICENSE](UNLICENSE) for more details).
This means you can use, modify, and distribute it without any restriction.  I
appreciate, but don't require, acknowledgement in derivative works.

[1]: http://brennan.io/2015/01/16/write-a-shell-in-c/
