# XAMPRO – Examination Management System

A comprehensive full-stack Examination Management System designed for autonomous colleges to digitize and automate the complete examination lifecycle.

---

> [!NOTE]
>
> This repository is a **public demonstration** of **XAMPRO**. It showcases the system architecture, technology stack, user interface, and selected implementation to demonstrate the project's design and development approach.
>
> The complete production version contains additional modules, advanced business logic, institution-specific configurations, security implementations, and other proprietary components that are intentionally excluded from this repository.
>
> The institution name, branding, academic information, logos, and sample data used throughout this demonstration are included solely for showcasing the application's functionality and user interface. They do **not** represent an official deployment, endorsement, partnership, or affiliation with any educational institution. All such information is used exclusively for demonstration and portfolio purposes.

---

# Overview

XAMPRO is a comprehensive Examination Management System developed to streamline and automate the complete examination process within autonomous higher education institutions.

The platform manages the entire examination lifecycle, from student registration and examination scheduling to hall ticket generation, seating arrangements, dummy numbering, valuation, mark entry, grade processing, result publication, and student services.

The system follows a modular architecture with secure role-based access control, RESTful APIs, and a scalable PostgreSQL database.

---

# Public Demonstration Scope

This repository demonstrates:

- Overall system architecture
- User interface design
- Project structure
- Core examination workflows
- Database design approach
- Technology stack
- Authentication flow
- REST API architecture
- Sample modules
- Development methodology

This repository intentionally excludes:

- Production business logic
- Institution-specific configurations
- Sensitive implementation details
- Complete backend services
- Production database
- Deployment configuration
- Security-related implementations
- Proprietary algorithms
- Advanced examination processing modules

---

# Tech Stack

| Layer | Technologies |
|--------|--------------|
| Frontend | React, TypeScript, Vite, Tailwind CSS, Radix UI, React Router |
| Backend | Node.js, Express.js, TypeScript |
| Database | PostgreSQL |
| Authentication | JWT, bcrypt |
| State Management | React Query |
| Forms | React Hook Form, Zod |
| Reports | jsPDF, html2canvas, JsBarcode |
| Charts | Recharts |
| Progressive Web App | Workbox |

---

# Architecture

```text
                  Browser (SPA)

             React Application

                    │

        Components → Services

                    │

          Repository Layer

                    │

            REST API Client

                    │

            Express REST API

                    │

 Controllers → Services → Repositories

                    │

 Authentication
 Authorization
 Rate Limiting
 Audit Logging

                    │

               PostgreSQL
```

---

# Project Structure

```text
apps/
├── client/
│   ├── api/
│   ├── components/
│   ├── config/
│   ├── hooks/
│   ├── pages/
│   ├── repositories/
│   ├── services/
│   └── utils/
│
└── api/
    ├── controllers/
    ├── database/
    ├── middleware/
    ├── routes/
    └── services/
```

---

# Screenshots

# XAMPRO – Examination Management System
 
A comprehensive digital platform designed for autonomous higher education institutions to automate the end-to-end examination lifecycle. The platform streamlines operations from student registration and examination scheduling to hall ticket generation, seating arrangements, dummy numbering, multi-phase valuation, mark entry, grade processing, and result publication.
 
---
 
## Features
 
### Admin / COE
 
**System & Master Data**
- Department, Program & Branch management with a hierarchical tree structure.
- Subject management with evaluation scheme linkage, credits, max marks, and category classification.
- Student biodata with automated registration and roll number generation.
- Staff management with login credentials and subject assignments.
- Configurable evaluation schemes with internal test conversion rules.
- Institutional settings with 100+ configurable parameters.
**Pre-Examination**
- Exam fee structure configuration.
- Nominal roll processing and official student rolls.
- Question paper code allocation.
- Exam timetable scheduling with FN/AN sessions.
- Automated hall seating arrangements.
- Practical allotment scheduling.
- Hall ticket generation and publication.
**Examination Operations**
- Exam attendance tracking.
- Dummy numbering system for answer script anonymization.
- Mark entry supporting total marks, question-wise, and non-letter grading.
- Multi-phase valuation with deviation-based moderation rules.
- Moderation eligibility analysis.
- Revaluation application and marks processing.
- Internal marks consolidation.
**Result Management**
- Result publication with configurable formats.
- Grade classifications for semester, final, and non-letter evaluations.
- Transfer and rejoin case evaluation.
- Transfer certificate generation.
**Administration**
- Role-based access control with granular menu-level permissions.
- Dashboard with analytics and enrollment trend charts.
- Staff privilege management.
- Holiday and working day calendar.
- System configuration panel.
### Internal Staff
 
Dashboard, assigned courses, student profiles, attendance management, COPO mapping, internal mark entry, question-wise mark entry, and question bank management.
 
### External Examiners
 
Register-numbered and dummy-numbered mark entry (total marks and question-wise).
 
### Student Portal
 
