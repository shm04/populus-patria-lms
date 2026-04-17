# Populus Patria — Enterprise EdTech Ecosystem

> **Category:** Enterprise SaaS / Credit-Based Marketplace  
> **Client:** Populus Patria / Elevate Agency  
> **Lead Architect:** Sebastian Hernandez ([Elevate Agency](https://your-elevate-link.com))  
> **Project Status:** In Production (v2.0)

---

## 🌎 Languages
Read this in [Spanish](./README-es.md)

---

# 📗 Table of Contents
- [📖 About the Project](#about-project)
- [🚀 Core Features & Virtual Economy](#core-features)
- [🏗️ Architectural Design](#architectural-design)
- [💻 Tech Stack](#tech-stack)
- [🧗 Technical Deep-Dive: Chronos & Ghost Sync](#technical-deep-dive)
- [🔒 Security & Compliance](#security)
- [🔒 Code Access Policy](#code-access)
- [👥 Authors](#authors)
- [📝 License](#license)

---

## 📖 About the Project <a name="about-project"></a>
Traditional language schools struggle with "Tool Fragmentation"—relying on disconnected systems for payments, scheduling, communication, and virtual classrooms. 

Populus Patria solves this by providing a unified, Enterprise-Grade Language Economy. It consolidates the entire student lifecycle into a single, high-performance dashboard, eliminating data silos and administrative friction.

**Key Links:**
* [Live Demo / Website](https://app.populuspatria.com/) 
* [Platform Walkthrough (Loom)](#)

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## 🚀 Core Features & Virtual Economy <a name="core-features"></a>
* **Automated "Meet-to-Archive" Lifecycle:** A sophisticated pipeline that generates Google Meet links upon booking, detects finished sessions via Node-cron, fetches recordings, and maps them to the correct students automatically.
* **Intelligent "Shadow" Recordings:** A unique access-control system ensuring students only view recordings of classes that occurred *after* their specific enrollment date, protecting historical intellectual property.
* **Hybrid Community Engine:** Deep integration with Rocket.Chat featuring SSO. It acts as the social layer while preventing platform leakage by blocking the unauthorized exchange of personal data.
* **Multi-Modal Wallet System:** A virtual economy supporting Stripe for global transactions across five distinct modalities: CPP (Personalized), CGG (General Group), CGP (Private Group), and CCC (Conversation Club).

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## 🏗️ Architectural Design <a name="architectural-design"></a>
Built using a **Domain-Driven Design (DDD)** approach combined with a Layered Architecture to ensure high maintainability.

* **Domain Modules:** The system is split into independent domains, including Auth, Payment, Classroom, and Community.
* **Controllers:** Handle strictly HTTP logic and routing.
* **Services:** Encapsulate the core business logic and virtual economy rules.
* **Repositories:** Abstract the Serverless PostgreSQL persistence layer.
* **Auto-Healing Engine:** A specialized background layer designed to resolve data inconsistencies (like manual class name changes) by mapping unique IDs rather than volatile strings.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## 💻 Tech Stack <a name="tech-stack"></a>
* **Frontend:** React 19, Vite, Tailwind CSS 4, Framer Motion, React Router v7.
* **Backend:** Node.js, Express v5.0, `node-cron`.
* **Database:** PostgreSQL (Hosted on Neon for serverless scalability).
* **Infrastructure:** Railway (Production App & Rocket.Chat hosting).
* **APIs & Integrations:** Stripe, Google Meet API, Rocket.Chat API, Nodemailer.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## 🧗 Technical Deep-Dive: The Chronos & Ghost Sync <a name="technical-deep-dive"></a>
The most complex engineering feat of this platform was solving **Session Hydration** (The Ghost Synchronization problem). 

When class names changed in the database, automated recording scripts would "lose" the connection to the video files. 

**The Engineering Solution:** I built a Self-Healing Mapping Engine that uses the Google Meet unique code as the absolute "Source of Truth." This reconnects orphaned sessions to the correct `class_id`, ensuring the automation never breaks, regardless of human administrative errors.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## 🔒 Security & Compliance <a name="security"></a>
* **Communications Shield:** Real-time RegEx filtering on the community layer to prevent "Business Leakage" by blocking phone numbers and external payment keywords.
* **Transaction Integrity:** Implemented Atomic SQL transactions for the Wallet to ensure no student can double-spend credits or book without a valid balance.
* **Stateless Auth:** Secure JWT implementation ensuring protected sessions even in a horizontally scaled environment.
* **Regulatory Compliance:** Privacy and data architecture aligned with LFPDPPP (Mexico) and general GDPR principles.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## 🔒 Code Access Policy <a name="code-access"></a>
The source code for this project is **Proprietary**. It contains confidential business logic regarding the payment gateways, community filtering, and credit system.

I am available for a **Live Technical Deep-Dive** via screen-share to demonstrate the Auto-Healing Engine, PostgreSQL transactions, and layered backend architecture.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## 👥 Authors <a name="authors"></a>

👤 **Sebastian Hernandez**
* **Role:** Lead Full-Stack Engineer / Architect
* **Agency:** [Elevate Agency](https://your-elevate-link.com)
* **LinkedIn:** [Sebastian Hernandez](https://www.linkedin.com/in/sebastian-hernandez-munoz/)
* **GitHub:** [@your-github](https://github.com/shm04)

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## 📝 License <a name="license"></a>
This project is **Proprietary and Closed Source**. All rights reserved.

<p align="right">(<a href="#readme-top">back to top</a>)</p>
