# 💬 Socket Chat Server

A minimal Node.js backend that delivers real time group chat with plain WebSockets through **Socket IO** and serves a light front-end from the **public** folder.

---

## ✨ What it does
- **Live messaging** &nbsp;•&nbsp; instant broadcast of chat text to everyone connected  
- **Online users counter** &nbsp;•&nbsp; shows how many clients are active at any moment  
- **Typing feedback** &nbsp;•&nbsp; broadcasts “Someone is typing…” signals  
- **Single endpoint** &nbsp;•&nbsp; just open `public/index.html` and start chatting  

---

## 🏗️ Tech stack

| Layer | Library |
|-------|---------|
| Server | Node.js 18 + |
| HTTP | Express |
| WebSocket | Socket IO |
| Static assets | Served from `/public` |

---

## 🚀 Quick start

1. **Clone and install**

   ```bash
   git clone https://github.com/<your-handle>/socket-chat-server.git
   cd socket-chat-server
   npm install

2. **Run the server**
   
npm start               # starts on http://localhost:4000

3. **Open the chat**

Visit http://localhost:4000 in two or more browser tabs and watch messages sync instantly.

API events
Direction	Event name	Payload	Description
server ➜ all	clients-total	number	Emits the current connected count
client ➜ server	message	{ username, text, time }	Send a chat line
server ➜ others	chat-message	same object	Broadcast a new chat line
client ➜ server	feedback	{ username, typing }	Notify typing status
server ➜ others	feedback	same object	Forward typing status

All events travel over the same Socket IO connection that is opened when the page loads.


## Deployment
The app is completely self contained. Point any cloud platform (Render, Railway, Fly.io, etc.) at npm start and expose either port 4000 or the $PORT environment variable supplied by the platform.


