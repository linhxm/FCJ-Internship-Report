---
title: "Week 6 Worklog"
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

### Week 6 Objectives:

* **Master Serverless Architecture:** Proficiently build, deploy, and trigger AWS Lambda functions via Amazon API Gateway.
* **Migration:** Move the entire AI/RAG logic from the local environment to the Cloud.
* **Dependency Management:** Solve the challenge of heavy Python libraries (LangChain, Pinecone) using Lambda Layers.

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ---- | ---------- | --------------- | ------------------ |
| 2 | - **Code Refactoring:** Rewrite `lambda_functions.py` to adhere to the AWS `lambda_handler` standard, separating Tarot and Horoscope logic. <br> - Migrate hardcoded configurations to Environment Variables. | 13/10/2025 | 13/10/2025 | `lambda_functions.py` |
| 3 | - **Create Lambda Layers:** Package heavy libraries like `openai`, `pinecone-client`, and `langchain` into Layers to reduce deployment package size and improve Cold Start time. | 14/10/2025 | 14/10/2025 | AWS Docs |
| 4 | - Deploy Lambda Function: Upload code and attach Layers. Integrate `prompts_master.py` to ensure the AI maintains its "Fortune Teller" persona. <br> - Test functions directly on the AWS Console. | 15/10/2025 | 15/10/2025 | `prompts_master.py` |
| 5 | - Configure **API Gateway**: Create REST APIs as entry points for the Frontend to invoke Lambda. <br> - Set up authentication (API Key or Cognito Authorizer) to secure the API. | 16/10/2025 | 16/10/2025 | <https://aws.amazon.com/api-gateway/> |
| 6 | - **Performance Optimization:** Adjust Memory (more RAM = more CPU) and Timeout settings (RAG can take >10s) to prevent premature termination. <br> - **9:00 PM Team Meeting:** Demo API Endpoints for Backend and Frontend integration. | 17/10/2025 | 17/10/2025 | Internal Team |
| 7 | - Debug integration issues (CORS, malformed JSON). <br> - Write Week 6 Worklog. | 18/10/2025 | 18/10/2025 | |

### Week 6 Achievements:

* **AI Application (Serverless):**
    * Successfully migrated logic from `lambda_function.py` and `lambda_functions.py` to AWS Lambda.
    * Solved dependency management issues using **Lambda Layers**.
    * The AI system is now accessible via the Internet through API Gateway, moving away from localhost.

* **Optimization:**
    * Configured appropriate Timeouts (e.g., 30s-60s) to ensure complex RAG tasks complete successfully without unnecessary cost overruns.

* **Teamwork:**
    * Provided API documentation (Endpoints, Request/Response body) to team members for system integration.