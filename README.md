<div align="center">
  <img width="100%" src="https://capsule-render.vercel.app/api?type=waving&color=0:042f2e,35:0f766e,70:14b8a6,100:99f6e4&height=190&section=header&text=Sahayi&fontSize=68&fontColor=ffffff&animation=twinkling&fontAlignY=36&desc=Voice-first%20health%20support%20in%20Malayalam%20and%20English.&descAlignY=58&descSize=16" alt="Sahayi animated header" />

  <p>
    <img src="https://img.shields.io/badge/API-FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white" alt="FastAPI" />
    <img src="https://img.shields.io/badge/Voice-Twilio-F22F46?style=for-the-badge&logo=twilio&logoColor=white" alt="Twilio" />
    <img src="https://img.shields.io/badge/Language-Sarvam%20AI-0F766E?style=for-the-badge" alt="Sarvam AI" />
    <a href="LICENSE"><img src="https://img.shields.io/badge/License-MIT-99F6E4?style=for-the-badge" alt="MIT License" /></a>
  </p>
</div>

## â˜Žï¸ What it is

Sahayi is a voice-first health-companion prototype built around phone calls and Indic-language speech. Its backend connects telephony, speech recognition and synthesis, conversation orchestration, retrieval, and a browser dashboard.

<p align="center"><img src="sahayi_flow.svg" width="92%" alt="Sahayi call-processing flow" /></p>

## ðŸ”„ Call path

```mermaid
flowchart LR
  A[Twilio call] --> B[Speech input]
  B --> C[Signal and safety checks]
  C --> D[Conversation agents and retrieval]
  D --> E[Speech response]
  C --> F[Escalation path]
  D --> G[Dashboard and session record]
```

## ðŸ§° Stack

| Area | Tools |
|---|---|
| Backend | Python, FastAPI, SQLAlchemy, SQLite, WebSockets |
| Telephony | Twilio Voice |
| Speech | Sarvam AI integrations |
| Models | Google Gemini and configured model clients |
| Retrieval | ChromaDB, sentence-transformers, PubMed E-utilities |
| Dashboard | React, Vite, Firebase Auth |

## ðŸš€ Run the components

Backend:

```bash
git clone https://github.com/ChristopherJoshy/Sahayi.git
cd sahayi/sahayi/backend
python -m venv .venv
# Windows: .venv\Scripts\Activate.ps1
# macOS/Linux: source .venv/bin/activate
pip install -r requirements.txt
Copy-Item .env.example .env  # PowerShell; use cp on macOS/Linux
uvicorn main:app --reload
```

Frontend, in another terminal:

```bash
cd sahayi/sahayi/frontend
npm install
npm run dev
```

Configure Twilio, Sarvam, model, database, and Firebase values locally. Do not put provider credentials in source control.

## ðŸ—‚ï¸ Layout

```text
sahayi/backend/   API, call handling, agents, retrieval and safety logic
sahayi/frontend/  dashboard and session views
sahayi_flow.svg   high-level call flow
```

## ðŸ“„ License

MIT. See [`LICENSE`](LICENSE).

## âš ï¸ Scope

This prototype is not a diagnostic or emergency-response service. It has not been clinically validated. Call recordings and health details are sensitive; use synthetic data for development and require qualified review before any real-world deployment.