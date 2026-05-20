# 🧠 QuizForge — AI-Powered Quiz & Exam Preparation Platform

> A Software Requirements Engineering (SRE) project proposing an AI-driven quiz and exam preparation platform for students and teachers in Bangladesh.

---

## 📌 Project Overview

**QuizForge** is a fully documented software concept developed as part of the *Software Requirement Engineering* course at **American International University-Bangladesh (AIUB)**

This repository contains the **complete SRE documentation** for QuizForge — a proposed web platform where teachers upload study materials (PDFs, DOCX, plain text) and an AI engine automatically generates quizzes from them. Students then take those quizzes, receive instant feedback, and track their progress over time — all in one place, in both **English and Bengali**.

> **This is a documentation-based project.** It covers the full software engineering lifecycle from problem identification through requirements, system design, UML modeling, business planning, and financial analysis.

---

## 👥 Team

| Name | Student ID |
|---|---|
| Abul Bashar Saurov | 22-48823-3 |
| Farhan Sadik Nabil | 22-48840-3 |
| Arpita Chakraborty | 22-48845-3 |
| Aminul Islam Dipu | 22-48847-3 |

---

## 📂 Document Contents

The SRE document (`SRE_Project.pdf`) is structured across 7 major sections:

| Section | What It Covers |
|---|---|
| **1. Problem Domain** | Background on Bangladesh's education gap, the solution concept, and comparison with existing platforms (Quizlet, Kahoot, Google Forms, Coursera) |
| **2. Solution Description** | Full system feature list with functional requirements (FR-01 to FR-23), quality attributes, and three UML diagrams |
| **3. Social Impact** | Analysis of QuizForge's potential impact on education equity, teacher workload, digital literacy, and the environment |
| **4. Development Plan** | Agile/Scrum SDLC methodology, 4-phase development roadmap, technology stack, Gantt chart, and team roles |
| **5. Marketing Plan** | Short-term (0–6 months) and long-term (6–24 months) marketing strategies targeting students, teachers, and institutions |
| **6. Cost & Profit Analysis** | Itemized development and marketing costs, revenue model (Free / Pro / Institution tiers), 3-year revenue projections, and profit margin analysis |
| **7. References** | Citations from BANBEIS, UNESCO, OpenAI, SSLCommerz, bKash, and standard SRE literature |

---

## ✨ Proposed Key Features

- **AI Quiz Generation** — Teachers upload a PDF or DOCX; the NLP engine extracts key concepts and generates MCQ, True/False, and short-answer questions automatically.
- **Bilingual Platform** — Full support for both **English and Bengali**, making it accessible to a wider Bangladeshi audience.
- **Role-Based System** — Three roles: `Admin`, `Teacher`, and `Student`, each with dedicated capabilities.
- **Quiz Management** — Configurable time limits, difficulty levels, passing marks, question shuffling, and availability windows.
- **Instant Student Feedback** — Per-question feedback, answer explanations, and performance history.
- **Analytics Dashboard** — Students track weak topics and score trends; teachers get class-level reports exportable as PDF/CSV.
- **Freemium Subscription Model** — Free tier + Pro Teacher (BDT 499/mo) + Institution (BDT 4,999/mo) plans, paid via bKash, Nagad, or card.

---

## 🗂️ UML Diagrams (included in document)

Three UML diagrams were designed to model the system:

**1. Use Case Diagram**
Identifies actors (Admin, Teacher, Student, AI Engine, Payment Gateway) and all their system interactions — from quiz generation and student tracking to subscription management.

**2. Activity Diagram**
Describes the step-by-step flow of a teacher creating an AI-generated quiz: login → upload material → AI extraction → review/edit → publish → student notification.

**3. Class Diagram**
Defines 8 core classes and their relationships:
- `User` ← extended by `Teacher` and `Student`
- `Quiz` contains many `Question`
- `Student` makes many `QuizAttempt`
- `Teacher` uploads `StudyMaterial` which generates `Question`
- `User` has a `Subscription`

---

## 🛠️ Proposed Technology Stack

| Layer | Technology |
|---|---|
| Frontend | React.js + Tailwind CSS |
| Backend | Node.js + Express.js |
| Database | PostgreSQL + Redis |
| File Storage | AWS S3 / Cloudflare R2 |
| AI Engine | OpenAI GPT-4 API / HuggingFace |
| Payment | bKash PGW + SSLCommerz |
| Hosting | AWS EC2 / DigitalOcean |
---
## 📚 References

Key sources used in this project:
- Bangladesh Bureau of Educational Information and Statistics (BANBEIS), 2023
- UNESCO — *Digital Transformation of Education in Bangladesh*, 2022
- OpenAI GPT-4 API Documentation, 2024
- Sommerville, I. — *Software Engineering*, 10th ed., Pearson Education
- Ministry of ICT Bangladesh — *Digital Bangladesh Vision 2041*

---

<p align="center">📘 Submitted to the Department of Computer Science, AIUB — Spring 2025–26</p>
