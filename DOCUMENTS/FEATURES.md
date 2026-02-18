# 📊 Database Features & Architecture

> **Note to Developers:** This document outlines the *current* schema capability. Items marked with ⚠️ represent features that are recommended to be moved to an Application Layer (Backend) in modern microservices architectures.

---

## 🏗️ Table Structure & Modernization Guide

### Core User Data
| Table            | Description                     | Modern Architecture Note   |
| :--------------- | :------------------------------ | :------------------------- |
| **dbo.Customer** | User profiles and account info. | ✅ Standard RDBMS use case. |
| **dbo.Settings** | User account settings.          | ✅ Standard RDBMS use case. |
| **dbo.Language** | Language preferences.           | ✅ Standard RDBMS use case. |
| **dbo.Location** | Location data.                  | ✅ Standard RDBMS use case. |

### Social Graph
| Table            | Description          | Modern Architecture Note                                              |
| :--------------- | :------------------- | :-------------------------------------------------------------------- |
| **dbo.Follow**   | User following user. | ✅ Graph DB (Neo4j) is optional but RDBMS works well for medium scale. |
| **dbo.Request**  | Follow requests.     | ✅ Standard RDBMS use case.                                            |
| **dbo.Blocking** | Blocked users.       | ✅ Standard RDBMS use case.                                            |

### Content & Interactions
| Table           | Description         | Modern Architecture Note                                                          |
| :-------------- | :------------------ | :-------------------------------------------------------------------------------- |
| **dbo.Content** | Posts/Media shared. | ⚠️ **Blob Storage:** Media files should go to S3/Azure Blob, store only URLs here. |
| **dbo.Comment** | User comments.      | ✅ Standard RDBMS use case.                                                        |
| **dbo.Liked**   | Likes on content.   | ✅ Standard RDBMS use case.                                                        |
| **dbo.Hashtag** | Tags on content.    | ✅ Standard RDBMS use case.                                                        |

### ⚠️ Legacy/Optimization Candidates

These tables handle logic that is often better served by other technologies in a modern stack:

| Table                | Current Usage                | Recommended Modern Approach                                            |
| :------------------- | :--------------------------- | :--------------------------------------------------------------------- |
| **dbo.Cookies**      | Storing session/cookie data. | 🔴 **Redis / Memcached:** Use In-Memory stores for sessions.            |
| **dbo.Message**      | Chat messages.               | 🟡 **NoSQL (MongoDB/Cassandra):** For high-volume real-time chat.       |
| **dbo.Notification** | User notifications.          | 🟡 **Push Services:** Combine DB with Firebase/Socket.io.               |
| **dbo.Algorithm**    | Feed ranking logic.          | 🔴 **Compute Service:** Move to Backend/ML Service.                     |
| **dbo.Analytics**    | Usage stats.                 | 🔴 **Data Warehouse:** Use ClickHouse/Snowflake for big data analytics. |

---

## ⚙️ Stored Procedures

The database includes a robust set of Stored Procedures (SPs) to handle business logic.

> **Migration Tip:** If you are building a modern API (NestJS/.NET), you may want to convert these SPs into application code (Services) to follow the *Application Layer* pattern instead of *Database Layer* pattern.

### User Management
-   `CREATE_USER`: Architecture compliant.
-   `UPDATE_USER`: Architecture compliant.
-   `DELETE_USER`: Architecture compliant.

### Content Operations
-   `CREATE_POST`: Triggers notifications and analytics.
-   `CREATE_COMMENT`: Triggers notifications.
-   `CREATE_LIKE`: Updates recommendation engine.

*(Refer to source code for full list of 25 procedures)*
