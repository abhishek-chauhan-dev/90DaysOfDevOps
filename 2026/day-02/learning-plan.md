# What is Linux ?

- Linux OS = Linux kernel + software

# What is Linux Kernel ?
Linux kernel is linux. Kernel is a program which controls everything.
- network, disk, memory, cpu
- files
- users & permissions
- runs programs

The kernel is written in the C language. To interact with it, we need something. Here comes "SHELL".

# What is a Shell ?
A program which works like a translator, i.e., it translates human-readable commands into a form which the kernel understands, the kernel performs an action, the shell returns the output.

When we SSH into a server, it starts a new Bash process, just for your session, i.e. shell for you which is ready to accept commands from you.

eg: When you type "ls" command, this is what happens in the background :

(a) Shell reads the command

(b) The shell searches for the "ls" program in the directories listed in PATH variable

(c) Once found, the shell asks the kernel to start that program.

(d) The kernel loads and runs the ls program.

(e) The program generates output.

(f) The output is shown on the screen through the terminal emulator.

# What is Terminal Emulator ?
A terminal emulator is an application which a user interacts with to perform tasks. It does not perform processing by itself, that is taken care by kernel.

It has 2 jobs:

(a) sending the request from user to shell
  
(b) returning the output from stdout to the user

Terminal: In earlier days, there was a physical machine which connected to the main computer. Its job was to take the input from user, send it to shell and return the output back to user. Terminal emulator is the software version of it.

eg: VT100

# What is a command-line interface ?

Text-based interface to talk to a computer

# What is a prompt in Linux ?

Prompt: user@ubuntu:~$

user - Who you're logged in as

ubuntu - What computer you're on

~ - Your current directory (~ means home directory)

$ - You're a normal user (# means root/admin)

# Linux day to day commands ?

- ssh -i private_key username@ip_address
- whoami
- hostname
- pwd
- ls
- cat
- date
- uptime
- echo
- touch
- rm <file-name>
- history
