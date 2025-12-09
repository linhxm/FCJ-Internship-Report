---
title: "Week 4 Worklog"
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

### Week 4 Objectives:

* **Security & Monitoring:** Secure infrastructure and set up CloudWatch monitoring to manage costs and performance from day one.
* **Project Kick-off:** Finalize feature scope, assign roles, and establish team workflows.
* **AI Prototyping:** Build a local AI prototype to validate RAG logic and Prompt Engineering for Tarot/Chatbot features.

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ---- | ---------- | --------------- | ------------------ |
| 2 | - Configure **AWS CloudWatch Alarms** for Billing (budget control) and EC2/RDS performance monitoring. <br> - Enable **CloudTrail** for account auditing and security logging. | 29/09/2025 | 29/09/2025 | <https://aws.amazon.com/cloudwatch/> |
| 3 | - Prepare detailed feature list: Tarot (1-card/3-card), Horoscope, Numerology. <br> - **9:00 PM Team Meeting:** Project Kick-off, finalize Tech stack (BE: Lambda, DB: Pinecone/RDS), and Gitflow process. | 30/09/2025 | 30/09/2025 | Internal Team |
| 4 | - **AI Coding:** Build a local Python script to simulate Tarot drawing and interpretation generation (using OpenAI API + Prompt templates). <br> - Test Prompt Engineering techniques to define the AI Persona ("Fortune Teller"). | 01/10/2025 | 01/10/2025 | `prompts.py` |
| 5 | - **RAG Coding:** Integrate Pinecone into the local script to retrieve card meanings from vectorized data. <br> - Evaluate response accuracy with and without RAG. | 02/10/2025 | 02/10/2025 | Pinecone Docs |
| 6 | - Design **Chatbot Logic:** Define guardrails to restrict the bot to spiritual topics and refuse out-of-scope questions. <br> - **9:00 PM Team Meeting:** Assign tasks on Jira/Trello. Officially take on the **AI Lead** role. | 03/10/2025 | 03/10/2025 | Internal Team |
| 7 | - Document the AI Logic Flow for the Backend team to understand integration points. <br> - Write Week 4 Worklog. | 04/10/2025 | 04/10/2025 | |

### Week 4 Achievements:

* **Infrastructure & Management:**
    * Established monitoring dashboards and billing alarms on AWS.
    * Finalized workflows and feature list for the MVP (Minimum Viable Product).

* **AI & Application (Local):**
    * Successfully built a **Local AI Prototype**:
        * Input: User question + Drawn cards.
        * Process: RAG (Pinecone) retrieves context -> LLM (OpenAI) generates advice.
        * Output: Spiritual, empathetic responses.
    * Defined clear boundaries for the Chatbot: Restricted it from answering questions that overlap with specific reading features (e.g., Chatbot guides users to the Tarot feature instead of doing the reading itself).

* **Teamwork:**
    * Officially accepted the AI Lead role and assigned tasks for the first Sprint.