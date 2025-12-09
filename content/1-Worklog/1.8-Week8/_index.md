---
title: "Week 8 Worklog"
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Week 8 Objectives:

* **Decoupling:** Implement Amazon SQS and SNS to decouple application components, ensuring stability under high load.
* **Asynchronous Processing:** Shift AI inference logic (RAG) to a Queue-based model to prevent API Gateway timeouts.
* **Data Pivot:** Execute a strategic change in the Astrology data source to improve reading accuracy.

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ---- | ---------- | --------------- | ------------------ |
| 2 | - **Research SQS/SNS:** Understand Pub/Sub patterns and Queue types (Standard vs. FIFO). <br> - Practice: Create an SQS Queue and trigger a Lambda function via Event Source Mapping. | 27/10/2025 | 27/10/2025 | <https://aws.amazon.com/sqs/> |
| 3 | - **9:00 PM Team Meeting (Pivot Discussion):** Discuss changing the Astrology data source. Decided to switch from the old `dataset_v1.jsonl` to the more detailed `dataset_v2.jsonl` structure for deeper AI insights. <br> - Assess the impact of this data swap on the current RAG pipeline. | 28/10/2025 | 28/10/2025 | Internal Team |
| 4 | - **Architecture Update:** Redraw the system diagram on draw.io, adding SQS between API Gateway and the AI processing Lambda. <br> - Refactor Code: Split `lambda_handler` in `lambda_functions.py` into a producer (pushes to SQS) and a worker (processes AI). | 29/10/2025 | 29/10/2025 | `High_Level_System_Architecture.drawio.jpg` |
| 5 | - **New Data Processing:** Write scripts to clean and re-vectorize the new Astrology dataset (`dataset_v2.jsonl`) into Pinecone/Neon. <br> - Update `prompts_master.py` to accommodate new data fields (e.g., Rising Sign, Descendant). | 30/10/2025 | 30/10/2025 | `prompts_master.py` |
| 6 | - **Integration Debugging:** Fix connection issues between Chatbot and Vector DB caused by the async shift. <br> - **9:00 PM Team Meeting:** Demo the new flow: User Request -> Receive ID -> Background Processing -> Notification. | 31/10/2025 | 31/10/2025 | Internal Team |
| 7 | - Review cost implications of SQS and increased Lambda invocations (workers). <br> - Write Week 8 Worklog. | 01/11/2025 | 01/11/2025 | |

### Week 8 Achievements:

* **Architecture:**
    * Successfully implemented **Amazon SQS** as a buffer for heavy AI inference requests, preventing system overload.
    * Improved User Experience (UX): The app now responds immediately (returning a "Processing" status) instead of making users wait 30-60s for the AI.

* **Data Pivot:**
    * Successfully migrated to a higher-quality Astrology dataset (`dataset_v2.jsonl`), resulting in more detailed and authentic AI readings.
    * The RAG pipeline is stable with the new data structure.

* **Source Code:**
    * Optimized `lambda_functions.py` logic for asynchronous processing.