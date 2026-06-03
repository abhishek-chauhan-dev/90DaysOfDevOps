Day 14 – Networking Fundamentals & Hands-on Checks

# OSI layers
- Application layer: User interacts with this layer, eg: Chrome, Whatsapp comes here
- Presentation layer: deals with presentation of data whether it will use http/https or anyother protocol to send data. Encryption of data is handled here.
- Session layer: establishes a connection between the client and server.
- Transport layer: handles transportation of data i.e. how much size of data can be sent at a time. So, this layer divide the data into chunks and transports it using protocole TCP (reliable) or UDP (not reliable).
- Network layer: deals with IP address & routing, decides where to send this data, routers comes here
- Data link layer: used to reach the next device using MAC address, switches comes here
- Physical layer: actual data (in the form of bits) flows from here, cables comes here

# Mini Task: Port Probe & Interpret
1) Identify one listening port: ss -tulnp
<img width="1366" height="627" alt="3" src="https://github.com/user-attachments/assets/25e18d68-d51d-4346-a314-7b331c46af5e" />

2) From the same machine, test it: nc -zv localhost <port> (or curl -I http://localhost:<port>)
<img width="818" height="644" alt="7" src="https://github.com/user-attachments/assets/246d5552-834b-431b-bd6e-5dd7a470b35c" />

3) Write one line: is it reachable?
- Yes, I am able to access the nginx service both from the local as well as from the browser.
- If it has failed, I would first verify if the service is running or not. If the service is running, check the logs and identify the port on which it is running. Once the port is also identified, I will check if the ingress traffic is allowed on my server, is there any firewall blocking it.

4) Which command gives you the fastest signal when something is broken ?
- ping : to check if the server is reachable on internet
- curl : to check if the application is working as intended
- systemctl : to validate if the service is running or not

5) What layer (OSI/TCP-IP) would you inspect next if DNS fails? If HTTP 500 shows up?
- Order of checks: DNS (Application layer) -> Port (Transport layer) -> IP (Network layer)
- If an HTTP 500 response is returned, the request successfully reached the web server, which means DNS resolution, network connectivity, and the TCP connection were successful. The server was reachable on the correct IP and port. The issue is likely within the application or one of its dependencies, so the next step is to inspect application and web server logs.

6) Two follow-up checks you’d run in a real incident ?
- Check if the application is running based on the logs
- Check the application dependencies are also healthy like databases, configurations, etc.
