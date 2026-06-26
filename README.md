# 🌐 Web Infrastructure & Deployment Notes

A beginner-friendly guide to understanding how web applications work behind the scenes.

This repository contains my personal notes while learning **Web Infrastructure**, **Networking**, and **Application Deployment**. It explains how a web application travels from a user's browser to a server and back.

---

# 📚 Topics Covered

* Internet Basics
* Client-Server Architecture
* Domain Names
* DNS (Domain Name System)
* IP Address
* VPS (Virtual Private Server)
* VPN (Virtual Private Network)
* Nginx
* Reverse Proxy
* HTTP & HTTPS
* Ports
* Node.js Application Hosting
* Next.js Deployment
* SSL/TLS
* PM2

---

# 🌍 How a Website Works

When a user visits a website, several components work together.

```
User
   │
   ▼
Browser
   │
   ▼
DNS
   │
   ▼
VPS
   │
   ▼
Nginx
   │
   ▼
Node.js / Next.js Application
   │
   ▼
Database
   │
   ▼
Response
   │
   ▼
Browser
```

---

# 🌐 Domain Name

A domain name is the human-readable name of a website.

Example:

```
google.com
github.com
example.com
```

Instead of remembering an IP address like:

```
142.250.190.78
```

we simply remember:

```
google.com
```

---

# 🌐 DNS (Domain Name System)

DNS is the Internet's phonebook.

Its job is to convert a domain name into an IP address.

Example:

```
example.com
        │
        ▼
194.195.117.171
```

Without DNS, users would need to remember IP addresses instead of website names.

---

# 🖥️ VPS (Virtual Private Server)

A VPS is a virtual computer hosted inside a data center.

It provides:

* CPU
* RAM
* Storage
* Operating System
* Public IP Address

A VPS can run:

* Ubuntu
* Node.js
* Nginx
* Docker
* Databases
* Any backend application

Example:

```
+------------------------+
|        VPS             |
|------------------------|
| Ubuntu                 |
| Node.js                |
| Nginx                  |
| MySQL                  |
| Docker                 |
+------------------------+
```

---

# 🔒 VPN (Virtual Private Network)

A VPN creates a secure encrypted tunnel between your device and another server.

Without VPN

```
Laptop
   │
Internet
   │
Website
```

With VPN

```
Laptop
   │
Encrypted Tunnel
   │
VPN Server
   │
Website
```

Benefits:

* Hides your public IP
* Encrypts internet traffic
* Secure public Wi-Fi
* Remote access to private networks

---

# 🔀 Nginx

Nginx is a web server and reverse proxy.

It receives requests from users and forwards them to your application.

Example:

```
Browser
   │
   ▼
Nginx
   │
   ▼
Next.js App
```

---

# 🔄 Reverse Proxy

A reverse proxy sits between users and your application.

Instead of users connecting directly to your app,

```
Browser
      │
      ▼
Nginx
      │
      ▼
Node.js Application
```

Benefits:

* HTTPS Support
* Load Balancing
* Security
* Better Performance
* Hide Internal Ports

---

# 🚀 Node.js Application

Suppose your application starts like this:

```bash
npm run start
```

It may run on:

```
localhost:3000
```

Users should **not** access it directly.

Instead,

```
Browser
      │
      ▼
Nginx (80/443)
      │
proxy_pass
      ▼
localhost:3000
```

Nginx forwards requests to the application.

---

# 🌍 Complete Deployment Flow

```
User
 │
 ▼
Types example.com
 │
 ▼
DNS
 │
 ▼
Public IP
 │
 ▼
VPS
 │
 ▼
Ubuntu
 │
 ▼
Nginx
 │
 ▼
Node.js / Next.js
 │
 ▼
Database
 │
 ▼
Response
 │
 ▼
Browser
```

---

# 🔢 Ports

Applications listen on ports.

Examples:

```
80   -> HTTP
443  -> HTTPS
3000 -> Next.js
5000 -> Express API
5432 -> PostgreSQL
3306 -> MySQL
27017 -> MongoDB
```

Only one application can listen on the same port.

---

# 🔐 HTTPS

HTTPS is the secure version of HTTP.

It encrypts communication between the browser and the server using SSL/TLS certificates.

```
Browser
   │
HTTPS
   │
Nginx
   │
Application
```

---

# ⚙️ PM2

PM2 is a process manager for Node.js applications.

It keeps your application running even if it crashes.

Example:

```bash
pm2 start npm --name myapp -- start
```

Benefits:

* Auto restart
* Process monitoring
* Logs
* Startup on reboot

---

# 🧠 Key Takeaways

* **Domain** → Human-readable website name.
* **DNS** → Converts a domain into an IP address.
* **VPS** → A virtual server where your application runs.
* **VPN** → A secure network connection for privacy and remote access.
* **Nginx** → Receives web requests and forwards them to your application.
* **Reverse Proxy** → Hides internal application ports and improves security.
* **Node.js/Next.js** → Runs your backend or full-stack application.
* **PM2** → Keeps your Node.js application running.
* **HTTPS** → Secures communication using SSL/TLS.

---

# 🎯 Goal

The goal of this repository is to build a strong understanding of **Web Infrastructure**, **Networking**, and **Deployment** concepts required for Full-Stack Development and DevOps.

# ❓ Frequently Asked Questions (Interview Style)

## 1. What is a Domain?

A domain is the human-readable name of a website.

Example:

```text
google.com
github.com
example.com
```

