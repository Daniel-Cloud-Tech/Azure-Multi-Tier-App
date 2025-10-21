# 📝 Task List Web App on Azure

A simple CRUD task list application built with Python and deployed to Azure App Service. The focus for this project was to gain hands-on experience with Azure App Service.

---

## 🚀 Project Overview

This web app allows users to:
- Create tasks
- View existing tasks
- Delete completed tasks

The goal was to keep the app lightweight while exploring Azure deployment and infrastructure setup.

---

## 🧱 Azure Deployment Steps

1. **Created a Resource Group**
   - All resources were placed in a single group for easy cleanup and management.

2. **Provisioned an App Service Plan**
   - Selected the **Free Tier (F1)** to start.
   - Plan can be upgraded later based on business needs.

3. **Created the Web App**
   - Linked it to the App Service Plan.
   - Chose **manual ZIP deployment** for quick testing.

4. **Initial Deployment & Error Handling**
   - Encountered a **500 Internal Server Error** on first launch.
   - Used **Log Stream** to trace the issue:
     - Error: `sqlite3.OperationalError: no such table: task`

5. **Fix & Redeployment**
   - Edited `app.py` to ensure the `task` table is created before queries run:
     ```python
     with app.app_context():
         db.create_all()
     ```
   - Re-deployed the app and confirmed successful operation.

---

## 🛠️ Technologies Used

- **Python + Flask**
- **SQLite** (local database)
- **Azure App Service (Linux)**
- **Manual ZIP Deployment**
- **Log Stream for diagnostics**

---

## 🔐 Next Steps: Security & Scaling

- Implement Azure App Gateway & Azure Firewall
- Migrate to Azure SQL for scalable data tier
- Add authentication via Azure AD or OAuth

---

## 📌 Author Notes

The web app was developed with the use of generative AI to accelerate learning. It serves as a foundational step toward building secure, scalable cloud-native applications.

