# Day 12 – Breather & Revision (Days 01–11)

(1) Which 3 commands save you the most time right now, and why ?
- update: created a shell script and added it in the PATH variable. Using update, I can run the command from any where and update the whole list in my Linux system.
- grep: helps me to filter a very big content by providing me the keyword occured anywhere in the file.
- sudo !!: whenever I get a permission issue while running a command, there is no need to type the whole command and put a sudo before the command. I can simply run this command.
  
(2) How do you check if a service is healthy ? List the exact 2–3 commands you’d run first.
- systemctl status nginx: tells me the current status of a service.
- journalctl -u nginx: display logs of a service and identify an issue in case exists.
- ps aux | grep -i "nginx": displays all the running processes belonging to nginx along with other details like who started it, PID, CPU, etc.

(3) How do you safely change ownership and permissions without breaking access ? Give one example command.
- chmod 700 notes.txt: will change the permissions to read, write & execute for the owner of the file "notes.txt"
- chown demo:tester notes.txt: will change the owner & group of a file. Now, user "demo" has the owner rights and all the users who are part of "tester" group will have access to notes.txt.

(4) What will you focus on improving in the next 3 days ?
- volumes in Linux
- practice shell scripting
- practice Git & GitHub

(5) Key takeways
- practice
