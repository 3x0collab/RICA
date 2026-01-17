# RICA | Regulatory Reporting Engine

**Status:** Production (Private Microservice)

### 📌 Project Context
**RICA** is a specialized reporting service that I extracted from the main **RadarPro** banking core. As our data volume grew, generating massive regulatory reports was slowing down the main app. I spun this out into its own standalone microservice to handle the heavy lifting without affecting user transactions.

**⚠️ Source Code Notice:**
This repository is a technical showcase. The source code remains private due to strict NDA and data protection agreements regarding the financial reporting standards used.

---

### What RICA Does
While the main banking app handles live money, **RICA** handles the compliance aftermath—automating the mandatory reports required by Central Banks and Financial Intelligence Units.

* **Automated Extraction:** Pulls raw transaction logs from the data warehouse at scheduled intervals (Daily/Weekly/Monthly).
* **Format Conversion:** Automatically converts data into strict regulatory formats (XML, CSV, XBRL) required by government portals.
* **Error Validation:** Pre-validates reports against schema rules before submission to prevent regulatory rejection.
* **Audit Trail:** Keeps a permanent, immutable log of exactly what data was sent to regulators and when.

### 🛠️ Tech Stack
* **Backend:** Python (Django) – Chosen for its robust data manipulation libraries.
* **Data Processing:** Pandas & NumPy – Used to aggregate and format millions of transaction rows efficiently.
* **Task Queue:** Celery – Manages the generation of massive reports in the background.
* **Database:** Read-Replica of the main PostgreSQL DB (to avoid locking the live database).

### 📸 Interface Preview
*(The dashboard where Compliance Officers schedule and download reports)*

![RICA Dashboard](Screenshot%202025-10-27%20150634.png)
*Report generation dashboard showing status and download options.*
