# email-to-sqldb-using-adf-logicapp
This project automates the process of extracting email attachments and loading them into Azure SQL Database.  
When an email is received *from a specific sender, **with the subject "credit data", the attached **CSV file* is automatically saved to *Azure Blob Storage* using a Logic App. An *Event Grid Trigger* then activates an Azure Data Factory pipeline that copies the CSV data into Azure SQL Database.

---

##  Architecture Workflow
1. *Logic App*  
   - Triggers when a new email arrives.  
   - Validates sender email and subject.  
   - Extracts only CSV attachments.  
   - Uploads file to Azure Blob Storage.

2. *Azure Data Factory*  
   - Uses an *Event Trigger* to detect the new file in Blob Storage.  
   - Executes a *Copy Activity* to load CSV data into Azure SQL Database.

---
##  Key Features
- Fully automated email → Blob → SQL workflow  
- Filters by *sender* and *"credit data"* subject  
- Supports only *CSV* for data ingestion  
- Event-based, serverless, low-maintenance design  

---

##  Use Case
Ideal for teams that receive periodic credit-related reports via email and want an automated, reliable ingestion pipeline into Azure SQL Database.

