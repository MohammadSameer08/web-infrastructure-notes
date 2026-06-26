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
