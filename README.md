# 📱 Social Media Database Template

[![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)](LICENSE)
[![Database](https://img.shields.io/badge/Database-SQL%20Server-red?style=flat-square)](https://www.microsoft.com/en-us/sql-server)
[![Status](https://img.shields.io/badge/Status-Active-blue?style=flat-square)](https://github.com/beydah/Social-Media-Database)

> **A comprehensive, enterprise-grade relational database architecture designed for scalable social networking platforms.** 

This project provides a robust **Data Layer** foundation for developers building social media applications similar to Twitter, Instagram, or LinkedIn. It features a fully normalized schema, pre-built business logic via stored procedures, and a clear modernization roadmap.

---

## 📖 Table of Contents
- [Introduction](#-introduction)
- [Key Features](#-key-features)
- [Database Architecture](#-database-architecture)
- [Modernization & Best Practices](#-modernization--best-practices)
- [Getting Started](#-getting-started)
- [Usage & Integration](#-usage--integration)
- [Roadmap](#-roadmap)
- [Contributing](#-contributing)
- [License](#-license)

---

## 🚀 Introduction

Building a social media platform requires a solid data foundation to handle complex relationships, high-volume content, and user interactions. This template offers a production-ready SQL Server schema that handles:
*   Complex User Relationships (Follow/Block/Mute)
*   Content Hierarchies (Posts, Threads, Comments)
*   Interaction Tracking (Likes, Views, Shares)
*   Administrative Controls (Reports, Logs, Moderation)

It is designed to be **backend-agnostic**, meaning you can connect it to **Node.js, .NET, Python, Go**, or any other technology stack.

---

## ✨ Key Features

### 👤 User Management
*   **Detailed Profiles:** Bio, Website, Location, Avatar/Banner headers.
*   **Privacy & Settings:** Granular control over account visibility and notifications.
*   **Security Logs:** Tracking login history and device information.

### 🌐 Social Graph
*   **Follow System:** Unidirectional (Twitter-style) or Bidirectional (Facebook-style) relationships.
*   **Blocking Logic:** Robust blocking system that prevents interaction at the database level.
*   **Recommendations:** Built-in logic to suggest users based on mutual connections.

### 📝 Content Engine
*   **Rich Media Support:** Schema supports posts with text, images, and video metadata.
*   **Threaded Comments:** Infinite depth commenting system.
*   **Hashtags & Trends:** Many-to-many relationship design for high-performance trending topic queries.

### 🛡️ Administration
*   **Reporting System:** Users can report content or other users with specific reasons.
*   **Moderation Queue:** Dedicated tables for reviewing reported items.

---

## 🏗️ Database Architecture

The project utilizes **Microsoft SQL Server** features to ensure data integrity and performance.

### Core Tables
*   `dbo.Customer` - The central user identity table.
*   `dbo.Content` - Stores all posts and media metadata.
*   `dbo.Follow` / `dbo.Request` - Manages the social graph.
*   `dbo.Notification` - Asynchronous event tracking.

### Stored Procedures (Business Logic)
The database includes 25+ Stored Procedures to encapsulate complex operations, ensuring that business rules (like "Creating a Post triggers a Notification") are enforced at the data layer.
*   `CREATE_POST`: Inserts content and updates user stats atomically.
*   `CREATE_FOLLOW`: Handles the logic of public vs. private profile requests.

---

## 💡 Modernization & Best Practices

⚠️ **Architectural Note:** While this template offers a complete "Monolithic Database" solution, modern high-scale applications often distribute responsibilities.

We recommend the following adaptations for a **Microservices** or **Cloud-Native** architecture:

| Feature                | Template Implementation     | Recommended Modern Approach                                                  |
| :--------------------- | :-------------------------- | :--------------------------------------------------------------------------- |
| **Session Management** | `dbo.Cookies` Table         | **Redis / Memcached** (In-Memory Key-Value Store) for speed and security.    |
| **Feed Generation**    | SQL Queries (`SELECT_MAIN`) | **Fan-out-on-write** + NoSQL (Cassandra/DynamoDB) for instant feed loading.  |
| **Media Storage**      | `dbo.Content` (Metadata)    | **Object Storage** (AWS S3, Azure Blob, MinIO). Store only the URL in SQL.   |
| **Analytics**          | `dbo.Analytics` Table       | **Data Warehouse** (Snowflake, ClickHouse) or ELK Stack for log aggregation. |

---

## 🏁 Getting Started

### Prerequisites
*   **Microsoft SQL Server** (2019 or newer)
*   **SSMS** (SQL Server Management Studio) or **Azure Data Studio**

### Installation
1.  **Clone the Repository**
    ```bash
    git clone https://github.com/beydah/Social-Media-Database.git
    ```
2.  **Restore the Database**
    *   Navigate to the `DATABASES/` folder.
    *   Open SSMS and connect to your SQL Server instance.
    *   Right-click `Databases` > `Restore Database...`
    *   Select `Device` -> `...` -> `Add` -> Select `BasicMedia_DB.bak`.
    *   Click `OK` to restore.

*See [INSTALLATION.md](DOCUMENTS/INSTALLATION.md) for detailed instructions.*

---

## 💻 Usage & Integration

You can connect to this database using any ORM or Database Client.

### 🟢 Node.js (Prisma ORM)
```bash
# 1. Initialize Prisma
npx prisma init

# 2. Configure .env
DATABASE_URL="sqlserver://localhost:1433;database=BasicMedia_DB;user=sa;password=your_password;encrypt=true"

# 3. Pull Schema
npx prisma db pull
```

### 🟣 .NET Core (Entity Framework)
```bash
# Scaffold the context from the existing DB
dotnet ef dbcontext scaffold "Server=.;Database=BasicMedia_DB;Trusted_Connection=True;" Microsoft.EntityFrameworkCore.SqlServer -o Models
```

*See [USAGE.md](DOCUMENTS/USAGE.md) for more examples.*

---

## 🗺️ Roadmap
*   [ ] **Docker Support:** Add `docker-compose.yml` for instant setup.
*   [ ] **API Layer:** Release a reference API implementation (NestJS & .NET).
*   [ ] **Migration Scripts:** Convert `.bak` files to version-controlled `.sql` migration scripts.
*   [ ] **Graph DB Export:** Script to export social graph to Neo4j.

---

## 🤝 Contributing

We welcome contributions from the community!
1.  Fork the Project.
2.  Create your Feature Branch (`git checkout -b feature/AmazingFeature`).
3.  Commit your Changes (`git commit -m 'Add some AmazingFeature'`).
4.  Push to the Branch (`git push origin feature/AmazingFeature`).
5.  Open a Pull Request.

Please review our [Code of Conduct](CODE_OF_CONDUCT.md) before contributing.

---

## 📄 License

Distributed under the MIT License. See `LICENSE` for more information.

---

<div align="center">
  <p>Maintained by <a href="https://github.com/beydah">Beydah Sağlam</a></p>
  <p>
    <a href="mailto:info.beydahsaglam@gmail.com">Contact</a> •
    <a href="https://github.com/beydah/Social-Media-Database/issues">Report Issue</a>
  </p>
</div>
