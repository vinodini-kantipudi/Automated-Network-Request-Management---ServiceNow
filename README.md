# Automated-Network-Request-Management---ServiceNow
Automated Network Request Management is a ServiceNow-based automation solution designed to streamline, track, and fulfill network configuration requests. This project replaces slow, manual ticketing workflows with automated orchestration to reduce deployment times.


##  Overview

Organizations often handle network-related requests, such as new connections, access changes, or configuration updates, through emails, calls, or spreadsheets. This makes tracking, approvals, and accountability difficult.

This project solves that by building an end-to-end automated workflow inside ServiceNow. Employees submit a request through the **Service Catalog**, and the system takes over from there — validating data, routing it for approval, notifying stakeholders, and updating request status automatically at every stage.


##  Key Features

- **Custom Database Table** to store all network requests, with fields for connection type, requester details, amount, and approval status
- **Service Catalog Item** with dynamic, user-friendly form fields
- **Reusable Variable Set** with auto-populate, so requester details fill in automatically based on the selected user
- **Catalog UI Policy** that shows or hides fields based on user input (for example, showing an "Existing ID" field only when the connection type is "Existing")
- **Flow Designer Automation** that:
  - Captures submitted catalog variables
  - Creates a record in the custom database table
  - Sends email notifications to stakeholders
  - Routes the request for approval
  - Updates the record's status and assignment based on the approval outcome (Approved / Rejected)
- **End-to-end tested** through the Service Portal, from submission to final approval


##  Tech Stack

| Category | Details |
|---|---|
| Platform | ServiceNow |
| Tools Used | Service Catalog, Flow Designer, Catalog UI Policies, Variable Sets, Custom Tables |
| Interfaces | ServiceNow Workspace, Service Portal |



##  Setup / How It Works

1. **Custom Table:** A table (`u_database_table`) was created under System Definition to store request records, with fields such as Mobile Number, Type of Connection, Total Amount, Approval Status, and Assigned To.
2. **Catalog Item:** A "Network Request" item was created under Service Catalog with relevant variables and a variable set (Requester Information) for auto-populated fields.
3. **UI Policy:** A Catalog UI Policy dynamically shows the "Existing ID" field only when the user selects "Existing" as the connection type.
4. **Flow Designer:** A flow named "Network Request" is triggered on catalog submission. It:
   - Retrieves catalog variables
   - Creates a database record
   - Sends a confirmation email
   - Requests approval from the designated approver
   - Updates the record based on the approval decision


##  Demo Video

>  https://drive.google.com/file/d/1J6adB8Q-zcY55d5RniRWo15MBw5uutPT/view?usp=sharing


##  Outcome

This project demonstrates a complete no-code/low-code automation pipeline within ServiceNow — reducing manual effort, improving turnaround time, and ensuring every request is tracked and auditable from creation to closure.
