## Day 15 – Networking Concepts: DNS, IP, Subnets & Ports

# Task 1: DNS – How Names Become IPs

(1) what happens when you type google.com in a browser?

- when we type "google.com", based on browser cache, device try to
find the IP address of the server.
- If above step fails, it looks for IP address in OS cache.
- If above step fails, it looks for IP address in ISP DNS records.
- If above step fails, it looks for IP address in Google DNS records.
By this point, the IP address of the server is identified on the internet. If the IP address is still not be found, then it looks for in Google
Authoritative server and identifies the IP address of the device.

- Once IP address of the server is identified, a TCP connection is established between the client and  server using 3 way handshake.

- Server sends a certificate to the client, if configured and client acceptsit.

- HTTP (GET) request initiated from the browser.

- Through multiple routers, it reaches cables.

- From cables the request reaches to Load balancer, which is accessible from the internet, and it has access to resources in a private network.

- Once the loadbalancer forwards the requests to server on port, which application listening to, it finally reaches the application.

(2) What are these DNS record ?

- stores information of a domain.

(3) What are these DNS record types ?

- A : maps a domain to IPv4 address
- AAAA : maps a domain to IPv6 address
- CNAME : creates an alias for another domain
- MX : where emails for your domain should go.
- NS : which DNS servers manage the domain's DNS records.

(4) Why do we need a DNS record type ?

- DNS record stores different types of information that is why we need
different DNS record types

(5) Run: dig google.com — identify the A record and TTL from the output
<img width="819" height="565" alt="image" src="https://github.com/user-attachments/assets/4f046eb0-70a4-4b7d-8126-210ce5255368" />

# Task 2: IP Addressing

(1) What is an IPv4 address ?
- unique number assigned to a device to identify it in a network.

(2) How is it structured ?
- 4 octects, 32 bits separated by dot (.)

(3) Difference between public and private IPs
- public: available on internet, can be routed
eg: 8.8.8.8
- private: not available on internet, can't be routed
eg: 10.208.80.54

(4) What are the private IP ranges ?
- 10.0.0.0 - 10.255.255.255 or 10.0.0.0/8
- 172.16.0.0 - 172.31.255.255 or 172.16.0.0/12
- 192.168.0.0 - 192.168.255.255 or 192.168.0.0/16

# Task 3: CIDR & Subnetting

(1) What does /24 mean in 192.168.1.0/24 ?
- /24 implies 24 network bits out of 32 bits.
- 8 bits are host bits.
- Total IPs = 2^(32-24) = 2^8 = 256 IPs in this
network.

(2) How many usable hosts in a /24? A /16? A /28 ?
- /24:
Subnet mask = 255.255.255.0;
Total IPs = 2^(32-24) = 2^8 = 256 IPs;
Usable IPs = 256-2 = 254 IPs

- /16:
Subnet mask = 255.255.0.0;
Total IPs = 2^(32-16) = 2^16 = 65536 IPs;
Usable IPs = 65534-2 = 65534 IPs

- /28:
Subnet mask = 255.255.255.240;
Total IPs = 2^(32-28) = 2^4 = 16 IPs;
Usable IPs = 16-2 = 14 IPs

(3) Why do we subnet ?
- Enhance security of our network
- To manage a network efficiently

# Task 4: Ports – The Doors to Services

(1) What is a port ?
- communication endpoint on a device from which we can send or receive data to a specific application or a service.
- traffic (incoming/outgoing) connects to a specific application through ports, like a gateway on a device.

(2) Why do we need them ?
- On a device, multiple applications will be running. In such a scenario, when the traffic comes from the external world, how the device will identify where i.e. which service to route the traffic to, through ports, it is managed.

(3) Common ports:
- 22: SSH
- 53: DNS
- 80: HTTP
- 443: HTTPS
- 27017: Mongodb
- 3306: Mysql
- 6379: Redis

(4) Run ss -tulpn — match at least 2 listening ports to their services
<img width="1366" height="678" alt="image" src="https://github.com/user-attachments/assets/8ee175d5-3b6d-47f9-9b15-ba181f422c11" />

# Task 5: Putting It Together

(1) You run curl http://myapp.com:8080 — what networking concepts from today are involved ?
- Request goes from the client browser (application) to the application to myapp.com.
- DNS resolves the domain to an IP address, reachable on the internet.
- Based on the IP address, router identifies the shortest path to reach the server, where application is running, using routing rules.
- Once the request reaches the server. Since the application listens on port 8080, the request is sent through this port to the application and the application receive the request and returns an intended response.

(2) Your app can't reach a database at 10.0.1.50:3306. what would you check first?
- check if the database service is running or not.
