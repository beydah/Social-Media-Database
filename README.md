# 📱 Social Media Database Template

![Project Status](https://img.shields.io/badge/Status-Database%20Template-blue)
![License](https://img.shields.io/badge/License-MIT-green)
![Tech](https://img.shields.io/badge/Main%20Tech-SQL%20Server-red)

> **A comprehensive, enterprise-grade relational database schema designed for social media platforms.**

---

## 📖 About The Project (For HR & Recruiters)

This project allows you to set up the data backbone of a fully functional social media application in minutes. It provides a robust **Relational Database Management System (RDBMS)** design capable of handling complex social interactions.

### key Capabilities
*   **User Management:** detailed profiles, settings, privacy controls.
*   **Social Graph:** Follow/Block logic, friend requests.
*   **Content Engine:** Posts, comments, hashtags, likes hierarchy.
*   **Communication:** Messaging chains and notifications.
*   **Analytics & Security:** Underlying structure for reporting and data analysis.

**Tech Stack:** `Microsoft SQL Server` (T-SQL), `Relational Database Design`, `Stored Procedures`.

---

## 👨‍💻 For Developers

This repository contains the **Data Layer** of a social media stack. It is designed to be the foundation for a `Node.js`, `.NET`, or `Python` backend.

### 🏗️ Architecture & Modernization Notes

⚠️ **Architectural Notice:** This project uses a **Stored Procedure heavy** architecture. While robust for data integrity, modern microservices architectures may require migrating some logic (like `Cookies` and `Algorithms`) to the Application Layer.

| Feature            | Current State (SQL)   | Modern Recommendation                              |
| :----------------- | :-------------------- | :------------------------------------------------- |
| **Session Mgmt**   | `dbo.Cookies` Table   | **Redis / In-Memory Store** (Faster & More Secure) |
| **Feed Algorithm** | `dbo.Algorithm` Table | **Backend Service** (AI/ML based ranking)          |
| **Logic**          | Stored Procedures     | **ORM (Prisma/TypeORM)** + Application Logic       |

### 📂 Repository Structure
*   `DATABASES/`: `.bak` backup files for instant restore.
*   `DIAGRAMS/`: Entity-Relationship Diagrams (ERD).
*   `DOCUMENTS/`: Detailed technical documentation.

---

## 🚀 Getting Started

1.  **Download:** Get the latest `.bak` file from [INSTALLATION.md](DOCUMENTS/INSTALLATION.md).
2.  **Restore:** Import into SSMS (SQL Server Management Studio).
3.  **Connect:** Link your API (Next.js, NestJS, .NET, etc.) to the database.

See [USAGE.md](DOCUMENTS/USAGE.md) for integration guides.

---

## 🤝 Contributing

We welcome contributions! Specifically, we are looking for:
*   Converting SPs to modern API Endpoints.
*   Dockerizing the SQL Server setup.
*   Migration scripts (`.sql`) instead of binary backups.

Please read [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md) before contributing.

---

<div align="center">
    <p>Developed with ❤️ by Beydah Sağlam</p>
    <a href="mailto:info.beydahsaglam@gmail.com">Contact</a>
</div>
