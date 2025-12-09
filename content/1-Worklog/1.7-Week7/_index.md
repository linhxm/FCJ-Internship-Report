---
title: "Week 7 Worklog"
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Week 7 Objectives:

* **CI/CD Implementation:** Establish a Continuous Integration/Continuous Deployment pipeline using **GitHub Actions** to automate Lambda code updates.
* **DNS & CDN:** Configure custom domains with **Route 53** and accelerate content delivery using **CloudFront**.
* **Environment Management:** Securely manage environment variables during the deployment process.

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ---- | ---------- | --------------- | ------------------ |
| 2 | - **Setup GitHub Actions:** Write `.yml` workflow files to automate steps: Checkout code, install Python dependencies, and deploy to AWS Lambda upon push to `main`. <br> - Configure **GitHub Secrets** to securely store credentials (AWS Credentials, Pinecone API Key, Neon DB URL). | 20/10/2025 | 20/10/2025 | GitHub Actions Docs |
| 3 | - **Pipeline Testing:** Test the CI/CD pipeline with `lambda_functions.py`. Verify that code changes are automatically reflected in the AWS Console. <br> - Resolve IAM permission issues for the GitHub Actions Runner (ensure permission to update Lambda code). | 21/10/2025 | 21/10/2025 | AWS IAM |
| 4 | - **Configure Route 53:** Register/Configure a Hosted Zone for the project API (e.g., `api.tamlinh.com`). <br> - Point DNS records (A Record/Alias) to the API Gateway. | 22/10/2025 | 22/10/2025 | <https://aws.amazon.com/route53/> |
| 5 | - **Configure CloudFront:** Create a Distribution to serve static assets like Tarot card images (stored in S3) via CDN to reduce latency for end-users. <br> - Setup SSL/TLS Certificate (ACM) to enable HTTPS. | 23/10/2025 | 23/10/2025 | <https://aws.amazon.com/cloudfront/> |
| 6 | - **9:00 PM Team Meeting:** Demo the "One-click Deploy" process. Guide team members on how to check build logs on GitHub. <br> - Agree on branch naming conventions and Merge Request (MR) processes. | 24/10/2025 | 24/10/2025 | Internal Team |
| 7 | - Security review of the Pipeline (ensure no Keys are exposed in logs). <br> - Write Week 7 Worklog. | 25/10/2025 | 25/10/2025 | |

### Week 7 Achievements:

* **DevOps Process:**
    * Successfully built a **CI/CD pipeline with GitHub Actions**. Updating AI logic (like tweaking prompts in `prompts_master.py`) now only requires a code push for automatic deployment.
    * Eliminated risks associated with manual deployment errors.
    * Secured sensitive information (API Keys) using GitHub Secrets instead of hardcoding.

* **Network Infrastructure:**
    * The API is now accessible via a professional, easy-to-remember domain secured with SSL.
    * Significant improvement in loading speed for Tarot images and static assets due to CloudFront caching.