# Remote Commands Execution App

> ⚠️ **Educational Use Only**  
> This software is intended **strictly for educational and research purposes**.  
> Do **NOT** use it in any unauthorized, malicious, or illegal activity.  
> The author is **not responsible** for any damage or misuse.

---

A proof-of-concept WebSocket + Flask based remote command execution system, designed for learning how client-server communication works at a low level. It features a real-time dashboard, MySQL storage, and supports sending commands to connected machines via WebSocket.

---

# Remote Commands Execution App - Admin Panel


## ✨ Features

- 📡 **WebSocket Server** – real-time client communication and status reporting  
- 🧠 **System Monitoring** – uptime, CPU, RAM, network info, etc.  
- 📊 **Flask Admin Panel** – send commands and view connected PCs  
- 🗂️ **MySQL Backend** – stores system info and connection state  
- 🔒 **Session Authentication** – basic panel protection  
- 🧵 **Async + Threading** – simultaneous Flask and WebSocket servers

---

## 📦 Stack

- `Python 3.10+`  
- `Flask`  
- `websockets`  
- `MySQL + mysql-connector-python`  
- `asyncio`, `threading`

---

# Remote Commands Execution App - Client

## ✨ Features

- 🔐 **Encrypted WebSocket Client** – connects using base64-decoded URL  
- 🧠 **System Monitoring** – collects CPU, RAM, IPs, user, uptime, and more  
- 📥 **Remote Command Execution** – receives and runs shell commands  
- 📡 **Data Reporter** – sends system status to server every 30 seconds  
- 🧩 **Executable Hash Validation** – compares SHA‑256 against API hash  
- 🕵️‍♂️ **Debugger Detection** – blocks execution inside debuggers  

---

## 📦 Stack

- `Python 3.10+`  
- `asyncio`, `websockets`, `aiohttp`, `psutil`  
- `base64`, `subprocess`, `hashlib`, `socket`, `platform`  

---

## 🔄 Client Lifecycle

1. 🔑 Fetch SHA‑256 hash from remote API  
2. 🛡 Check for debugger and file integrity  
3. 🔓 Decrypt WebSocket URL and connect  
4. 📤 Send system info to server every 30s  
5. 🧾 Await and execute shell commands  
6. 📨 Send command results back to server  

---

## 📄 License

This project is licensed under the [Mozilla Public License 2.0](https://www.mozilla.org/en-US/MPL/2.0/).

---

> Created by **custosh**
