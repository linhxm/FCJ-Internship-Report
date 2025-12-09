---
title: "Week 11 Worklog"
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---

### Week 11 Objectives:

* **Integration Testing:** Ensure seamless connectivity between Frontend and Backend (API Gateway/Lambda) and verify AI system accuracy under load.
* **AI Polish (Persona Tuning):** Refine the AI's tone and style to be more mystical and empathetic, aligning with the spiritual theme.
* **Cost Optimization:** Audit and adjust AWS/Pinecone resources to minimize operational costs.

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ---- | ---------- | --------------- | ------------------ |
| 2 | - **Load Testing:** Use tools (like Locust/JMeter) to simulate high traffic to the Fortune Telling API. Monitor CloudWatch to identify bottlenecks. <br> - Resolve Timeout issues in API Gateway caused by long AI inference times. | 17/11/2025 | 17/11/2025 | AWS CloudWatch |
| 3 | - **Prompt Tuning:** Based on test feedback, update `prompts_master.py` to ensure the AI provides deeper, more spiritual insights rather than short answers. <br> - Add Few-shot prompting examples to `prompts.py` to better guide the model's responses. | 18/11/2025 | 18/11/2025 | `prompts.py` |
| 4 | - **Code Optimization:** Review `lambda_functions.py` and remove excessive logging statements to save on CloudWatch Logs storage costs. <br> - Configure Caching on API Gateway for identical requests (e.g., Horoscope for the same sign on the same day). | 19/11/2025 | 19/11/2025 | AWS API Gateway |
| 5 | - **Cost Optimization:** Downscale Pinecone Pods or switch to Serverless mode to save costs during idle times. <br> - Tune Lambda Memory settings to the minimum required to execute the `local_worker.py` logic efficiently. | 20/11/2025 | 20/11/2025 | Pinecone Console |
| 6 | - **9:00 PM Team Meeting:** Code Freeze. No new features will be added; focus shifts entirely to bug fixing. <br> - Assign tasks for recording the demo video and creating the presentation slides. | 21/11/2025 | 21/11/2025 | Internal Team |
| 7 | - Final check of the CI/CD pipeline on GitHub Actions to ensure the final deployment is error-free. <br> - Write Week 11 Worklog. | 22/11/2025 | 22/11/2025 | |

### Week 11 Achievements:

* **Performance & Stability:**
    * The system successfully handled 500+ simulated concurrent requests.
    * Latency issues were resolved through caching strategies and Python code optimization.

* **AI Quality:**
    * The "Virtual Fortune Teller" now possesses a natural, mystical, and consistent persona thanks to refined prompts in `prompts_master.py`.
    * Edge cases (e.g., off-topic user questions) are handled gracefully.

* **Cost Efficiency:**
    * Achieved a ~30% reduction in projected monthly costs by optimizing Lambda resources and Vector DB configurations.