Instead of remembering an IP address, users remember a domain name.

---

## 2. What is DNS?

DNS (Domain Name System) converts a domain name into an IP address.

Example:

```text
example.com
      │
      ▼
194.195.117.171
```

Without DNS, users would have to remember IP addresses.

---

## 3. What is an IP Address?

An IP address is the unique address of a device connected to the internet.

Example:

```text
194.195.117.171
```

It is similar to the address of your house.

---

## 4. What is a VPS?

A VPS (Virtual Private Server) is a virtual computer hosted in a data center.

You can install:

* Ubuntu
* Node.js
* Nginx
* Docker
* Databases

Your application runs inside the VPS.

---

## 5. What is a VPN?

VPN stands for Virtual Private Network.

It creates an encrypted tunnel between your device and a VPN server.

Benefits:

* Hides your IP address
* Encrypts internet traffic
* Secure public Wi-Fi
* Remote access

---

## 6. VPS vs VPN

| VPS                   | VPN                       |
| --------------------- | ------------------------- |
| Virtual computer      | Secure network connection |
| Hosts applications    | Protects internet traffic |
| Has CPU, RAM, Storage | Creates encrypted tunnel  |
| Used for deployment   | Used for privacy          |

---

## 7. What is Nginx?

Nginx is a web server and reverse proxy.

It receives requests from users and forwards them to your application.

Example:

```text
Browser
   │
Nginx
   │
Node.js App
```

---

## 8. Is Nginx part of a VPS?

No.

A VPS is a virtual computer.

Nginx is software that you install on the VPS.

---

## 9. Does the application run on the VPS?

Yes.

Example:

```text
VPS
│
├── Ubuntu
├── Nginx
├── Node.js
└── Next.js App
```

The application runs on the VPS.

---

## 10. How does Nginx know the application is running on port 3000?

Because we configure it.

Example:

```nginx
location / {
    proxy_pass http://localhost:3000;
}
```

`proxy_pass` tells Nginx where the application is running.

---

## 11. What is localhost?

`localhost` means **this computer**.

Example:

```text
localhost:3000
```

means an application running on port **3000** on the same VPS.

---

## 12. Why don't users access port 3000 directly?

Instead of:

```text
http://example.com:3000
```

users access:

```text
https://example.com
```

Nginx receives the request on ports **80** or **443** and forwards it internally to port **3000**.

---

## 13. What is a Reverse Proxy?

A reverse proxy sits between the client and the application.

```text
Browser
   │
Nginx
   │
Application
```

The client never communicates directly with the application.

Benefits:

* HTTPS
* Security
* Load balancing
* Better performance

---

## 14. What are Ports?

Ports identify different services running on the same server.

Examples:

```text
80    HTTP
443   HTTPS
22    SSH
3000  Next.js
5000  Express
3306  MySQL
5432  PostgreSQL
27017 MongoDB
```

---

## 15. What is SSH?

SSH (Secure Shell) is used to securely connect to a remote server.

Example:

```bash
ssh root@194.195.117.171
```

This opens a terminal on the VPS.

---

## 16. What is PM2?

PM2 is a process manager for Node.js applications.

It keeps applications running even if they crash.

Example:

```bash
pm2 start npm --name myapp -- start
```

---

## 17. What is HTTP?

HTTP (HyperText Transfer Protocol) is used for communication between browsers and web servers.

It is **not encrypted**.

---

## 18. What is HTTPS?

HTTPS is the secure version of HTTP.

It encrypts communication using SSL/TLS certificates.

---

## 19. What is SSL/TLS?

SSL/TLS encrypts data transferred between the browser and the server.

Without SSL:

```text
Browser ---- Server
```

With SSL:

```text
Browser ====Encrypted==== Server
```

---

## 20. How does a request reach my application?

```text
User
 │
 ▼
Browser
 │
 ▼
DNS
 │
 ▼
Public IP
 │
 ▼
VPS
 │
 ▼
Nginx
 │
 ▼
Node.js Application
 │
 ▼
Database
 │
 ▼
Response
 │
 ▼
Browser
```

---

## 21. Can multiple applications run on one VPS?

Yes.

Example:

```text
VPS
│
├── Next.js App (3000)
├── Express API (5000)
├── Admin Panel (8080)
└── Nginx
```

Nginx routes requests to the correct application.

---

## 22. Why do we need DNS if we already have an IP address?

Because domain names are easier to remember.

Instead of:

```text
194.195.117.171
```

we simply use:

```text
example.com
```

DNS converts the domain into its IP address.

---

## 23. What is the complete deployment flow?

```text
User
 │
 ▼
Domain
 │
 ▼
DNS
 │
 ▼
Public IP
 │
 ▼
VPS
 │
 ▼
Ubuntu
 │
 ▼
Nginx
 │
 ▼
Node.js / Next.js
 │
 ▼
Database
 │
 ▼
Response
 │
 ▼
Browser
```

---

# 🚀 Interview Summary

* Domain → Website name
* DNS → Converts domain to IP
* IP Address → Address of a server
* VPS → Virtual server where applications run
* VPN → Secure encrypted network
* Nginx → Web server and reverse proxy
* Reverse Proxy → Routes requests to applications
* Node.js → Runs backend applications
* PM2 → Keeps applications running
* HTTP → Unsecured communication
* HTTPS → Secure encrypted communication
* SSH → Remote server access
* Ports → Identify different services
* SSL/TLS → Encrypts communication


