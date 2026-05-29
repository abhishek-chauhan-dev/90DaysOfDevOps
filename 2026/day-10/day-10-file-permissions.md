# Day 10: File Permissions & File Operations Challenge

## Files Created
- devops.txt
- notes.txt
- script.sh

## Permission Changes

What are current permissions ?

- owner: read & write
- group: read & write
- others: read

Who can read/write/execute?

- devops.txt: owner (read); group (read); others (read)
- notes.txt: owner (read & write); group (read); others ()
- script.sh: owner (read, write & execute); group (read & write); others (read)

<img width="573" height="352" alt="Task 4 part 1" src="https://github.com/user-attachments/assets/ed5bcdb3-8f8a-411a-ab1e-c09403987cb0" />

<img width="634" height="523" alt="Task 4 part 2" src="https://github.com/user-attachments/assets/ee0a3b3e-32dd-45b4-9cb2-895f197324ca" />

## Commands Used
- touch devops.txt
- echo "This file stores devops notes" > notes.txt
- vim script.sh
- ls -l
- cat notes.txt
- vim script.sh
- head -n 5 /etc/passwd
- tail -n 5 /etc/passwd
- ls -l notes.txt
- ls -l script.sh
- ls -l script.sh notes.txt
- ls -l script.sh notes.txt devops.txt
- chmod 764 script.sh
- ls -l script.sh
- ./script.sh
- ls -l devops.txt
- chmod 444 devops.txt
- ls -l devops.txt
- chmod 640 notes.txt
- ls -l notes.txt
- mkdir project
- ls -l project/
- ls -l
- chmod 755 project/
- ls -l
- vim devops.txt
- ./notes.txt
- sudo ./notes.txt

## Error messages
1) Editing a read-only file

<img width="599" height="713" alt="Task 5 part 2" src="https://github.com/user-attachments/assets/d990670d-8be8-4771-88c0-da3d2f83d3bd" />


2) Executing a file with no execute permissions

<img width="607" height="489" alt="Task 5 part 3" src="https://github.com/user-attachments/assets/49793b70-7e25-4767-a2db-be53fd6fa2d4" />

## What I Learned
- Importance of permissions
- How to edit a readonly file using "!"
- How to execute scripts in Linux
