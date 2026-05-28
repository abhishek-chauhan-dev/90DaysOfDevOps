# Day 09 Challenge

## Users & Groups Created
- Users: tokyo, berlin, professor, nairobi
- Groups: developers, admins, project-team

## Group Assignments
- developers: tokyo, berlin
- admins: berlin, professor
- project-team: nairobi, tokyo

## Directories Created
- /opt/dev-project
- /opt/team-workspace

## Commands Used
- sudo adduser (username)
<img width="775" height="713" alt="1" src="https://github.com/user-attachments/assets/eb52d797-94e7-4e5e-953b-a0854fd58b2f" />

- sudo groupadd (group_name)
<img width="623" height="488" alt="6" src="https://github.com/user-attachments/assets/da08bf52-9b3e-43c3-a3a5-ec084aeab4e0" />

- sudo useradd -m (username)
<img width="603" height="650" alt="12" src="https://github.com/user-attachments/assets/c4c04ddb-0eea-4f8c-9879-ee9f92cd4ab8" />

- cat /etc/passwd
<img width="905" height="320" alt="4" src="https://github.com/user-attachments/assets/a833484d-f2a8-4b10-8739-3e2c1d98fb62" />

- cat /etc/group
<img width="623" height="488" alt="6" src="https://github.com/user-attachments/assets/eae89659-947c-481f-bdf9-866ed7eb585a" />

- sudo mkdir -p /opt/dev-project
<img width="757" height="682" alt="10" src="https://github.com/user-attachments/assets/5275d210-f7d0-4d9b-af1d-165276f8fbca" />

- chmod 775 dev-project/
<img width="757" height="682" alt="10" src="https://github.com/user-attachments/assets/dc1bd52d-d175-4266-997f-b5ac7a178cd6" />
  
- usermod -aG project-team nairobi
<img width="562" height="300" alt="7" src="https://github.com/user-attachments/assets/f846b85e-899b-4b70-a316-275bf7a5e386" />


## What I Learned
- Power of root - Supreme controller in Linux.
- How to manage permissions in Linux.
- How to manage owners & groups in Linux.
