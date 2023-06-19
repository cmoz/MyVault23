
1. Use a unix-based system to manipulate directories and files, and execute commands to complete simple tasks
    
2. Create, transfer, and edit files  in a unix system
    
3. Use tools (such as gcc, gdb, and objdump) on a unix system) to compile and examine execution of code, and interpret data files.


To use a UNIX shell to perform simple tasks such as creating files and directories, compiling programs, disassembling programs, and editing files, you can write shell scripts ¹³.

Shell scripts are written using text editors such as vim or nano ¹. Once you have written your shell script, you can make it executable using the chmod command ².

Here is an example of a simple shell script that creates a directory:

```
#!/bin/bash
mkdir my_directory

```

(1) Shell Scripting Tutorial: How to Create Shell Script in Linux/Unix - Guru99. [https://www.guru99.com/introduction-to-shell-scripting.html](https://www.guru99.com/introduction-to-shell-scripting.html) Accessed 01/06/2023. (2) Shell Scripting for Beginners – How to Write Bash Scripts in Linux. [https://www.freecodecamp.org/news/shell-scripting-crash-course-how-to-write-bash-scripts-in-linux/](https://www.freecodecamp.org/news/shell-scripting-crash-course-how-to-write-bash-scripts-in-linux/) Accessed 01/06/2023. (3) bash - How do I create new unix executable (.sh?) files for the .... [https://stackoverflow.com/questions/45391309/how-do-i-create-new-unix-executable-sh-files-for-the-terminal-to-use-as-comm](https://stackoverflow.com/questions/45391309/how-do-i-create-new-unix-executable-sh-files-for-the-terminal-to-use-as-comm) Accessed 01/06/2023. (4) Automating Tasks With Bash Scripts [Practical Examples] - Linux Handbook. [https://linuxhandbook.com/bash-automation/](https://linuxhandbook.com/bash-automation/) Accessed 01/06/2023. (5) The Linux command line for beginners | Ubuntu. [https://ubuntu.com/tutorials/command-line-for-beginners](https://ubuntu.com/tutorials/command-line-for-beginners) Accessed 01/06/2023.

`objdump` is a Linux utility that allows users to disassemble and examine binary files. It can be used to examine object files, executables, shared libraries, and core dumps. It can also be used to display the symbol table, dynamic linking information, and the disassembly of the file¹.

Here is an example of how you can use `objdump` to examine a data file:

```
$ objdump -s -j .data datafile

```

This command will display the contents of the `.data` section of the `datafile`.

(1) Using Objdump To Debug Software In Linux: An Essential Tutorial. [https://www.systranbox.com/using-objdump-to-debug-software-in-linux-an-essential-tutorial/](https://www.systranbox.com/using-objdump-to-debug-software-in-linux-an-essential-tutorial/) Accessed 01/06/2023. (2) Linux objdump Command Explained for Beginners (7 Examples) - HowtoForge. [https://www.howtoforge.com/linux-objdump-command/](https://www.howtoforge.com/linux-objdump-command/) Accessed 01/06/2023. (3) objdump(1) - Linux manual page - [man7.org](http://man7.org/). [https://www.man7.org/linux/man-pages/man1/objdump.1.html](https://www.man7.org/linux/man-pages/man1/objdump.1.html) Accessed 01/06/2023. (4) Objdump Command in Linux with Examples - GeeksforGeeks. [https://www.geeksforgeeks.org/objdump-command-in-linux-with-examples/](https://www.geeksforgeeks.org/objdump-command-in-linux-with-examples/) Accessed 01/06/2023. (5) objdump to extract contents of text segment to a binary format. [https://stackoverflow.com/questions/20898354/objdump-to-extract-contents-of-text-segment-to-a-binary-format](https://stackoverflow.com/questions/20898354/objdump-to-extract-contents-of-text-segment-to-a-binary-format) Accessed 01/06/2023.