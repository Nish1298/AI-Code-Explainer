# 🤖 AI Code Explainer

An AI-powered fullstack platform that explains complex code in simplified **English** and **Hindi**. Built with React, Express, and Google Gemini AI.

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Node](https://img.shields.io/badge/node-18%2B-green.svg)
![React](https://img.shields.io/badge/react-18-61dafb.svg)

## ✨ Features

- 🖥️ **Monaco Code Editor** — VS Code-quality syntax highlighting and editing
- 🤖 **AI-Powered Explanations** — Powered by Google Gemini AI
- 🌐 **Bilingual Support** — Get explanations in English 🇬🇧 or Hindi 🇮🇳
- 📊 **Depth Control** — Choose Beginner, Intermediate, or Advanced explanations
- 💬 **Chatbot Mode** — Ask follow-up questions about your code
- 🎨 **Dark/Light Theme** — Beautiful UI with theme toggle
- 📱 **Responsive Design** — Works on mobile, tablet, and desktop
- 📋 **History** — Recent explanations saved locally
- 🔗 **Chatbot-Ready API** — RESTful API that can be integrated into any chatbot

## 🚀 Quick Start

### Prerequisites

- [Node.js](https://nodejs.org/) v18 or higher
- [Google Gemini API Key](https://aistudio.google.com/) (free tier available)

### Installation

```bash
# Clone the repo
git clone <your-repo-url>
cd ai-code-explainer

# Install all dependencies
npm run install-all
```

### Configuration

```bash
# Create your environment file
cp server/.env.example server/.env

# Add your Gemini API key to server/.env
GEMINI_API_KEY=your_actual_api_key_here
```

### Run the App

```bash
# Start both frontend and backend
npm run dev
```

- Frontend: http://localhost:3000
- Backend API: http://localhost:5000

## 📡 API Endpoints

### POST `/api/explain`

Explain a piece of code.

```json
{
  "code": "def fibonacci(n):\n    if n <= 1:\n        return n\n    return fibonacci(n-1) + fibonacci(n-2)",
  "language": "Python",
  "outputLanguage": "en",
  "depth": "beginner"
}
```

**Response:**
```json
{
  "success": true,
  "explanation": "## Summary\nThis code defines a recursive function..."
}
```

### POST `/api/chat`

Chat about previously explained code.

```json
{
  "message": "How can I optimize this?",
  "code": "def fibonacci(n): ...",
  "history": [
    { "role": "user", "content": "What does this do?" },
    { "role": "assistant", "content": "This function calculates..." }
  ]
}
```

### GET `/api/health`

Health check endpoint.

## 🏗️ Tech Stack

| Layer | Technology |
|-------|-----------|
| Frontend | React 18 + Vite |
| Styling | Tailwind CSS |
| Code Editor | Monaco Editor |
| Backend | Node.js + Express |
| AI Engine | Google Gemini AI |

## 📁 Project Structure

```
ai-code-explainer/
├── package.json          # Monorepo scripts
├── server/
│   ├── index.js          # Express server
│   ├── services/
│   │   └── geminiService.js  # AI integration
│   └── middleware/
│       └── rateLimiter.js
└── client/
    ├── src/
    │   ├── App.jsx           # Main layout
    │   ├── components/       # UI components
    │   ├── context/          # React Context
    │   ├── hooks/            # Custom hooks
    │   └── services/         # API layer
    └── index.html
```

## 🤝 Chatbot Integration

The `/api/explain` and `/api/chat` endpoints are designed to be easily integrated into any chatbot platform (Telegram, Discord, Slack, WhatsApp). Simply make HTTP requests to these endpoints from your bot.

## 📄 License

MIT License — feel free to use, modify, and distribute.
