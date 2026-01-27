# What Happens When You Type https://www.google.com in your browser and press Enter
This is a classic interview question  used to assess a software engineer's understanding of how the web works.
In the article, we will walk step by step through what happens when a user types `https://www.google.com` into a browser and presses **Enter**.

## 1. DNS Request
When the user enters `https://www.google.com`, the browser first needs to know **which server** to contact.
- The browser checks its cache to see if it already knows the IP address.
 - If not found, it asks the operating system.
 - If still unknown, a **DNS request** is sent to a DNS resolver.
 - DNS translates the domain name `www.google.com` into **IP address (for example: `142.250.74.206).
Once the IP address is known, the browser can contact the server.

## 2. TCP/IP Connection
Using the IP address, the browser etablishes a connection with the server using **TCP/IP**.
- TCP ensures reliable communication.
- A **three-way handshake** occurs:
    1. SYN
    2. SYN-ACK
    3. ACK
This guarantees that both the client and server are ready to communicate.

## 3. Firewall
Before the request reaches the server, it may pass through one or more **firewalls**.
- Firewalls filter traffic.
- They block malicious or unauthorized requests.
Only allowed traffic (such as HTTPS on port 443) is permitted.

## 4. HTTPS/ SSL
Because the URL starts with **https**, an encrypted connection is required.
- The browser and server perform an **SSL/TLS handshake**.
- The server sends its SSL certificate.
- The browser verifies the certificate.
- A secure, encrypted session is etablished.
This projects the data from being intercepted or modified.

## 5. Load Balancer
For large websites like Google, traffic does not go to a single server.
- The request reaches a **load balancer**.
- The load balancer distributes incoming requests across multiple servers.
- This improves performance and reliability.

## 6. Web Server
The request is fordwarded to a **web server** (such as Nginx or Apache).
- The web server handles HTTP request.
- It serves static content or forwards dynamic requests to the application server.

## 7. Application server
The **application server** processes the business logic.
- It execute application code.
- it determines what data is needed.
- It communicates with the database if required.

## 8. Database
If data is needed, the application server queries the **database**.
- The database stores persistent data.
- It retrieves or updates information.
- The response is sent back to the application server.

## 9. Response Back To The Browser
- The application server sebds data to the web server.
- The web sever sends an HTTP response to the browser.
- The browser renders the HTML, CSS and Javascript.
- The user sees the Google homepage.

## Conclusion
From a simple browser action, many systems work together:
DNS, TCP/IP, firewalls, HTTPS, load balancers, servers and databases.
Understanding this workflow is essential for any software engineer working with web technologies.
