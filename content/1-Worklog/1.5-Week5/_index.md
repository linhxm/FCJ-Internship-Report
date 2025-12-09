---
title: "Week 5 Worklog"
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

### Week 5 Objectives:

* **AWS Scaling & Load Balancing:** Master the configuration of Application Load Balancer (ALB) and Auto Scaling Groups (ASG) for high availability.
* **Data Engineering:** Finalize the Data Ingestion Pipeline and process raw datasets into vector embeddings.
* **RAG Optimization:** Refine data chunking strategies and update advanced prompt templates for specific domains (Love, Career).

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ---- | ---------- | --------------- | ------------------ |
| 2 | - **AWS Practice:** Configure ALB with Target Groups and define Launch Templates for ASG. <br> - Perform stress tests to validate auto-scaling logic based on CPU utilization. | 06/10/2025 | 06/10/2025 | <https://aws.amazon.com/autoscaling/> |
| 3 | - Batch process `dataset_v4.jsonl` to generate vector embeddings. <br> - **9:00 PM Team Meeting:** Review estimated costs for Pinecone/Neon with large data ingestion. | 07/10/2025 | 07/10/2025 | Internal Team |
| 4 | - Optimize **Chunking Strategy:** Test optimal text segment lengths for RAG retrieval using `dataset_v3.jsonl`. <br> - Review logic in `lambda_functions.py` in preparation for cloud migration. | 08/10/2025 | 08/10/2025 | Pinecone Docs |
| 5 | - Refine Prompt System: Update `prompts_master.py` with specialized scenarios for Love and Career readings. <br> - Write Python scripts to automate embedding updates for new data. | 09/10/2025 | 09/10/2025 | `prompts_master.py` |
| 6 | - Deep dive into **Metadata Filtering** in Pinecone to improve RAG accuracy (e.g., filter by 'Tarot' vs 'Horoscope'). <br> - **9:00 PM Team Meeting:** Finalize the Vector Storage strategy. | 10/10/2025 | 10/10/2025 | Internal Team |
| 7 | - Summarize Scaling knowledge. <br> - Write Week 5 Worklog. | 11/10/2025 | 11/10/2025 | |

### Week 5 Achievements:

* **AWS Infrastructure:**
    * Validated Auto Scaling logic to ensure system resilience under high traffic loads.
    * Gained practical experience in traffic distribution using Application Load Balancer.

* **Data & AI (Project):**
    * Successfully indexed the full Knowledge Base from `dataset_v2.jsonl`, `dataset_v3.jsonl`, and `dataset_v4.jsonl` into the Vector DB.
    * Achieved high RAG retrieval accuracy through Metadata and Chunking optimization.
    * Source code (`lambda_functions.py`, `prompts_master.py`) is ready for deployment to AWS Lambda next week.

* **Cost Management:**
    * Confirmed the cost-effectiveness of Serverless Vector DB solutions compared to self-hosted EC2/RDS options for the initial phase.