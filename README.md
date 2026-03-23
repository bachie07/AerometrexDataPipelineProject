# Aerometrex Data Ingestion Pipeline

A secure customer data ingestion pipeline for Aerometrex's MetroMap platform.
Allows users to upload aerial imagery and have it processed and made available within MetroMap.

---

## Tech Stack
- **Frontend** — React
- **Backend** — Node.js + Express
- **Pipeline** — Python
- **Database** — PostgreSQL
- **Cloud** — AWS

---

## Prerequisites
Make sure you have these installed before getting started:

| Tool | Version | Download |
|------|---------|----------|
| Node.js | 18+ | https://nodejs.org |
| Python | 3.14+ | https://python.org |
| Git | Latest | https://git-scm.com |

---

## Getting Started

### 1. Clone the repo
```bash
git clone https://github.com/bachie07/AerometrexDataPipelineProject.git
cd AerometrexDataPipelineProject
```



**Windows:**
```bash
copy .env.example .env
```

Then fill in your values in the `.env` file. Ask your team lead for the actual values.

---

## Frontend Setup
```bash
cd frontend
npm install
npm start
```
Opens at **http://localhost:3000**

---

## Backend Setup
```bash
cd backend
npm install
npm start
```
Runs at **http://localhost:8000**

Test it works by opening **http://localhost:8000/health** in your browser.
You should see:
```json
{"status": "backend is running"}
```

⚠️ **Mac users:** If port 8000 is blocked, AirPlay may be using it.
Go to System Preferences → General → AirDrop & Handoff → turn off AirPlay Receiver.

---

## Pipeline Setup

**Mac/Linux:**
```bash
cd pipeline
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

**Windows:**
```bash
cd pipeline
python -m venv venv
venv\Scripts\activate
pip install -r requirements.txt
```

⚠️ **Pipeline is currently in early setup stage.**
More dependencies will be added when client provides sample datasets.

---

## Folder Structure
```
AerometrexDataPipeline/
    ├── /frontend        → React upload portal
    ├── /backend         → Node.js + Express server
    ├── /pipeline        → Python processing pipeline
    ├── /infrastructure  → AWS configuration
    ├── /docs            → Architecture diagrams and reports
    └── /tests           → Test files
```

---

## Branching Strategy
```
main        → stable, demo ready code only
dev         → integration branch, merge features here first
feature/xxx → individual features e.g. feature/upload-portal
fix/xxx     → bug fixes e.g. fix/validation-error
```

⚠️ Never push directly to `main`. Always go through `dev` first.

---

## Team
| Role | Name |
|------|------|
| Scrum Master | Gia |
| Product Owner | Nikola |

---

## Client Contact
**Primary:** Sam Holt — Aerometrex
**CC:** Daniel O'Donnell, James P.

> Please consolidate questions into one email before sending.

---

## Notes
- Never commit `.env` files
- Never commit `node_modules/`
- Never commit `venv/`
- Never commit imagery files (`.tif`, `.ecw`, `.jp2`)