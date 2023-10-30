## What happens when we run a command in linux terminal?

- **Command Entry:** We type the command, in this case, "ls," and press Enter.

- **Shell Interpretation:** The shell (e.g., Bash) interprets the command. It checks its own internal commands and, if "ls" is not one of them, it searches for an executable file named "ls" in directories listed in the PATH environment variable.

- **Path Resolution:** If "ls" is found in a directory listed in PATH, the shell locates the executable file. If it's not found, we will receive an error indicating that the command is not found.

- **Execution:** If the executable is found, it's loaded into memory, and its code is executed. In the case of "ls," it will list the contents of the current directory.

- **Output Display:** The output of the command is displayed in the terminal. For "ls," this will be a list of files and directories in the current directory.

> Example:
> - Type "ls" and press Enter.
> - The shell interprets the command and finds "ls" in the PATH.
> - It locates the "ls" executable.
> - "ls" is executed, and it lists the contents of the current directory.
> - The list of files and directories in the current directory is displayed as the output.
