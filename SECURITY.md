# 🛡️ Security Policy

## Supported Versions

| Version              | Supported                   |
| :------------------- | :-------------------------- |
| **AdvancedMedia_DB** | ✅ Yes                       |
| **BasicMedia_DB**    | ✅ Yes                       |
| **EduMedia_DB**      | ❌ No (Educational Use Only) |

## ⚠️ Known Security Risks & Limitations

This project is a **Database Template** and comes with inherent risks if not implemented correctly in the Application Layer:

1.  **Session Management:** The `dbo.Cookies` table is for *demonstration purposes only*. DO NOT use this in production. Use secure, encrypted, HTTPOnly cookies with a Redis/Memcached backend.
2.  **SQL Injection:** If you are using Raw SQL commands in your app to query this DB, you are at risk. Always use an ORM (Entity Framework, Prisma) or Parameterized Queries.
3.  **Data Privacy (GDPR/KVKK):** The schema includes PII (Personally Identifiable Information). Ensure you implement "Right to be Forgotten" (data anonymization) in your application logic.

## 🐛 Reporting a Vulnerability

We take security seriously.

1.  **Do not** open a public GitHub issue for sensitive security vulnerabilities.
2.  Email **[info.beydahsaglam@gmail.com](mailto:info.beydahsaglam@gmail.com)** with details.
3.  We will acknowledge your report within 48 hours.
