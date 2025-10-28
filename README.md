# 🎙️ AI Voice Agent with Human-in-the-Loop Supervisor System

A **production-ready AI voice agent system** that handles customer calls, escalates unknown questions to human supervisors, and automatically learns from their responses — creating a self-improving, intelligent call-handling solution.

---

## 🌟 Core Capabilities

| Feature | Description |
|----------|-------------|
| 🎤 **Real-Time Voice Conversations** | Natural phone calls via LiveKit |
| 🤖 **AI-Powered Responses** | Instant and context-aware replies using Google Gemini AI |
| 📞 **Smart Escalation** | Auto-escalates unknown questions to human supervisors |
| 🧠 **Automatic Learning** | Learns new answers from supervisor responses |
| 📊 **Live Dashboard** | Manage help requests, view logs, and monitor analytics |
| 🔄 **Complete Workflow** | End-to-end: customer → AI → supervisor → knowledge update |
| 🌍 **Production Ready** | Scalable architecture with robust error handling |

---

## 🧱 Architecture

```text
┌─────────────────────────────────────────────────────────────────┐
│ Customer Interface                                              │
│ Phone Call → LiveKit → Voice Agent → Backend API → AI Response  │
└─────────────────────────────────────────────────────────────────┘
↓
┌─────────────────────────────────────────────────────────────────┐
│ Processing Pipeline                                              │
│ 1. Speech-to-Text (OpenAI Whisper)                              │
│ 2. Knowledge Base Search (Firebase)                             │
│ 3. AI Processing (Gemini AI)                                    │
│ 4. Escalation Detection (Pattern Matching)                      │
│ 5. Text-to-Speech (OpenAI TTS)                                  │
└─────────────────────────────────────────────────────────────────┘
↓
┌─────────────────────────────────────────────────────────────────┐
│ Human-in-the-Loop                                               │
│ Unknown Question → Help Request → Supervisor Dashboard          │
│ Supervisor Response → Knowledge Update → Customer Callback      │
│ Future Calls → AI Knows the Answer                              │
└─────────────────────────────────────────────────────────────────┘
↓
┌─────────────────────────────────────────────────────────────────┐
│ Data Flow Diagram                                               │
│ Customer → LiveKit → Python Agent → Node.js Backend             │
│ ↓                ↓                                              │
│ OpenAI API       Firebase Firestore                             │
│ ↓                ↓                                              │
│ Gemini AI        Knowledge Base                                 │
│ ↓                ↓                                              │
│ Supervisor Dashboard                                            │
└─────────────────────────────────────────────────────────────────┘
```

🛠️ Tech Stack
🧩 Backend (Node.js)

Express.js – REST API server

Firebase Admin SDK – Firestore database

Google Gemini AI – Natural language processing

LiveKit Server SDK – Token generation

UUID – Unique identifiers

🐍 Voice Agent (Python)

LiveKit Agents – Voice call handling

OpenAI Whisper – Speech-to-text

OpenAI TTS – Text-to-speech

OpenAI GPT-4o-mini – Language understanding

Aiohttp – Async HTTP client

💻 Frontend

Vanilla JavaScript – Lightweight and fast

Modern CSS – Responsive dashboard design

Fetch API – REST communication

☁️ Infrastructure

Firebase Firestore – Cloud NoSQL database

LiveKit Cloud – Real-time voice infrastructure

Google Cloud – AI services and hosting

📋 Prerequisites
🧰 Required Software

Node.js ≥ 18.0.0

Python ≥ 3.11

npm and pip installed

🔑 Required Accounts (Free tiers available)

Firebase – Firestore database

Google AI Studio – Gemini API

LiveKit – Voice infrastructure

OpenAI – Voice + AI services

Deepgram – Speech recognition (optional)

Cartesia – Voice synthesis (optional)

🚀 Installation Guide
Step 1: Clone the Repository
# Create project directory
mkdir FRONTDESK
cd FRONTDESK

Step 2: Setup Backend (Node.js)
# Create folder structure
mkdir -p backend/src/{config,services}
mkdir -p backend/public


cat > backend/package.json << 'EOF'
{
  "name": "Frontdesk",
  "version": "1.0.0",
  "description": "Backend API for AI Agent Supervisor System",
  "main": "src/server.js",
  "scripts": {
    "start": "node src/server.js",
    "dev": "nodemon src/server.js"
  },
  "dependencies": {
    "@google/generative-ai": "^0.21.0",
    "express": "^4.18.2",
    "cors": "^2.8.5",
    "dotenv": "^16.3.1",
    "firebase-admin": "^12.0.0",
    "body-parser": "^1.20.2",
    "uuid": "^9.0.1",
    "livekit-server-sdk": "^2.8.0"
  },
  "devDependencies": {
    "nodemon": "^3.0.2"
  }
}
EOF
# Install dependencies
cd backend
npm install

