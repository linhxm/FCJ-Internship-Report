---
title: "Worklog Tuần 2"
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

### Mục tiêu tuần 2:

* **Nắm vững AWS Core Services:** Hiểu sâu và thực hành thành thạo các dịch vụ tính toán (EC2), lưu trữ (S3) và quản lý định danh (IAM).
* **Nghiên cứu công nghệ cho dự án:** Tìm hiểu và đánh giá các giải pháp Cơ sở dữ liệu Vector Serverless (Pinecone, Neon) để chuẩn bị cho bài toán RAG sau này.
* **Chuẩn bị tài nguyên:** Thiết lập môi trường làm việc và thu thập, xử lý sơ bộ dữ liệu thô (Tarot, Tử vi).

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2 | - Nghiên cứu lý thuyết IAM: Users, Groups, Roles, Policies để quản lý quyền truy cập. <br> - Thực hành: Cấu hình MFA cho tài khoản Root và tạo Admin User để bảo mật tài khoản. | 15/09/2025 | 15/09/2025 | <https://aws.amazon.com/iam/> |
| 3 | - Tìm hiểu chuyên sâu về S3: Các lớp lưu trữ (Storage Classes), Lifecycle Rules. <br> - Thu thập và upload bộ dữ liệu thô (Raw Data) về Tarot/Tử vi lên S3 để lưu trữ. | 16/09/2025 | 16/09/2025 | <https://aws.amazon.com/s3/> |
| 4 | - Nghiên cứu về EC2: Các loại Instance (T2, T3...), Security Groups, AMI. <br> - Cài đặt môi trường Python, các thư viện AI (LangChain, OpenAI) trên máy cục bộ để test logic. | 17/09/2025 | 17/09/2025 | <https://aws.amazon.com/ec2/> |
| 5 | - **Nghiên cứu AI:** So sánh ưu nhược điểm giữa RDS pgvector, Pinecone và Neon cho việc lưu trữ vector. <br> - Viết script Python nhỏ để test kết nối và đẩy dữ liệu mẫu lên Pinecone (Free tier). | 18/09/2025 | 18/09/2025 | Docs của Pinecone & Neon |
| 6 | - Tìm hiểu về quy trình CI/CD và lý do lựa chọn GitHub Actions. <br> - **21:00 Họp Team:** Báo cáo kết quả nghiên cứu Vector DB và thống nhất cấu trúc dữ liệu đầu vào. | 19/09/2025 | 19/09/2025 | Nội bộ nhóm |
| 7 | - Tối ưu hóa các đoạn code xử lý dữ liệu (làm sạch, format chuẩn JSONL). <br> - Tổng hợp kiến thức và viết Worklog tuần 2. | 20/09/2025 | 20/09/2025 | |

### Kết quả đạt được tuần 2:

* **Về hạ tầng AWS:**
    * Đã cấu hình bảo mật tài khoản AWS (IAM, MFA) theo đúng tiêu chuẩn (Best practices).
    * Hiểu rõ cơ chế hoạt động của S3 và đã lưu trữ an toàn bộ dữ liệu thô phục vụ cho dự án.
    * Nắm được cách khởi tạo và bảo mật cho EC2.

* **Về chuẩn bị cho dự án (AI/Data):**
    * Hoàn thành việc đánh giá các giải pháp Vector Database. Quyết định chọn **Pinecone** hoặc **Neon** cho giai đoạn đầu để tối ưu chi phí và tận dụng tính năng Serverless.
    * Đã chuẩn bị xong môi trường phát triển (Development Environment) với đầy đủ các thư viện cần thiết.
    * Thống nhất được với team về định dạng dữ liệu (Schema) cho các tính năng Tarot và Tử vi.

* **Về quy trình:**
    * Đã nắm được khái niệm cơ bản về CI/CD để sẵn sàng triển khai pipeline tự động trong các tuần tới.