Profile dashboard, hall ticket download, attendance records, internal assessment marks, published results, exam registration, elective registration, and fee statements.
 
---
 
## Technology Stack
 
| Layer | Technologies | Purpose |
| :--- | :--- | :--- |
| **Frontend** | React 18, TypeScript 5 | UI framework |
| | Vite 5 + SWC | Build tool and compiler |
| | Tailwind CSS 3 + Radix UI | Styling and component library |
| | React Router v6 | Client-side routing |
| | Recharts | Data visualization |
| | jsPDF + html2canvas | PDF generation |
| | JsBarcode | Barcode rendering |
| | TanStack React Query | Server state management |
| | React Hook Form + Zod | Form validation |
| | PWA (Workbox) | Offline capabilities |
| **Backend** | Node.js + Express 4 | REST API server |
| | TypeScript | Type safety |
| | JWT + bcryptjs | Authentication and password hashing |
| | express-rate-limit | Rate limiting |
| | Multer | File upload handling |
| | JSZip | Batch export support |
| **Database** | PostgreSQL | Primary database |
| | pg (node-postgres) | Database driver with connection pooling |
| | SQL migrations | Schema versioning on server start |
 
---
 
## Architecture
 
```
                    Browser (SPA)
                         │
   React App → Service → Repository → ApiClient
                         │ HTTP
                         ▼
                Express REST API
        Routes → Controllers → PostgreSQL
        ┌─────────────────────────────┐
        │  Auth → Rate Limit → Audit  │
        └─────────────────────────────┘
                         │
                         ▼
                    PostgreSQL
```
 
### Project Structure
 
```text
apps/
├── client/ (Frontend src/)
│   ├── api/             # HTTP REST client
│   ├── components/      # Reusable UI components
│   ├── config/          # Route and privilege definitions
│   ├── hooks/           # Custom React hooks
│   ├── pages/           # Role-based page components
│   ├── repositories/    # Data access layer
│   ├── services/        # Business logic layer
│   └── utils/           # Academic utilities and helpers
│
└── api/ (Backend/)
    ├── controllers/     # Request handling and business logic
    ├── database/        # Connection pool and SQL migrations
    ├── middleware/      # Authentication, authorization, rate limiting
    └── routes/          # API route definitions
```
 
## Authentication
 
- Unified login supporting admin, staff, external examiner, and student roles.
- JWT-based sessions with per-role session tracking.
- Granular privilege control at the menu level.
## Public Demonstration Scope
 
This repository serves as a public demonstration of XAMPRO, showcasing system architecture, user interface design, core examination workflows, and the overall development approach. The complete production version contains additional advanced business logic, modules, institution-specific configurations, and proprietary components intentionally excluded from this public portfolio repository. All institution names, branding, logos, and sample data are used exclusively for demonstration purposes.
 
## Screenshots
 
The following screenshots demonstrate the primary user interfaces available in the public demonstration of XAMPRO.
 
---
 
## Role Selection
![Role Selection](screenshots/role-selection.png)
 
---
 
## Controller of Examination
 
### Login Page
![Login Page](screenshots/admin-login.png)
 
### Dashboard
![Dashboard](screenshots/admin-dashboard.png)
 
### Hall Ticket Generation
![Hall Ticket Generation](screenshots/hall-ticket-generation.png)
 
### Practical Examination Timetable
![Practical Examination Timetable](screenshots/practical-exam-timetable.png)
 
### Semester Marksheet Generation
![Semester Marksheet Generation](screenshots/semester-marksheet-generation.png)
 
### Moderation Eligibility Report
![Moderation Eligibility Report](screenshots/moderation-eligibility-report.png)
 
---
 
## Internal Staff
 
### Login Page
![Login Page](screenshots/internal-login.png)
 
### Dashboard
![Dashboard](screenshots/internal-dashboard.png)
 
### Student Profile Lookup
![Student Profile Lookup](screenshots/student-profile-lookup.png)
 
### Internal Mark Entry
![Internal Mark Entry](screenshots/internal-mark-entry.png)
 
---
 
## External Examiners
 
### Login Page
![Login Page](screenshots/external-login.png)
 
### Module Selection
![Module Selection](screenshots/external-module-selection.png)
 
### Dummy Number Mark Entry
![Dummy Number Mark Entry](screenshots/external-dummy-mark-entry.png)
 
---
 
## Student Portal
 
### Login Page
![Login Page](screenshots/student-login.png)
 
### Dashboard
![Dashboard](screenshots/student-dashboard.png)
 
### Hall Ticket
![Hall Ticket](screenshots/student-hall-ticket.png)
 
### End Semester Result
![End Semester Result](screenshots/student-endsem-result.png)
 
---
 

# Disclaimer

This repository is intended solely for portfolio and demonstration purposes.

The production version of XAMPRO includes additional modules, workflows, optimizations, institution-specific customizations, and proprietary implementations that are not included in this public repository.

---

# Author

**Adhil Fahim A**

GitHub: https://github.com/Adhil-fah
