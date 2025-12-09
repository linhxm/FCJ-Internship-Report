---
title: "Worklog Tuần 6"
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

### Mục tiêu tuần 6:

* **Làm chủ Kiến trúc Serverless:** Nắm vững cách xây dựng, triển khai và kích hoạt AWS Lambda functions thông qua Amazon API Gateway.
* **Migration (Di dời hệ thống):** Chuyển đổi toàn bộ logic AI/RAG từ môi trường cục bộ lên đám mây (Cloud).
* **Quản lý Dependencies:** Giải quyết bài toán thư viện Python nặng (LangChain, Pinecone) bằng Lambda Layers.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2 | - **Refactor Code:** Viết lại file `lambda_functions.py` theo chuẩn `lambda_handler` của AWS, tách biệt logic xử lý Tarot và Tử vi. <br> - Chuyển các cấu hình cứng (hardcoded) sang Biến môi trường (Environment Variables). | 13/10/2025 | 13/10/2025 | `lambda_functions.py` |
| 3 | - **Tạo Lambda Layers:** Đóng gói các thư viện nặng như `openai`, `pinecone-client`, `langchain` thành Layer để giảm dung lượng file code chính và tăng tốc độ khởi động (Cold start). | 14/10/2025 | 14/10/2025 | AWS Docs |
| 4 | - Triển khai Lambda Function: Upload code và gắn Layer. Tích hợp file `prompts_master.py` để đảm bảo AI giữ đúng vai trò "Thầy bói". <br> - Test thử nghiệm function trực tiếp trên AWS Console. | 15/10/2025 | 15/10/2025 | `prompts_master.py` |
| 5 | - Cấu hình **API Gateway**: Tạo REST API để làm cổng giao tiếp cho Frontend gọi xuống Lambda. <br> - Thiết lập cơ chế xác thực (API Key hoặc Cognito Authorizer) để bảo vệ API. | 16/10/2025 | 16/10/2025 | <https://aws.amazon.com/api-gateway/> |
| 6 | - **Tối ưu hiệu năng:** Điều chỉnh cấu hình Memory (tăng RAM cũng tăng CPU) và Timeout (xử lý RAG có thể mất >10s) cho Lambda để tránh lỗi ngắt giữa chừng. <br> - **21:00 Họp Team:** Demo API Endpoint cho team Backend và Frontend tích hợp. | 17/10/2025 | 17/10/2025 | Nội bộ nhóm |
| 7 | - Gỡ lỗi (Debug) các vấn đề phát sinh khi tích hợp (CORS, sai định dạng JSON). <br> - Viết Worklog tuần 6. | 18/10/2025 | 18/10/2025 | |

### Kết quả đạt được tuần 6:

* **Về Ứng dụng AI (Serverless):**
    * Đã chuyển đổi thành công logic từ file `lambda_function.py` và `lambda_functions.py` lên AWS Lambda.
    * Giải quyết triệt để vấn đề quản lý thư viện (Dependencies hell) bằng **Lambda Layers**.
    * Hệ thống AI hiện đã có thể truy cập từ Internet thông qua API Gateway, không còn chạy local nữa.

* **Về Tối ưu hóa:**
    * Đã cấu hình Timeout hợp lý (ví dụ: 30s-60s) để đảm bảo các tác vụ RAG phức tạp có đủ thời gian hoàn thành mà không lãng phí chi phí chờ đợi.

* **Về Teamwork:**
    * Đã cung cấp tài liệu API (Endpoint, Request/Response body) cho các thành viên khác để bắt đầu ghép nối hệ thống.