# 📚 Remote Commands Execution Server – Documentation

## 🧩 Overview

This is the server-side component of a remote PC control system, combining **Flask** (for the admin panel) and a **WebSocket server** (for real-time communication with clients). All client information is stored in a **MySQL** database.

---

## 🔧 Tech Stack

- Python 3.10+
- Flask – HTTP admin panel
- websockets – real-time communication with clients
- MySQL – stores client system data
- asyncio, threading – async task handling
- mysql.connector.pooling – connection pooling for MySQL

---

## 🚀 System Startup

- Main entry point: `main()`
- A dedicated **async event loop** is created for the WebSocket server
- The following components run in parallel:
  - Flask server on port `8889`
  - WebSocket server on port `8888`
  - Background task `update_offline_status`, which marks PCs as offline if inactive for over 1 minute

---

## 🖥️ Admin Panel

### 🔐 Authentication

- Path: `/login`
- Method: `POST`
- Inputs: `username`, `password`
- On success: redirect to `/dashboard`

---

### 📊 Dashboard (`/dashboard`)

- Displays a list of all clients from the database
- Shows:
  - IP addresses (local & public)
  - Online/offline status
  - CPU and RAM usage
  - Uptime, user, hostname, etc.

---

### 📤 Command Dispatch

- API: `POST /api/send_command`
- Payload format:

```json
{
  "pc_name": "name_of_PC",
  "command": "shell_command_to_execute"
}
