# Day 16 – Shell Scripting Basics

## Task 1: Your First Script
1) Create a file hello.sh
2) Add the shebang line #!/bin/bash at the top
3) Print Hello, DevOps! using echo
4) Make it executable and run it

<img width="535" height="462" alt="image" src="https://github.com/user-attachments/assets/09706269-612f-4d5b-ad68-7b5ece5e5715" />

5) What happens if you remove the shebang line ?
- Kernel will not understand which shell to use to run the script. Due to this, if we are on a different shell, syntax of one shell might fail for another shell. That is why, using a shebang, it tells the kernel which shell to use to run the below script.

## Task 2: Variables
1) Create variables.sh with:
- A variable for your NAME
- A variable for your ROLE (e.g., "DevOps Engineer")
- Print: Hello, I am (NAME) and I am a (ROLE)

<img width="587" height="312" alt="image" src="https://github.com/user-attachments/assets/956d2a90-ede1-4742-9a19-f13e3139ab2a" />

2) Try using single quotes vs double quotes — what's the difference ?
- Single quotes: prints variables as it is.
- Double quotes: prints the value of variable which it reference to.

<img width="473" height="291" alt="image" src="https://github.com/user-attachments/assets/ea8fdd3a-c68e-4ed3-ae2a-40de7210ee7a" />

## Task 3: User Input with read
1) Create greet.sh that:
- Asks the user for their name using read
- Asks for their favourite tool
- Prints: Hello (name), your favourite tool is (tool)
<img width="516" height="307" alt="4" src="https://github.com/user-attachments/assets/46121b4a-1226-426f-92cf-5298658c7e31" />

## Task 4: If-Else Conditions
1) Create check_number.sh that:
- Takes a number using read
- Prints whether it is positive, negative, or zero
<img width="585" height="422" alt="5" src="https://github.com/user-attachments/assets/d15998f9-7539-4bf4-8bb2-f7ef9e076f33" />

2) Create file_check.sh that:
- Asks for a filename
- Checks if the file exists using -f
- Prints appropriate message
<img width="596" height="362" alt="image" src="https://github.com/user-attachments/assets/8fd71b82-c368-4e77-a5ae-30e743538f47" />

## Task 5: Combine It All
1) Create server_check.sh that:
- Stores a service name in a variable (e.g., nginx, sshd)
- Asks the user: "Do you want to check the status? (y/n)"
- If y — runs systemctl status <service> and prints whether it's active or not
- If n — prints "Skipped."
<img width="1228" height="656" alt="image" src="https://github.com/user-attachments/assets/78e9f206-5381-493d-93cc-cd7a630e4f4f" />
