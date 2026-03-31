# 🤖 Gemini AI Chatbot

![Spring Boot](https://img.shields.io/badge/Spring_Boot-6DB33F?style=for-the-badge&logo=spring-boot&logoColor=white)
![Java](https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)
![WebSocket](https://img.shields.io/badge/WebSocket-010101?style=for-the-badge&logo=socketdotio&logoColor=white)
![Gemini AI](https://img.shields.io/badge/Gemini_AI-4285F4?style=for-the-badge&logo=google&logoColor=white)
![Railway](https://img.shields.io/badge/Railway-0B0D0E?style=for-the-badge&logo=railway&logoColor=white)
![GitHub Pages](https://img.shields.io/badge/GitHub_Pages-222222?style=for-the-badge&logo=github&logoColor=white)

A full-stack real-time AI chatbot powered by **Google Gemini 1.5 Flash**, built with a **Spring Boot WebSocket backend** and a sleek dark-themed frontend — deployed live on Railway + GitHub Pages.

---

## 🌐 Live Demo

🔗 **[rishabhshahwal.github.io/Chat_Bot_UI](https://rishabhshahwal.github.io/Chat_Bot_UI)**

---

## 📸 Screenshots

> Add your screenshots in a `/screenshots` folder in this repo and update the paths below.

| Welcome Screen | Chat in Action |
|---|---|
| <img width="1919" height="907" alt="welcome png" src="https://github.com/user-attachments/assets/9d8bdf87-b7dd-44be-9d0a-5dcf79831bb6" />
 | <img width="1919" height="904" alt="chat png" src="https://github.com/user-attachments/assets/a701b22c-eb6b-4fc6-8876-c256c3fd951f" />
 |

---

## ✨ Features

- 💬 Real-time chat using **WebSocket** (no page refresh needed)
- 🤖 Powered by **Google Gemini 1.5 Flash** API
- 🎨 Beautiful dark UI with gradient accents
- ⚡ Quick-action chips for instant prompts
- 🔄 Auto-reconnect if connection drops
- 🟢 Live connection status indicator
- 📝 Chat history in sidebar
- 📱 Responsive design

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Frontend | HTML, CSS, JavaScript (Vanilla) |
| Backend | Java, Spring Boot |
| Communication | WebSocket (`spring-websocket`) |
| AI Model | Google Gemini 1.5 Flash |
| Backend Hosting | Railway |
| Frontend Hosting | GitHub Pages |

---

## 🚀 Run Locally

### Prerequisites
- Java 17+
- Maven
- A Google Gemini API key → [Get one here](https://aistudio.google.com/app/apikey)

### 1. Clone the backend repo

```bash
git clone https://github.com/rishabhshahwal/ChatBot-Backend.git
cd ChatBot-Backend
```

### 2. Add your Gemini API key

Open `src/main/resources/application.properties` and add:

```properties
server.port=8080
gemini.api.key=YOUR_GEMINI_API_KEY_HERE
```

### 3. Run the Spring Boot backend

```bash
mvn spring-boot:run
```

Backend starts at `http://localhost:8080`
WebSocket available at `ws://localhost:8080/chat`

### 4. Open the frontend

```bash
git clone https://github.com/rishabhshahwal/Chat_Bot_UI.git
cd Chat_Bot_UI
```

Open `index.html` directly in your browser — it auto-connects to `localhost:8080` when running locally.

---

## 📁 Project Structure

```
ChatBot-Backend/
├── src/main/java/com/cfs/ChatBot/
│   ├── controller/
│   │   └── GemeniWebSocketHandler.java   # Handles WS messages & calls Gemini
│   ├── config/
│   │   └── WebSocketConfig.java          # Registers /chat WebSocket endpoint
│   └── ChatBotApplication.java
└── src/main/resources/
    └── application.properties

Chat_Bot_UI/
└── index.html                            # Full frontend (UI + WebSocket client)
```

---

## ⚙️ How It Works

```
Browser (index.html)
    │
    │  wss://chatbotbackend-production-0075.up.railway.app/chat
    │
Spring Boot (WebSocketConfig → /chat)
    │
    └── GemeniWebSocketHandler
            │
            └── POST https://generativelanguage.googleapis.com/...
                        │
                   Gemini 1.5 Flash
                        │
              Response → WebSocket → Browser
```

---

## 🔑 Environment Variables (Railway)

| Variable | Description |
|---|---|
| `GEMINI_API_KEY` | Your Google Gemini API key |
| `PORT` | Auto-set by Railway |

---

## 👤 Author

**Rishabh Shahwal**
- GitHub: [@rishabhshahwal](https://github.com/rishabhshahwal)

---

## ⭐ Show Your Support

If you like this project, please give it a **star ⭐** on GitHub!
