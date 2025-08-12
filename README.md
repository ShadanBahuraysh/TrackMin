# 📌 TrackMin – Issue Tracking & Support System

> Cross‑platform issue tracking for fuel stations with a built‑in assistant (**PetroBot**) for troubleshooting and procedures.

## 📖 Overview
TrackMin streamlines reporting and resolving technical/operational issues across fuel stations. It includes a Flutter front end, a Python/Flask backend, and a built‑in chatbot (**PetroBot**) that answers common problems, guides procedures, and links to training materials. This repository contains **project documentation** only (README and optional images) — no private data or internal links.

## ✨ Key Features
- **Multi‑platform UI (Flutter)** – Mobile, web, and desktop.
- **Smart filters** – By status, severity, station, and date.
- **Auto‑escalation** – Time‑based escalation by severity during business hours.
- **Email updates** – Notify staff when statuses change.
- **Multi‑assignment** – Assign multiple employees to one issue.
- **Built‑in assistant (PetroBot)** – Answers FAQs, IT support, troubleshooting steps, and operations procedures.

## 🧠 PetroBot (Built‑in Assistant)
PetroBot helps staff resolve issues faster by providing **step‑by‑step fixes**, **IT tips**, and **standard operating procedures**.

### What PetroBot can do
- **Troubleshooting**: Maps common symptoms (e.g., “pump out of order”, “MPOS not connecting”) to actionable steps.
- **IT Support**: Quick guides for Wi‑Fi, printer, PC, monitor, and switch‑port light issues.
- **Procedures**: Operational checklists (e.g., opening/closing shifts, cash management, deliveries).
- **Tutorial lookup**: Returns relevant training video titles (company-authenticated links only; not published here).

### Example API (for illustration)
> These examples document the **concept**. Endpoints and payloads may differ in your deployment. Replace host/paths as needed.

#### 1) Troubleshooting
```http
POST /chatbot
Content-Type: application/json

{
  "question": "The MPOS is not connecting to the network"
}
```
**Response**
```json
{
  "response": "Issue: MPOS Connection Issue ... Steps: 1) Open Firewall ... 2) Turn off options ... 3) Ensure MPOS is on Net-Fuel ..."
}
```

#### 2) IT Support
```http
POST /IT_Support
Content-Type: application/json

{
  "question": "My monitor is black"
}
```
**Response**
```json
{
  "response": "Monitor Troubleshooting ... 1) Ensure power on ... 2) Check HDMI/VGA ... 3) Try different port/cable ..."
}
```

#### 3) Standard Procedures
```http
POST /procedure_chatbot
Content-Type: application/json

{
  "question": "closing shift procedure"
}
```
**Response**
```json
{
  "response": "Issue: Proper Opening and Closing of Shift ... Steps: Take readings, reconcile MADA, issue change fund ..."
}
```

#### 4) Tutorial Lookup (titles only)
```http
GET /video?title=tutorial
```
**Response**
```json
{
  "found": true,
  "response": "Here’s a list of available tutorials: ..."
}
```

> 🔒 **Privacy**: Actual tutorial URLs and any internal systems are **not** included in this public documentation. Use company auth in production.

## 🏗 Architecture (High Level)
- **Frontend**: Flutter (cross-platform UI)
- **Backend**: Flask (Python) with scheduled tasks (APScheduler)
- **Database**: PostgreSQL
- **Notifications**: Email on status updates
- **Escalation**: Severity‑based timers within business hours (configurable)

## 📊 Dashboard Highlights
- Status bar for: Pending · In Progress · On Hold · Escalated · Resolved
- Counts auto‑update based on active filters (e.g., date range)
- Issue details page shows assignees, department, and update time

## 🖼 Screenshots (Optional)
Create a folder like `images/` and add safe demo screenshots:
```
images/dashboard.png
images/issue_details.png
images/filters.png
```
Then reference them in this README.

## 🚀 Roadmap
- AI‑assisted suggestions for root cause and fixes
- Live chat handoff to support agents
- Analytics for station performance trends

## ✅ Public Repo Checklist
- [x] No real names, emails, phone numbers, or station identifiers
- [x] No internal URLs, credentials, or API keys
- [x] Demo data only in screenshots
- [x] README explains features without exposing private info

## 📄 License & Attribution
This project was developed during a summer training initiative. All content here is for **demonstration/documentation** purposes only. Production code and private assets remain internal.

---

### How to use this README
- Create a new GitHub repo (public or private).
- Add this `README.md` and an `images/` folder (optional).
- Update endpoints and descriptions to reflect your deployment (without sharing private data).
