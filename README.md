# AI Scam Shield
### A Bangla-First Scam Detection and Awareness Training Platform

AI Scam Shield is a web application designed to help people in Bangladesh identify suspicious messages, links, and phone numbers and learn how to protect themselves from online scams.

The platform provides AI-powered scam detection, risk assessment, red-flag explanations, recommended safety actions, and an interactive AI Scam Trainer featuring realistic Bangladeshi scam scenarios.

**Course:** CSE 4104 – Software Development III  
**Institution:** Northern University of Business & Technology, Khulna  
**Department:** Computer Science & Engineering

---

## 1. Team Information

| Field        | Details                                                 |
|--------------|---------------------------------------------------------|
| Team         | CSE4104-7C-T08                                          |
| Section      | 7C                                                      |
| Course       | CSE 4104 – Software Development III                     |
| Submitted To | Md. Riaz Mahmud, Assistant Professor, Department of CSE |

### Team Members

| Member            | Role        | Responsibility                  |
|-------------------|-------------|---------------------------------|
| Shariya Akter     | Team Leader | AI Integration and Coordination |
| Samanta Rahman    | Team Member | Frontend Development            |
| Suraya Akter Ritu | Team Member | Backend and Database            |

---

## 2. Problem Statement

Mobile financial services such as bKash, Nagad, and Rocket are widely used in Bangladesh. However, users increasingly face fraudulent activities, including fake OTP requests, phishing links, prize messages, fake job offers, and impersonation calls.

Existing solutions often lack Bangla and Banglish language support, clear explanations of scam detection results, and practical awareness training.

AI Scam Shield aims to address these limitations through an accessible, Bangla-first platform.

## 3. Project Objectives

- Detect suspicious messages, links, and phone numbers.
- Provide clear risk levels and risk scores.
- Explain detected red flags in simple language.
- Recommend appropriate safety actions.
- Provide AI-based scam awareness training.
- Maintain scan history and training progress.
- Allow users to report new scams.
- Enable administrators to review reported scams and manage educational content.

## 4. Key Features

| Feature            | Description                                             |
|--------------------|---------------------------------------------------------|
| Authentication     | Secure registration and login using JWT and bcrypt.     |
| Scam Checker       | Analyze messages, links, and phone numbers.             |
| AI Scam Trainer    | Interactive scam simulation with feedback and scores.   |
| Dashboard          | Display scan history, training history, and progress.   |
| Scam Report System | Allow users to submit suspicious scam reports.          |
| Scam Library       | Provide educational guides about common scams.          |
| Admin Panel        | Manage reports, scenarios, guides, and statistics.      |
| Optional OCR       | Extract text from uploaded screenshots if time permits. |

## 5. Technology Stack

|       Layer         |      Technology           |
|---------------------|---------------------------|
| Frontend            | React.js, CSS, Axios      |
| Backend             | Node.js, Express.js       |
| Database            | PostgreSQL (Supabase)     |
| Authentication      | JWT, bcrypt               |
| AI Integration      | Gemini or OpenAI API      |
| AI Experiments      | Hugging Face Transformers |
| Version Control     | Git, GitHub               |
|     Testing         | Jest, Postman             |
| Frontend Deployment | Vercel                    |
| Backend Deployment  | Render                    |
| Database Hosting    | Supabase                  |

## 6. System Architecture

The system follows a client-server architecture.

**Main Components:**

1. Frontend – React.js user interface.
2. Backend – Node.js and Express.js REST API.
3. Database – PostgreSQL for persistent data storage.
4. AI Services – Gemini or OpenAI API for scam analysis and training.

**Communication Flow:**

```text
User
  |
  v
Frontend (React.js)
  |
  v
Backend API (Node.js + Express.js)
  |
  +------> PostgreSQL Database
  |
  +------> AI Services (Gemini / OpenAI)
  |
  v
Analysis Result
  |
  v
Frontend Display
```

AI API keys and database credentials are stored securely as backend environment variables.

## 7. Database Design

The system uses PostgreSQL as its relational database.

The database design supports:

- User authentication and role management.
- Scam scan records and analysis results.
- AI training sessions and scores.
- User-submitted scam reports.
- Scam training scenarios.
- Educational library content.

Primary keys, foreign keys, attributes, and relationships are documented in the ER Diagram.

## 8. API Design

The backend provides RESTful API endpoints for communication between the frontend, database, and AI services.

### Authentication APIs

| Method |      Endpoint        |     Purpose         |
|--------|----------------------|---------------------|
| POST   | `/api/auth/register` | Register a new user |
| POST   | `/api/auth/login`    | Authenticate a user |
| POST   | `/api/auth/logout`   | Log out a user      |

### User APIs

| Method |       Endpoint       |      Purpose          |
|--------|----------------------|-----------------------|
| GET    | `/api/users/profile` | Retrieve user profile |
| PUT    | `/api/users/profile` | Update user profile   |

### Scam Checker APIs

| Method |      Endpoint        |                Purpose                               |
|--------|----------------------|------------------------------------------------------|
| POST   | `/api/scans/analyze` | Analyze suspicious messages, links, or phone numbers |
| GET    | `/api/scans/history` | Retrieve previous scan records                       |
| GET    | `/api/scans/:id`     | Retrieve a specific scan result                      |

