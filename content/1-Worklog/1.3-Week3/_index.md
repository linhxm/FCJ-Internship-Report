---
title: "Week 3 Worklog"
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

### Week 3 Objectives:

* **Master Networking:** Understand and design secure Virtual Private Cloud (VPC) architectures with proper subnetting.
* **Master Databases:** Distinguish between and practice with RDS (SQL) and DynamoDB (NoSQL).
* **AI/RAG Preparation:** Deep dive into vector storage options, specifically comparing RDS (pgvector) vs. specialized solutions like Pinecone.

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ---- | ---------- | --------------- | ------------------ |
| 2 | - Study VPC theory: CIDR, Subnets (Public/Private), Route Tables, IGW vs NAT Gateway. <br> - Understand Network ACLs vs Security Groups. | 22/09/2025 | 22/09/2025 | <https://aws.amazon.com/vpc/> |
| 3 | - **Practice:** Design and deploy a Custom VPC with a 2-tier architecture (Public Web layer, Private DB layer). <br> - **9:00 PM Team Meeting:** Discuss basic network architecture and security for the upcoming project. | 23/09/2025 | 23/09/2025 | Internal Team |
| 4 | - Research RDS: Multi-AZ, Read Replicas, Backup strategies. <br> - Research DynamoDB: NoSQL model, Partition Key, Sort Key. | 24/09/2025 | 24/09/2025 | <https://aws.amazon.com/rds/> |
| 5 | - **Practice:** Launch an RDS Instance (PostgreSQL) and connect via EC2. <br> - **AI Research:** Install and test the `pgvector` extension on PostgreSQL for vector storage. | 25/09/2025 | 25/09/2025 | GitHub pgvector |
| 6 | - Create DynamoDB tables and perform basic Put/Get Item operations. <br> - **9:00 PM Team Meeting:** Finalize Database strategy (Pinecone vs. RDS pgvector) balancing ease of use and cost. | 26/09/2025 | 26/09/2025 | Internal Team |
| 7 | - Summarize Networking & Database knowledge. <br> - Write Week 3 Worklog. | 27/09/2025 | 27/09/2025 | |

### Week 3 Achievements:

* **Networking (VPC):**
    * Successfully built a VPC network topology including Public/Private Subnets, Route Tables, and NAT Gateways.
    * Mastered Security Group configurations to secure traffic flow (e.g., restricting RDS access to only EC2 instances).

* **Database & AI Data:**
    * Successfully deployed RDS (PostgreSQL) and DynamoDB instances.
    * **Key Achievement:** Tested `pgvector` extension on PostgreSQL.
    * Evaluated trade-offs between **Pinecone** (Serverless, specialized) and **RDS + pgvector** (Unified stack), preparing for the RAG implementation decision in the upcoming project phase.

* **Teamwork:**
    * Aligned with the team on the foundational network architecture (VPC) to be ready for application deployment starting next week (Week 4 - Project Kick-off).