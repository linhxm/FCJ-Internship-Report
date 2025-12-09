---
title: "Worklog Tuần 3"
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

### Mục tiêu tuần 3:

* **Chuyên sâu về Networking:** Hiểu rõ và tự thiết kế được kiến trúc mạng ảo (VPC) an toàn, phân chia subnet hợp lý cho ứng dụng.
* **Làm chủ Cơ sở dữ liệu (Database):** Phân biệt và thực hành với RDS (SQL) và DynamoDB (NoSQL).
* **Chuẩn bị cho AI/RAG:** Nghiên cứu sâu về việc lưu trữ vector embeddings trên RDS (sử dụng pgvector) so với các giải pháp chuyên biệt như Pinecone.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2 | - Nghiên cứu lý thuyết VPC: CIDR, Subnets (Public/Private), Route Tables, Internet Gateway (IGW) vs NAT Gateway. <br> - Tìm hiểu về Network ACLs và Security Groups (Firewall). | 22/09/2025 | 22/09/2025 | <https://aws.amazon.com/vpc/> |
| 3 | - **Thực hành:** Thiết kế và triển khai một mô hình VPC Custom với kiến trúc 2 lớp (Web layer public, DB layer private). <br> - **21:00 Họp Team:** Thảo luận về kiến trúc mạng và bảo mật cơ bản cho dự án. | 23/09/2025 | 23/09/2025 | Nội bộ nhóm |
| 4 | - Nghiên cứu RDS: Các tính năng Multi-AZ, Read Replicas, Backup. <br> - Nghiên cứu DynamoDB: Mô hình NoSQL, Partition Key, Sort Key. | 24/09/2025 | 24/09/2025 | <https://aws.amazon.com/rds/> |
| 5 | - **Thực hành:** Khởi tạo RDS Instance (PostgreSQL) và kết nối từ EC2. <br> - **Nghiên cứu AI:** Cài đặt và thử nghiệm extension `pgvector` trên PostgreSQL để lưu trữ vector. | 25/09/2025 | 25/09/2025 | GitHub pgvector |
| 6 | - Tạo bảng DynamoDB và thực hiện các thao tác Put/Get Item cơ bản. <br> - **21:00 Họp Team:** Chốt phương án Database cho dự án (Dùng Pinecone cho nhanh hay tận dụng RDS pgvector để tiết kiệm chi phí). | 26/09/2025 | 26/09/2025 | Nội bộ nhóm |
| 7 | - Tổng hợp kiến thức về Networking & Database. <br> - Viết Worklog tuần 3. | 27/09/2025 | 27/09/2025 | |

### Kết quả đạt được tuần 3:

* **Về Networking (VPC):**
    * Đã hiểu và tự xây dựng được hệ thống mạng VPC với đầy đủ các thành phần: Public/Private Subnets, Route Tables, NAT Gateway.
    * Nắm vững cách cấu hình Security Group để chỉ cho phép traffic cần thiết đi qua (Ví dụ: Chỉ cho phép EC2 truy cập vào RDS).

* **Về Database & AI Data:**
    * Đã triển khai thành công RDS (PostgreSQL) và DynamoDB.
    * **Quan trọng:** Đã thử nghiệm extension `pgvector` trên PostgreSQL.
    * Đã có cơ sở để so sánh giữa việc dùng **Pinecone** (dễ dùng, serverless) và **RDS + pgvector** (quản lý tập trung, tối ưu nếu dự án đã dùng Postgres).

* **Về Teamwork:**
    * Đã thống nhất với nhóm về kiến trúc mạng cơ bản (VPC) để chuẩn bị deploy ứng dụng vào tuần sau (Tuần 4 - Khởi động dự án).