# Linux File System Hierarchy & Practice

# Part 1: Linux File System Hierarchy [Important]

(1) / (root)
- root directory, linux starting point
- On running "ls -l /" command, got some files, directories & symbolic links
- I would use this directory when I want to understand the root filesystem of linux.

(2) /etc 
- system configurations
- On running "ls -l /etc" command, displayed system configuration files
- I would use this directory when I wanted to see the system configurations like what are the users on our systems, how many groups,etc.

(3) /home 
- user home directory, stores user files & folders
- On running "ls -l /home" command, get the user home directory
- I would use this directory when I wanted to see which users exist on the system, see their permissions, troubleshooting user issues

(4) /root 
- root user home directory, stores root user files & folders
- On running "ls -l /root" command, list contents inside the /root directory. Important point to be noted here is that, it prompted me to give password of the root user before listing the content of /root directory
- I would use this directory when I want to learn about permissions, troubleshooting the system

(5) /var 
- stores variable files i.e. log files which stores the status of services running on system
- On running the command "ls -l /var", got a list of directories like backups, log, etc.
- I would use this directory while troubleshooting an issue with a service based on the logs generated inside the /var/log directory.
  
(6) /tmp 
- stores temporary files which get removed when the system reboots
- On running command, "ls -l /tmp", got a list of temporary directories like hsperfdata_jenkins, snap-private-tmp,etc.
- I would use this directory when I am going to work on a temporary task like creating a cloning a code and building its container image. And once the system boots, that code is vanished.

(7) /bin 
- stores binaries (commands) used by users in the system to manage day to day tasks. /bin is a symbolic link to /usr/bin
- On running command, "ls -l /bin", show a list of user commands like mkdir, cp, mv, etc.
- I would use this directory to perform day to day tasks on my linux system like creating a directory, storing files in it.

(8) /sbin 
- stores binaries (commands) used by root user to manage system. /sbin is a symbolic link to /usr/sbin
- On running the command, "ls -l /sbin", shows a list of commands like systemctl, shutdown which a root (admin) uses to manage a system
- I would use this directory to check the status of a service.

(9) /opt 
- place to store third party softwares like google chrome, MS VScode,etc.
- On running the command, "ls -l /opt" shows a list of softwares installed like containerd in my case.
- I would use this directory to keep my 3d party softwares at one place so that it would be easy to manage them.

# Part 2: Scenario-Based Practice

# Scenario 1: Service Not Starting
- systemctl status myapp: with this command, I will be able to identify the status, service is enabled on reboot, service logs
- journalctl -u myapp: since this service is managed by systemd, using this command, I will find all the logs in a pager format.

# Scenario 2: High CPU Usage
- top OR htop OR btop: interactive (live) process viewer
- ps aux: lists all the running processes, based on it, we can filter out the process consuming the maximum CPU & memory

# Scenario 3: Finding Service Logs
- journalctl -u service-name: display all the logs associated with the service. Using flags, we can further modify the stdout

# Scenario 4: File Permissions Issue
- ls -l: lists the files along with details of the file i.e., premissions attached to the file, owner & group, the file belongs to
- Once it is identified that the user is missing necessary permissions, using sudo (temporary root) privileges, we can update the permissions like this, chmod 755 file-name and perform the further action
