# 🧠 QuizForge — AI-Powered Quiz & Exam Preparation Platform

> **Turning study materials into smart quizzes — instantly.**

QuizForge is a web-based educational platform designed for teachers and students in Bangladesh. Teachers upload their own notes or PDFs, and the AI engine automatically generates multiple-choice, true/false, and short-answer questions from that content. Students take the quizzes, receive instant feedback, and track their performance over time — all in one place, in both **English and Bengali**.

This repository contains the **Software Requirements Engineering (SRE) document** for QuizForge, developed as a course project at **American International University-Bangladesh (AIUB)**, Department of Computer Science, Spring 2025–26.

---

## 📋 Table of Contents

- [Motivation](#-motivation)
- [Key Features](#-key-features)
- [System Architecture](#-system-architecture)
- [Tech Stack](#-tech-stack)
- [Getting Started](#-getting-started)
- [Usage](#-usage)
- [Project Structure](#-project-structure)
- [Team](#-team)

---

## 💡 Motivation

Over **40 million students** are enrolled in Bangladeshi educational institutions (BANBEIS, 2023), yet fewer than **5% have access to any AI-assisted or adaptive learning tool**. Traditional teaching relies almost entirely on manual lectures and printed tests, leaving students with no reliable way to self-assess before exams.

Meanwhile, teachers spend **5–8 hours per week** just writing quiz questions — time that could go toward teaching.

QuizForge was designed to solve both problems at once.

---

## ✨ Key Features

- **AI-Powered Quiz Generation** — Upload a PDF, DOCX, or plain-text file; the AI engine extracts key concepts and generates MCQ, True/False, and short-answer questions automatically.
- **Bilingual Support** — Full support for question generation and platform navigation in **English and Bengali**.
- **Role-Based Access** — Three distinct roles: `Admin`, `Teacher`, and `Student`, each with tailored dashboards and permissions.
- **Quiz Management** — Teachers can set time limits, difficulty levels, passing marks, quiz availability windows, and question shuffling.
- **Student Quiz Experience** — Countdown timer, immediate per-question feedback (optional), and a full answer-review mode after submission.
- **Performance Analytics** — Students see score trends and weak topics; teachers get class-level stats and exportable PDF/CSV reports.
- **Subscription & Payment** — Freemium model with Pro Teacher and Institution plans; payments via **bKash**, **Nagad**, and credit/debit card.
- **Secure Authentication** — JWT-based sessions, bcrypt password hashing, and email OTP for password recovery.

---

## 🏗️ System Architecture

QuizForge follows a three-tier architecture with an external AI engine integration:

```
┌─────────────────────────────────────────────────┐
│                  Client Layer                   │
│         React.js + Tailwind CSS (Web)           │
└────────────────────┬────────────────────────────┘
                     │ REST API (HTTPS)
┌────────────────────▼────────────────────────────┐
│                 Application Layer               │
│           Node.js + Express.js (API)            │
│   ┌───────────────────────────────────────┐     │
│   │  Auth │ Quiz CRUD │ Analytics │ Subs  │     │
│   └───────────────────────────────────────┘     │
└────┬──────────────────────────────┬─────────────┘
     │                              │
┌────▼─────────┐           ┌────────▼──────────┐
│  PostgreSQL  │           │  External Services│
│  + Redis     │           │  OpenAI GPT API   │
│  (DB/Cache)  │           │  bKash / SSLCommerz│
│  AWS S3      │           │  HuggingFace NLP  │
└──────────────┘           └───────────────────┘
```

### UML Diagrams (included in SRE document)

| Diagram | Description |
|---|---|
| **Use Case Diagram** | Actors: Admin, Teacher, Student, AI Engine (external), Payment GW (external) |
| **Activity Diagram** | Full teacher quiz-creation flow from login → AI generation → publish → student notification |
| **Class Diagram** | 8 core classes: `User`, `Teacher`, `Student`, `Quiz`, `Question`, `QuizAttempt`, `StudyMaterial`, `Subscription` |

---

## 🛠️ Tech Stack

| Layer | Technology | Purpose |
|---|---|---|
| **Frontend** | React.js + Tailwind CSS | Responsive, component-based UI |
| **Backend** | Node.js + Express.js | Scalable REST API |
| **Database** | PostgreSQL + Redis | Relational data + session caching |
| **File Storage** | AWS S3 / Cloudflare R2 | Secure PDF/DOCX storage |
| **Hosting** | AWS EC2 / DigitalOcean | Cloud deployment |
| **AI Engine** | OpenAI GPT-4 API / HuggingFace | NLP-based question generation |
| **Payments** | bKash PGW + SSLCommerz | Bangladesh-local payment support |
| **Auth** | JWT + bcrypt | Secure session and password management |

---

## 📖 Usage

### For Teachers

1. **Register** as a Teacher and log in.
2. Navigate to **"Upload Material"** and upload a PDF or DOCX file (e.g., your lecture notes).
3. Click **"Generate Quiz"** — the AI engine extracts concepts and creates question candidates.
4. **Review and edit** the generated questions, then configure quiz settings (time limit, difficulty, availability window).
5. **Publish** and assign the quiz to your student group.
6. View class-wide results in the **Analytics Dashboard** and export reports as PDF/CSV.

### For Students

1. **Register** as a Student and log in.
2. Browse available quizzes by subject or teacher from the **Quiz Library**.
3. Click **"Start Quiz"** — a countdown timer begins.
4. Submit answers and receive **instant feedback** with explanations for incorrect answers.
5. Track your score trends, weak topics, and time-spent history in the **Performance Dashboard**.

### For Admins

1. Log in with admin credentials.
2. Manage all users (create, update, deactivate) from the **User Management** panel.
3. View platform-wide reports and manage subscription plans.


## 📄 License

This project is submitted as an academic coursework project at AIUB. All rights reserved by the authors.

---

<p align="center">Built with ❤️ for Bangladesh's 40 million students.</p>
