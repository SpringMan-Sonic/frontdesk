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


