# Commands in Linux:

# Files:
(a) Create, view, edit, copy, move/rename, remove:

- create: touch (file-name), vi (file-name), nano (file-name)
- edit: vi (file-name), nano (file-name)
- view: cat (file-name)
- copy: cp (source) (destination)
- move/rename: mv (source) (destination)
- remove: rm (file-name)

(b) find: to find files

- name: find (path) -name "*.txt"
- type: find (path) -type f or d -name "*.conf"
  
  Note: Here f represents file & d represents directory
- size: find (path) -size +10M

(c) file: info of a file
- file (file-name)

 stat: detailed info of a file
- stat (file-name)

(d) Permissions: set permission to a file
- chmod: changes mode (read (r); write(w); execute(x))

  Usage: chmod 777 (file-name) or chmod +x (file-name)
- chown: changes owner of a file/directory

  Usage: chown owner:group (file-name)
- chgrp: changes group of a file/directory

  Usage: chown group (file-name)

# Directory:
(a) Create

Usage: 
- mkdir (directory_name)

(b) Remove

Usage: 
- rmdir (directory_name)

# Manual:
(a) man: detailed information of a command

Usage: 
- man (command)

(b) which: location of a command

Usage:
- which (command)
- command -v (command)

(c) type: shows the type of a command

Usage:
- type (command)

# Processes:
- top/htop: shows live processes
