# Chat Application Tutorial
Spring Boot + WebSocket + STOMP + Thymeleaf

A simple, real-time chat application built with Spring Boot on the back end and Thymeleaf + JavaScript on the front end. Uses WebSocket and the STOMP messaging protocol for bi-directional communication between clients and server.

# 🚀 Features
* Real-time messaging using WebSocket + STOMP
* Server-side: Spring Boot, Spring WebSocket, Spring Messaging
* Client-side: Thymeleaf templates + JavaScript (ES6), SockJS fallback, STOMP.js
* Clean UI using Bootstrap
* Simple architecture, ideal for learning or extending

# 🛠 Tech Stack

Backend (Server-Side):
* Spring Boot
* Spring WebSocket
* Spring Messaging (STOMP Protocol)
* Thymeleaf

Frontend (Client-Side):
* Thymeleaf
* JavaScript (ES6)
* SockJS
* STOMP.js
* HTML / CSS
* Bootstrap

# 📷 Screenshots
![image alt](https://github.com/patelaviral/Chat-Application/blob/e7ce1f9f0986b9325b8f07494e01cd6800ee57cb/realTime_chat_application.png)

# 📁 Project Structure
```
src/
 └── main/
     ├── java/
     │    └── com.example.chatapp/
     │         ├── controller/
     │         │     └── ChatController.java
     │         ├── config/
     │         │     └── WebSocketConfig.java
     │         └── model/
     │               └── ChatMessage.java
     └── resources/
         ├── templates/
         │     └── chat.html
         └── static/
               └── js/
                   └── chat.js
```

# ▶️ How to Run Locally

1. Clone the repository
```
git clone https://github.com/patelaviral/Chat-Application.git
cd Chat-Application
```

2. Build and run with Maven (or your preferred method)
```
mvn spring-boot:run
```

3. Open your browser and navigate to:
```
http://localhost:8080/chat
```
# 📡 WebSocket & Messaging Endpoints
Endpoint	              Description
/chat                   (GET)	Loads the chat UI template (via controller)
/chat                   (SockJS/WebSocket)	STOMP endpoint for WebSocket handshake
/app/sendMessage	      Client sends chat messages to this application prefix
/topic/messages	        Server broadcasts messages to this topic for subscribed clients
# 📖 How It Works

* The client loads chat.html and connects to the WebSocket endpoint /chat using SockJS + STOMP.
* When a user sends a message, the client sends it to /app/sendMessage.
* On the server side (ChatController), the message is processed and returned/broadcast to /topic/messages.
* All clients subscribed to /topic/messages receive the message instantly and render it in the UI.

# 🧪 Usage / Demo

* Open multiple browser windows or tabs to http://localhost:8080/chat.
* Type a message and hit send — you should see it appear in all clients in real time.
* No login or persistence implemented in the base version (can be added as an extension).

# 🔄 Extending & Customization Ideas
* Add user login and authentication
* Persist message history in a database
* Add rooms/channels (multiple topics)
* Private messaging (user-to-user)
* File or image attachments
* UI enhancements (avatars, notifications, typing indicator)
