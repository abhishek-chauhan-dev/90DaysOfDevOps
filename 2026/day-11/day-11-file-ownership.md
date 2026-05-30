# Day 11 – File Ownership Challenge (chown & chgrp)

## Files & Directories Created
- ls -l: lists all the files & directories

<img width="569" height="241" alt="1" src="https://github.com/user-attachments/assets/3465764f-a742-405f-bf6d-75f67dbb5338" />

## Ownership Changes
- Created file devops-file.txt
- Before changing ownership, ran command: ls -l devops-file.txt
- After changing ownership, ran command: ls -l devops-file.txt

<img width="782" height="582" alt="2" src="https://github.com/user-attachments/assets/0d7425cf-8036-4d47-9649-b6033b614eee" />

## Commands Used
- ls -l
<img width="569" height="241" alt="1" src="https://github.com/user-attachments/assets/ba45dd3b-f44a-4aa6-9d52-6e001718f04d" />

- touch devops-file.txt
- ls -l devops-file.txt
- sudo chown tokyo devops-file.txt
- sudo chown berlin devops-file.txt
<img width="782" height="582" alt="2" src="https://github.com/user-attachments/assets/c035b07e-87ab-40ce-8ad1-c4dae18b821f" />

- touch team-notes.txt
- ls -l team-notes.txt
- sudo groupadd heist-team
- sudo chgrp heist-team team-notes.txt
<img width="722" height="555" alt="3" src="https://github.com/user-attachments/assets/68079489-c3ca-4be2-bde8-f3b40733d8fa" />

- ls -l team-notes.txt
- touch project-config.yaml
- ls -l project-config.yaml
- sudo chown professor:heist-team project-config.yaml
- ls -l project-config.yaml
- mkdir app-logs
- sudo chown berlin:heist-team app-logs/
<img width="795" height="265" alt="4" src="https://github.com/user-attachments/assets/e37b301f-1f48-4bb2-b382-c0359e407254" />
<img width="810" height="540" alt="5" src="https://github.com/user-attachments/assets/c38f5899-e50e-49ac-a30d-a52ad2766b9d" />
 
- mkdir -p heist-project/vault
- mkdir -p heist-project/plans
- touch heist-project/vault/gold.txt
- touch heist-project/plans/strategy.conf
- sudo groupadd planners
- sudo chown -R professor:planners heist-project/
- ls -l
- ls -lR heist-project/
<img width="920" height="712" alt="7" src="https://github.com/user-attachments/assets/250a1bc5-a546-40bf-ae4f-cf47c9c1f0f7" />
<img width="751" height="629" alt="8" src="https://github.com/user-attachments/assets/4d4a67da-7beb-417a-81ba-02c528474ca2" />

- groupadd vault-team
- sudo groupadd vault-team
- cat /etc/group | grep -i "vault"
- cat /etc/group | grep -i "tech-team"
- groupadd tech-team
-  sudo groupadd tech-team
- cat /etc/group | grep -i "tech-team"
- mkdir bank-heist
- ls -l
- touch bank-heist/access-codes.txt
- touch bank-heist/blueprints.pdf
- touch bank-heist/escape-plan.txt
- tree bank-heist/
- ls -l bank-heist/
- sudo chown tokyo:vault-team bank-heist/access-codes.txt
- sudo chown berlin:tech-team bank-heist/blueprints.pdf
- sudo chown nairobi:vault-team bank-heist/escape-plan.txt
- ls -l bank-heist/
<img width="746" height="719" alt="9" src="https://github.com/user-attachments/assets/b40f06c1-fe1b-4f38-a2f5-741fb9e90deb" />
<img width="820" height="642" alt="10" src="https://github.com/user-attachments/assets/de956494-2053-43c7-a377-fa88e3d93cb1" />


## What I Learned
- Linux uses "Priniciple of Least Privilege". Using this, we can control who can access what.
- Since, linux supports multi-user, ownership & permissions becomes the prominent part of linux.