### AI Scam Trainer APIs

| Method |      Endpoint            |              Purpose                     |
|--------|--------------------------|------------------------------------------|
| GET    | `/api/trainer/scenarios` | Retrieve available training scenarios    |
| POST   | `/api/trainer/start`     | Start a training session                 |
| POST   | `/api/trainer/chat`      | Send a message during AI simulation      |
| POST   | `/api/trainer/complete`  | Complete a session and generate feedback |

### Scam Report APIs

| Method |     Endpoint              |                Purpose                     |
|--------|---------------------------|--------------------------------------------|
| POST   | `/api/reports`            | Submit a scam report                       |
| GET    | `/api/reports`            | Retrieve reports for administrative review |
| PUT    | `/api/reports/:id/status` | Update report status                       |

### Dashboard and Admin APIs

| Method |      Endpoint           |            Purpose                 |
|--------|-------------------------|------------------------------------|
| GET    | `/api/dashboard`        | Retrieve dashboard information     |
| GET    | `/api/admin/statistics` | Retrieve administrative statistics |
| POST   | `/api/admin/scenarios`  | Create training scenarios          |
| POST   | `/api/admin/library`    | Add educational content            |

**Note:** These are planned API endpoints. Request formats, validation rules, authentication requirements, and response structures will be finalized during implementation.

## 9. AI Integration Workflow

AI integration is a core component of AI Scam Shield.

**AI Service:** Google Gemini or OpenAI API (final selection during implementation).

### Scam Detection Workflow

```text
User Enters Suspicious Content
          |
          v
Frontend Sends Request
          |
          v
Backend API
          |
          v
AI Service (Gemini / OpenAI)
          |
          v
Scam Analysis
          |
          v
Risk Level + Risk Score
+ Red Flags + Safety Advice
          |
          v
Frontend Displays Result
```

### AI Input

- Suspicious message or text.
- Link or phone number.
- Relevant context for analysis.

### AI Output

- Risk classification: Safe, Suspicious, or Scam.
- Risk score.
- Identified red flags.
- Recommended safety actions.

### Why AI Is Needed

AI helps analyze different writing styles, Bangla and Banglish expressions, suspicious requests, and contextual scam patterns.

It also powers realistic scam simulation and provides feedback to improve users' awareness.

All AI requests are processed through the backend to protect API credentials.

## 10. Repository Structure

```text
cse4104-7c-t08-ai-scam-shield/
│
├── frontend/
│
├── backend/
│
├── database/
│
├── diagrams/
│
├── documentation/
│   ├── CSE4104-7C-T08_Proposal.pdf
│   ├── CSE4104-7C-T08_SRS.pdf
│   └── CSE4104-7C-T08_SystemDesign.pdf
│
├── .gitignore
│
└── README.md
```

## 11. Branch Strategy

|     Branch       |          Purpose                       |
|------------------|----------------------------------------|
| `main`           | Stable project version                 |
| `development`    | Integration of completed features      |
| `frontend`       | Frontend development                   |
| `backend`        | Backend and database development       |
| `ai-integration` | AI Scam Checker and Trainer development|

Team members contribute through commits and pull requests.

## 12. Project Development Plan

|  Phase  | Weeks |              Planned Work                          |
|---------|-------|----------------------------------------------------|
| Phase 1 | 1–2   | Team formation, project proposal, repository setup |
| Phase 2 | 3–4   | SRS, diagrams, API design, AI workflow             |
| Phase 3 | 5–7   | Authentication, database, Scam Checker             |
| Phase 4 | 8–10  | AI Scam Trainer, scoring, dashboard                |
| Phase 5 | 11–12 | Admin panel, scam reports, scam library            |
| Phase 6 | 13–14 | Testing, deployment, final documentation           |

## 13. Documentation

The project documentation is maintained in the `documentation/` directory.

|            Document                |            File                      |
|------------------------------------|--------------------------------------|
| Project Proposal                   | `CSE4104-7C-T08_Proposal.pdf`        |
| Software Requirement Specification | `CSE4104-7C-T08_SRS.pdf`             |
| System Design Document             | `CSE4104-7C-T08_SystemDesign.pdf`    |

The `diagrams/` directory maintains individual project diagrams and related design resources.

## 14. Security Considerations

- Passwords are hashed using bcrypt.
- JWT is used for authentication.
- Role-based access control separates user and administrator permissions.
- AI API keys and database credentials remain on the backend.
- Sensitive information such as real OTPs and PINs should never be submitted.
- User input must be validated before processing.

## 15. Disclaimer

AI Scam Shield provides advisory scam detection results for awareness and educational purposes only. Users should verify suspicious messages through official service channels.

Never share your real OTP, PIN, or password with anyone, including this application.

## 16. Future Improvements

- Screenshot-based scam detection using OCR.
- Improved Bangla and Banglish language processing.
- More local scam training scenarios.
- Enhanced scam pattern detection.
- Additional security and performance improvements.

---

**Project:** AI Scam Shield  
**Team:** CSE4104-7C-T08  
**Institution:** Northern University of Business & Technology, Khulna  
**Department:** Computer Science & Engineering
