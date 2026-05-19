# Linux Practice: Processes and Services

# Run and record output for at least 6 commands
- id: shows information about a user along with its id
- groups: display user is part of which group
- groups jenkins: display "jenkins user" is part of which group
- whoami: who is logged in to system i.e. current user
- who: more information than whoami about the current logged in user to system
- w: more information than who about the current logged in user to system

# Include 2 process commands
- ps aux: shows a list of running process
- top: shows live status of the running processes

# Include 2 service commands
- systemctl status docker: shows details of the docker service
- systemctl enable docker: will start the docker service on system reboot

# Include 2 log commands
- journalctl -u docker: to see the logs of docker service
- tail -f (file-name): shows live logs/content of a file

# Pick one service on your system (example: ssh, cron, docker) and inspect it
- systemctl status docker: shows details of the docker service
- ps aux | grep -i "docker": shows details of the docker service from the running processes
