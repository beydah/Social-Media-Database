# 📥 Installation & Setup Guide

## 1. Prerequisites
-   **Microsoft SQL Server** (2019 or newer)
-   **SSMS** (SQL Server Management Studio)

## 2. Download Database
Choose the version that fits your needs:

| Version      | Description                     | Download Link                                                                                            |
| :----------- | :------------------------------ | :------------------------------------------------------------------------------------------------------- |
| **Basic**    | Core schema (27 Tables)         | [Download .bak](https://github.com/beydah/Social-Media-Database/raw/main/DATABASES/BasicMedia_DB.bak)    |
| **Advanced** | Core schema + Stored Procedures | [Download .bak](https://github.com/beydah/Social-Media-Database/raw/main/DATABASES/AdvancedMedia_DB.bak) |
| **Edu**      | Pre-populated with dummy data   | [Download .bak](https://github.com/beydah/Social-Media-Database/raw/main/DATABASES/EduMedia_DB.bak)      |

## 3. Restoration Guide (SSMS)

1.  Open **SQL Server Management Studio (SSMS)** and connect to your instance.
2.  Right-click **Databases** node > **Restore Database...**
3.  Select **Device** radio button > Click **...** (Browse).
4.  Add the downloaded `.bak` file.
5.  Click **OK** to restore.

> **💡 Pro Tip:** If you encounter permission errors, try running SSMS as Administrator.

## 4. Docker Setup (Recommended for Local Dev)

*Coming Soon: A `docker-compose.yml` file will be provided to spin up an MS-SQL container with this database pre-loaded.*
