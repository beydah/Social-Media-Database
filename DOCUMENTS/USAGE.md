# 💻 Developer Usage & Integration Guide

## 🔌 Connecting to an Application

This database is designed to be the backend for modern applications. Below are examples of how to connect.

### Option A: Node.js (Prisma ORM)
Using Prisma is recommended to generate type-safe clients from this existing schema.

1.  **Initialize:** `npx prisma init`
2.  **Introspect:** Pull the schema from the DB.
    ```bash
    npx prisma db pull
    ```
3.  **Use:**
    ```typescript
    const users = await prisma.customer.findMany({
      include: { posts: true }
    });
    ```

### Option B: .NET Core (Entity Framework)
1.  **Scaffold:**
    ```bash
    dotnet ef dbcontext scaffold "Server=.;Database=AdvancedMedia_DB;Trusted_Connection=True;" Microsoft.EntityFrameworkCore.SqlServer -o Models
    ```

---

## 🛠️ Contribution & Development
We are actively looking to modernize this repository.

### High Priority Tasks
-   [ ] **Create API Layer:** Build a REST/GraphQL API on top of this DB.
-   [ ] **Dockerize:** Create a `Dockerfile` for the SQL instance.
-   [ ] **Tests:** Add integration tests for Stored Procedures.

### How to Contribute
1.  Fork the repository.
2.  Create a Feature Branch (`git checkout -b feature/AmazingFeature`).
3.  Commit changes (`git commit -m 'Add AmazingFeature'`).
4.  Push (`git push origin feature/AmazingFeature`).
5.  Open a **Pull Request**.

See [CODE_OF_CONDUCT.md](../CODE_OF_CONDUCT.md) for community guidelines.
