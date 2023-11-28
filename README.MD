## Overview
SASH (Slaine-Again Shell) is a minimalistic shell program implemented in C, providing basic shell functionalities, including executing commands, handling built-in commands, and managing jobs (foreground and background processes).

## Features
- **Command Execution**: Executes both built-in and external commands.
- **Job Control**: Supports job control commands such as `bg` (background) and `fg` (foreground).
- **Signal Handling**: Handles signals like `SIGINT`, `SIGTSTP`, and `SIGCHLD`.
- **Built-in Commands**: Includes built-in commands like `quit`, `jobs`, `bg`, and `fg`.

## Functions
- `eval`: Parses and executes commands entered by the user.
- `builtin_cmd`: Checks and executes built-in commands.
- `do_bgfg`: Implements the `bg` and `fg` built-in commands.
- `waitfg`: Waits for a foreground job to complete.
- `sigchld_handler`: Handles `SIGCHLD` signals.
- `sigint_handler`: Handles `SIGINT` (Ctrl-C) signals.
- `sigtstp_handler`: Handles `SIGTSTP` (Ctrl-Z) signals.

## Usage
1. Compile the program using `gcc` or makefile by entering `make` in your shell.
2. Run the executable to start the shell.
3. Type commands at the prompt and press Enter to execute.

## Signal Handling
Press Ctrl-C to send `SIGINT` to the current foreground job. Press Ctrl-Z to stop the foreground job with `SIGTSTP`.

## Job Control
Use `jobs` to list all jobs. Use `bg %<jobid>` to continue a stopped job in the background, and `fg %<jobid>` to bring a job to the foreground.

## Exiting the Shell
Type `quit` to exit SASH.

## Note
SASH is a simple implementation and does not include all features of a full-fledged shell.



## Files:

- `Makefile`        # Compiles your shell program and runs the tests
- `README`          # This file
- `sash.c`          # The shell program that you will write and hand in
- `tshref`          # The reference shell binary.

## The remaining files are used to test the shell
- `sdriver.pl`      # The trace-driven shell driver
- `trace*.txt`      # The 15 trace files that control the shell driver
- `tshref.out`      # Example output of the reference shell on all 15 traces

## Little C programs that are called by the trace files
- `myspin.c`        # Takes argument `<n>` and spins for `<n>` seconds
- `mysplit.c`       # Forks a child that spins for `<n>` seconds
- `mystop.c`        # Spins for `<n>` seconds and sends SIGTSTP to itself
- `myint.c`         # Spins for `<n>` seconds and sends SIGINT to itself
