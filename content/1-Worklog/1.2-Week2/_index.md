---
title: "Week 2 Worklog"
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

### Week 2 Objectives:

* **Master AWS Core Services:** Gain deep understanding and hands-on experience with Compute (EC2), Storage (S3), and Identity Access Management (IAM).
* **Project Technology Research:** Investigate and evaluate Serverless Vector Database solutions (Pinecone, Neon) for future RAG implementation.
* **Resource Preparation:** Set up the development environment and gather/process raw data (Tarot, Horoscope).

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ---- | ---------- | --------------- | ------------------ |
| 2 | - Study IAM concepts: Users, Groups, Roles, Policies for access management. <br> - Practice: Configure Root MFA and create an Admin User for account security. | 15/09/2025 | 15/09/2025 | <https://aws.amazon.com/iam/> |
| 3 | - Deep dive into S3: Storage Classes, Lifecycle Rules. <br> - Collect and upload raw datasets (Tarot/Horoscope) to S3 for storage. | 16/09/2025 | 16/09/2025 | <https://aws.amazon.com/s3/> |
| 4 | - Research EC2: Instance types (T2, T3...), Security Groups, AMI. <br> - Setup local Python environment with necessary AI libraries (LangChain, OpenAI) for logic testing. | 17/09/2025 | 17/09/2025 | <https://aws.amazon.com/ec2/> |
| 5 | - **AI Research:** Compare RDS pgvector vs. Pinecone vs. Neon for vector storage. <br> - Write a small Python script to test connection and data upsert to Pinecone (Free tier). | 18/09/2025 | 18/09/2025 | Pinecone & Neon Docs |
| 6 | - Research CI/CD concepts and why GitHub Actions is chosen. <br> - **9:00 PM Team Meeting:** Present Vector DB research findings and finalize input data structure. | 19/09/2025 | 19/09/2025 | Internal Team |
| 7 | - Optimize data processing scripts (cleaning, formatting to JSONL). <br> - Summarize knowledge and write Week 2 Worklog. | 20/09/2025 | 20/09/2025 | |

### Week 2 Achievements:

* **AWS Infrastructure:**
    * Secured AWS account configuration (IAM, MFA) following best practices.
    * Understood S3 mechanisms and successfully stored project raw data.
    * Gained knowledge on EC2 instance launch and security configuration.

* **Project Preparation (AI/Data):**
    * Completed evaluation of Vector Database solutions. Selected **Pinecone** or **Neon** for the initial phase to optimize costs and leverage Serverless capabilities.
    * Development environment is ready with all necessary libraries installed.
    * Aligned with the team on the Data Schema for Tarot and Horoscope features.

* **Process:**
    * Grasped the basic concepts of CI/CD, ready for automated pipeline implementation in the upcoming weeks.