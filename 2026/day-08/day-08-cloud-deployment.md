# Server Setup: Docker, Nginx & Web Deployment

# Part 1: Launch a VM & SSH Access
- Created a Ubuntu VM on my laptop using VMware hypervisor.
- Using ssh-keygen command, created key-pairs and copied the public key to my ubuntu server using ss-copy-id command.
- Using command ssh user@192.168.1.100, logged in to my ubuntu server from the terminal emulator [WezTerm].

# Part 2: Install Docker & Nginx

To install docker & nginx, ran the below commands:

(a) sudo apt update && sudo apt install nginx -y

(b) sudo apt install docker -y

# Part 3: Security Group Configuration

I tried to access this URL in browser: http://192.168.1.100:8097 and go the nginx welcome page.
<img width="1366" height="456" alt="11" src="https://github.com/user-attachments/assets/b5292302-ad91-48bc-8b05-8872bedeefc4" />

# Part 4: Extract Nginx Logs
- Using journalctl -u nginx command, extracted the logs of nginx service. To get the live logs, use "-f" flag along with this command.
- Navigate to this directory: /var/log/nginx/access.log to see the logs of nginx
- To copy the log file from server to my local, I used this command: scp user@192.168.1.100:/var/log/nginx/access.log /c/Users/hp/Documents/

<img width="566" height="226" alt="image" src="https://github.com/user-attachments/assets/0d8a0640-436d-43ba-bae6-ed2f0180a1a2" />

# Challenges Faced
I was able to install nginx on my server but when I tried to access the URL: "http://192.168.1.100:80" in the browser, I got 404 NotFound error.

<img width="432" height="216" alt="err-1" src="https://github.com/user-attachments/assets/c8942d44-f80b-4658-a315-b9c39b6d9d94" />

To fix this issue, I used ChatGPT, tried to debug the the issue. On debugging, came to know that nginx was listening on port 80. Not only this, I was running a K3s cluster earlier on the same server due to which, there was an ingress-controller (traefik) which was taking those incoming requests from browser to no where.

<img width="1366" height="111" alt="7" src="https://github.com/user-attachments/assets/88d382c7-05fc-4e49-ad2e-9679695781fc" />

To fix this issue, since no 2 applications can't run on the same port, I navigated to this file: /etc/nginx/sites-available/default and changed the nginx port from 80 to 8097. Then, I restarted the nginx service using systemctl restart nginx command.

Now, when I tried to access the URL: http://192.168.1.100:8097 in the browser, nginx page was coming up as intended.

<img width="1366" height="456" alt="11" src="https://github.com/user-attachments/assets/a986ce9a-9078-4164-aa62-e821e3539612" />

# What I learned
- If your service is not reachable from the internet, first check locally.
- Check if the service is running using systemctl
- Check on which port it is listening to using ss -tulnp and check configurations as well
- Check if it is listening locally using curl localhost
- Check if it is reachable from outside (from your laptop) using ping VM-ip. Later, curl http://192.168.1.100:80, what this shows ? 
check it.
- Check if the firewall has blocked that port on which your service is exposed.

Getting a Nginx Welcome Page wasn't easy but the journey was enjoyable as it taught me "How to debug a service".
