---
title: "Week 9 Worklog"
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

### Week 9 Objectives:

* **Scheduled Tasks:** Implement the "Daily Horoscope" feature using **Amazon EventBridge** for scheduling and **Amazon SES** for email delivery.
* **Security & Identity:** Integrate **Amazon Cognito** for user management and **AWS Secrets Manager** to protect sensitive API Keys.
* **Architecture Finalization:** Finalize and approve the High-Level Architecture (HLA) diagram.

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ---- | ---------- | --------------- | ------------------ |
| 2 | - **Configure Cognito:** Create a User Pool for app authentication and integrate it with API Gateway Authorizer. <br> - **Security:** Migrate API Keys (OpenAI, Pinecone) from environment variables to **AWS Secrets Manager**. | 03/11/2025 | 03/11/2025 | AWS Cognito & Secrets Manager |
| 3 | - **Setup SES:** Configure Amazon SES (Simple Email Service), verify sender domain/email. <br> - Implement the `send_email` function in `lambda_functions.py` integrated with SES. | 04/11/2025 | 04/11/2025 | <https://aws.amazon.com/ses/> |
| 4 | - **Create Cron Job:** Configure **EventBridge Scheduler** to trigger the `DailyEmailJob` Lambda at 6:00 AM daily. <br> - Update `prompts_master.py` with a new prompt template for "Daily Forecast". | 05/11/2025 | 05/11/2025 | AWS EventBridge |
| 5 | - **Integration Testing:** Verify the flow: EventBridge -> Lambda -> RAG (get forecast) -> SES (send email). Ensure emails are delivered to Inbox. | 06/11/2025 | 06/11/2025 | Internal Team |
| 6 | - **9:00 PM Team Meeting:** Present the complete Architecture Diagram (updated with SQS, EventBridge, SES, Cognito) for final team approval. <br> - Discuss the Demo scenario for the final week. | 07/11/2025 | 07/11/2025 | Internal Team |
| 7 | - Audit IAM permissions (Least Privilege) for the newly added services. <br> - Write Week 9 Worklog. | 08/11/2025 | 08/11/2025 | |

### Week 9 Achievements:

* **Features:**
    * **"Daily Horoscope"** is now fully automated: The system wakes up at 6 AM, calculates the forecast, and sends emails to users without manual intervention.
    * User Authentication (AuthN/AuthZ) is secured with Cognito.

* **Security:**
    * Eliminated storage of API Keys in code or insecure environment variables by using **Secrets Manager**.

* **Documentation:**
    * The Architecture Diagram has been updated to reflect the full implementation (EventBridge, SES, Cognito) and matches the actual deployment.