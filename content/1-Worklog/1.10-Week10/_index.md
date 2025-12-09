---
title: "Week 10 Worklog"
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---

### Week 10 Objectives:

* **Production Deployment:** Deploy the official Production Environment infrastructure, including VPC, Security Groups, and Database instances.
* **Full Data Vectorization:** Process and ingest all datasets into the Vector Database (Pinecone/Neon).
* **Backend Logic Finalization:** Finalize the core processing logic for Tarot and Horoscope features in the Production environment.

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ---- | ---------- | --------------- | ------------------ |
| 2 | - **Infrastructure Setup:** Deploy Production VPC, configure strict Security Groups (allow only API Gateway -> Lambda -> DB) based on the approved diagram. <br> - Set up Environment Variables (Prod) for Lambda. | 10/11/2025 | 10/11/2025 | AWS VPC |
| 3 | - **Big Data Processing:** Write batch scripts to vectorize all data from `dataset_v2.jsonl` (Horoscope), `dataset_v3.jsonl` (Numerology), and `dataset_v4.jsonl` (Tarot). <br> - Upsert vectors into Pinecone index (Prod). | 11/11/2025 | 11/11/2025 | Pinecone Docs |
| 4 | - **Code Merge:** Coordinate with the team to merge Feature branches into Main. Resolve code conflicts in `lambda_functions.py`. <br> - Run CI/CD pipeline to deploy the latest build. | 12/11/2025 | 12/11/2025 | GitHub Actions |
| 5 | - **RAG Optimization (Prod):** Check retrieval speed with the full dataset. Tune the `top_k` parameter in `query_rag` to balance accuracy and latency. <br> - Final update to `prompts_master.py` to ensure consistent tone. | 13/11/2025 | 13/11/2025 | `local_worker.py` |
| 6 | - **9:00 PM Team Meeting:** Demo the "Lifetime Horoscope" feature with full data. <br> - Review Business Logic errors before entering the integration testing week. | 14/11/2025 | 14/11/2025 | Internal Team |
| 7 | - Backup Databases (RDS Snapshot/DynamoDB Export). <br> - Write Week 10 Worklog. | 15/11/2025 | 15/11/2025 | |

### Week 10 Achievements:

* **Infrastructure:**
    * Production environment is live and fully isolated from Dev/Test.
    * Network and security settings are configured according to the High-Level Architecture (HLA).

* **Data (Core AI):**
    * **100% of Data** from datasets (`v2`, `v3`, `v4`) has been cleaned and indexed into the Vector DB. The AI can now provide detailed readings for all Tarot cards and Zodiac signs.
    * RAG logic performs smoothly with the full dataset loaded.

* **Source Code:**
    * The codebase is stable; feature branches have been merged and are ready for comprehensive Integration Testing next week.