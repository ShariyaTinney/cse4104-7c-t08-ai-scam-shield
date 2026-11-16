# AI Scam Shield

**A Bangla-First Scam Detection and Awareness Training Platform**

AI Scam Shield is a web application that helps people in Bangladesh check suspicious messages, links and phone numbers, and learn how to resist scams. Users receive a clear risk level with the red flags found and simple advice, and they can practise against an AI "scammer" in realistic local scenarios such as a fake bKash agent, a prize message or a fake job offer.

> Course project for **CSE 4104 – Software Development III**
> Northern University of Business & Technology, Khulna | Department of Computer Science & Engineering

---

## Team Information

| Field        |               Details                              |
|--------------|----------------------------------------------------|
| Team         | CSE4104-7C-T08                                     |
| Section      | 7C                                                 |
| Course       | CSE 4104 – Software Development III                |
| Submitted to | Md. Riaz Mahmud, Assistant Professor, Dept. of CSE |


|    Member         |     Role            |      Responsibility             |
| ------------------|---------------------|---------------------------------|
| Shariya Akter     | Team Leader         | AI integration and coordination |
| Samanta Rahman    | Team Member         | Frontend                        |
| Suraya Akter Ritu | Team Member         | Backend and database            |

Every member contributes to the repository.

---

## Problem

Mobile financial services such as bKash, Nagad and Rocket are used by millions of people in Bangladesh, and fraud has grown with them. Common attacks include fake OTP or PIN requests, prize SMS, phishing links, fake job offers and fake customer-care calls. Existing tools mostly rely on phone numbers or generic spam patterns, do not understand Bangla or Banglish messages, give no explanation for their verdict, and do not teach users how to respond.

## Objectives

- Build a Bangla-first system that checks suspicious messages, links and phone numbers and returns a clear risk level.
- Explain every verdict in simple language, with the red flags found and the next steps the user should take.
- Provide an AI Scam Trainer for safe, scenario-based practice against simulated scams.
- Track each user's scans and training scores so improvement is visible over time.
- Let users report new scams and let an administrator review them, so the system keeps up with new scam patterns.
- Improve scam awareness among everyday users, students and elderly people.

## Features

|      Feature       |                                                               Description                                                                                                             |
|--------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Authentication     | User registration and login using JWT, with passwords hashed using bcrypt. Role-based access (User, Admin).                                                                           |
| Scam Checker       | Paste a message, link or phone number. The system returns Safe / Suspicious / Scam, a risk score, the red flags found and recommended actions. Works in Bangla, English and Banglish. |
| AI Scam Trainer    | Scenario-based role-play where the AI plays a scammer. The user receives feedback and a score at the end.                                                                             |
| Dashboard          | Scan history, training history, scores and a progress chart.                                                                                                                          |
| Scam Report System | Users report new scam messages. Admins review them (Pending / Approved / Rejected).                                                                                                   |
| Scam Library       | Short guides on common scam types and how to avoid them.                                                                                                                              |
| Admin Panel        | Manage training scenarios and library guides, review reported scams and view basic statistics.                                                                                        |
| Optional           | Screenshot upload with OCR to extract message text (only if time allows).                                                                                                             |

## Technology Stack

| Layer           |                  Technology                              |
|-----------------|----------------------------------------------------------|
| Frontend        | React.js, CSS, Axios                                     |
| Backend         | Node.js, Express.js                                      |
| Database        | PostgreSQL (hosted on Supabase)                          |
| Authentication  | JWT, bcrypt                                              |
| AI integration  | Gemini or OpenAI API (called only from the backend)      |
| AI experiments  | Hugging Face (Transformers)                              |
| Version control | Git, GitHub                                              |
| Testing         | Jest, Postman                                            |
| Deployment      | Vercel (frontend), Render (backend), Supabase (database) |
| Documentation   | Markdown README, Google Docs                             |

## System Architecture

```
Users (browser)  →  Frontend (React)  →  Backend API (Node.js + Express)  →  Database (PostgreSQL)
                                                      ↓
                                                AI Services (Gemini / OpenAI)
```

The AI API keys and database credentials stay on the backend as environment variables and are never exposed to the browser. See `docs/CSE4104-7C-T08_ArchitectureDiagram.pdf` for the full diagram.

## Repository Structure

```
cse4104-7c-t08-ai-scam-shield/
├── frontend/     # React application (pages, components, API calls)
├── backend/      # Node.js + Express API (routes, controllers, AI module, database access)
├── docs/         # Project documents and diagrams
│   ├── CSE4104-7C-T08_Proposal.pdf
│   ├── CSE4104-7C-T08_SRS.pdf
│   ├── CSE4104-7C-T08_UseCaseDiagram.pdf
│   ├── CSE4104-7C-T08_ERDiagram.pdf
│   └── CSE4104-7C-T08_ArchitectureDiagram.pdf
└── README.md
```

### Branches

|      Branch      |         Purpose                  |
|------------------|----------------------------------|
| `main`           | Stable, working version          |
| `development`    | Integration of finished features |
| `frontend`       | Frontend work                    |
| `backend`        | Backend and database work        |
| `ai-integration` | AI Scam Checker and Trainer work |

Every member contributes through commits and pull requests.

## Documentation

- **SRS:** `docs/CSE4104-7C-T08_SRS.pdf` (functional requirements FR-01 to FR-37, non-functional requirements NFR-01 to NFR-29, user roles and 14 use cases)
- **Use Case Diagram:** `docs/CSE4104-7C-T08_UseCaseDiagram.pdf`
- **ER Diagram:** `docs/CSE4104-7C-T08_ERDiagram.pdf`
- **Architecture Diagram:** `docs/CSE4104-7C-T08_ArchitectureDiagram.pdf`

## Project Plan

| Phase | Weeks |                       Planned work                                     |
|-------|-------|------------------------------------------------------------------------|
|   1   | 1–2   | Team formation, idea, proposal, repository setup, sample scam messages |
|   2   | 3–4   | SRS, ER diagram, wireframes, API design, AI model and prompt design    |
|   3   | 5–7   | Authentication, database setup, Scam Checker                           |
|   4   | 8–10  | AI Scam Trainer, scoring, dashboard and history                        |
|   5   | 11–12 | Admin panel, scam reports, scam library, optional OCR                  |
|   6   | 13–14 | Testing, deployment, final documentation and presentation              |

This is an initial plan and will be adjusted to the official course timeline.

## Disclaimer

AI Scam Shield gives advisory results only. Always verify suspicious messages with the official service (for example the bKash or Nagad helpline). Never share your real OTP, PIN or password with anyone, including this application.