Step 3: Setup Voice Agent (Python)
cd ..
mkdir voice-agent
cd voice-agent

# Create virtual environment
python -m venv venv

# Activate environment
# Windows
venv\Scripts\activate
# Mac/Linux
source venv/bin/activate

# Create requirements.txt
cat > requirements.txt << 'EOF'
livekit~=1.0.17
livekit-agents==1.2.15
livekit-plugins-silero==1.2.15
python-dotenv==1.0.0
aiohttp~=3.10
google-generativeai
EOF

# Install dependencies
pip install -r requirements.txt

⚙️ Configuration
Step 1: Create .env for Backend
# Firebase Configuration
FIREBASE_PROJECT_ID=your-project-id
FIREBASE_PRIVATE_KEY="-----BEGIN PRIVATE KEY-----\nYour\nPrivate\nKey\nHere\n-----END PRIVATE KEY-----\n"
FIREBASE_CLIENT_EMAIL=firebase-adminsdk-xxxxx@your-project.iam.gserviceaccount.com

# Google Gemini Configuration
GEMINI_API_KEY=AIzaSyxxxxxxxxxxxxxxxxxx

# Server Configuration
PORT=3000
NODE_ENV=development

# Business Information
BUSINESS_NAME=Luxury Salon & Spa
BUSINESS_PHONE=+919876543210
SUPERVISOR_PHONE=+919876543210
SUPERVISOR_NAME=Your Name

Step 2: Create .env for Voice Agent
# LiveKit Configuration
LIVEKIT_URL=wss://your-project.livekit.cloud
LIVEKIT_API_KEY=APIxxxxxxxxx
LIVEKIT_API_SECRET=xxxxxxxxxxxxxxxx

# OpenAI Configuration
OPENAI_API_KEY=sk-proj-xxxxxxxxxxxxxxxxxx

# Backend API
BACKEND_API=http://localhost:3000/api

# Business Info
BUSINESS_NAME=Luxury Salon & Spa

🔥 Firestore Initialization

Go to Firebase Console → Firestore Database

Click "Create Database"

Select "Start in test mode"

Choose a region (e.g., asia-south1 for India)

Click Enable

Wait 2–3 minutes for activation

🎬 Running the System
Terminal 1 — Start Backend
cd backend
npm start


Expected Output:

✅ Firebase initialized successfully
✅ Knowledge base initialized
🚀 Backend API running at http://localhost:3000
📊 Dashboard: http://localhost:3000
🏢 Business: Luxury Salon & Spa

Terminal 2 — Start Voice Agent
cd voice-agent
# Activate environment
venv\Scripts\activate  # (Windows)
source venv/bin/activate  # (Mac/Linux)

# Start agent
python agent.py dev

Browser — Open Dashboard
http://localhost:3000


You’ll see the Supervisor Dashboard with:

⏳ Pending Requests

📜 History

📚 Knowledge Base

📊 Statistics

🧪 Testing
✅ Test 1: Known Question (No Escalation)
curl -X POST http://localhost:3000/api/process-message \
-H "Content-Type: application/json" \
-d '{ "message": "What are your hours?", "sessionId": "test-123", "callerInfo": {"name": "Test User", "phone": "+919999999999"} }'


Expected Response:

{
  "answer": "We are open Monday through Saturday from 9am to 7pm, and Sunday from 10am to 5pm.",
  "needsHelp": false,
  "confidence": 0.85,
  "source": "knowledge_base"
}

⚠️ Test 2: Unknown Question (Escalation)
curl -X POST http://localhost:3000/api/process-message \
-H "Content-Type: application/json" \
-d '{ "message": "Do you offer bridal packages?", "sessionId": "test-123", "callerInfo": {"name": "Priya Sharma", "phone": "+919876543210"} }'


Expected Response:

{
  "answer": "Let me check with my supervisor and get back to you shortly.",
  "needsHelp": true,
  "requestId": "abc-123-def-456",
  "confidence": 0,
  "source": "escalation"
}

🧑‍💼 Test 3: Supervisor Resolution Flow

Open the Dashboard → Pending Requests

Click Respond

Enter answer:
"Yes! We offer bridal packages starting at ₹15,000. Includes makeup, hair styling, and draping."

Click Submit

Terminal Output:

✅ Resolved help request
✅ Added new knowledge: "Do you offer bridal packages?"
📞 Simulated callback sent to customer


Now, re-test the same question — the AI should answer automatically!

📂 Project Structure
```

FRONTDESK/
│
├── backend/
│   ├── src/
│   │   ├── config/
│   │   ├── services/
│   │   └── server.js
│   ├── public/
│   ├── package.json
│   └── .env
│
├── voice-agent/
│   ├── agent.py
│   ├── requirements.txt
│   ├── venv/
│   └── .env
│
└── README.md
```






