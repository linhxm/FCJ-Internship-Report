---
title: "Worklog Tuần 9"
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

### Mục tiêu tuần 9:

* **Scheduled Tasks (Tác vụ định kỳ):** Triển khai tính năng "Tử vi hằng ngày" tự động gửi email cho người dùng sử dụng **Amazon EventBridge** và **Amazon SES**.
* **Security & Identity (Bảo mật & Định danh):** Tích hợp **Amazon Cognito** để quản lý người dùng và **AWS Secrets Manager** để bảo vệ các API Key nhạy cảm.
* **Architecture Finalization:** Hoàn thiện và chốt Sơ đồ kiến trúc hệ thống cấp cao (HLA).

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2 | - **Cấu hình Cognito:** Tạo User Pool để quản lý đăng ký/đăng nhập cho ứng dụng, tích hợp với API Gateway Authorizer. <br> - **Bảo mật:** Chuyển các API Key (OpenAI, Pinecone) từ biến môi trường sang **AWS Secrets Manager** để tăng cường bảo mật. | 03/11/2025 | 03/11/2025 | AWS Cognito & Secrets Manager |
| 3 | - **Cấu hình SES:** Thiết lập Amazon SES (Simple Email Service), xác thực domain/email gửi đi để chuẩn bị cho tính năng gửi thông báo. <br> - Viết hàm `send_email` trong `lambda_functions.py` tích hợp với SES. | 04/11/2025 | 04/11/2025 | <https://aws.amazon.com/ses/> |
| 4 | - **Tạo Cron Job:** Cấu hình **EventBridge Scheduler** để kích hoạt Lambda `DailyEmailJob` vào 6:00 sáng mỗi ngày. <br> - Cập nhật `prompts_master.py` thêm mẫu prompt cho "Dự báo ngày mới". | 05/11/2025 | 05/11/2025 | AWS EventBridge |
| 5 | - **Test tích hợp:** Kiểm tra luồng: EventBridge -> Lambda -> RAG (lấy vận hạn) -> SES (gửi mail). Đảm bảo email không bị rơi vào Spam. | 06/11/2025 | 06/11/2025 | Nội bộ nhóm |
| 6 | - **21:00 Họp Team:** Trình bày Sơ đồ kiến trúc hoàn chỉnh (đã cập nhật SQS, EventBridge, SES, Cognito) để team duyệt lần cuối. <br> - Thảo luận về kịch bản Demo cho tuần cuối. | 07/11/2025 | 07/11/2025 | Nội bộ nhóm |
| 7 | - Rà soát lại toàn bộ quyền IAM (Least Privilege) cho các dịch vụ mới thêm vào. <br> - Viết Worklog tuần 9. | 08/11/2025 | 08/11/2025 | |

### Kết quả đạt được tuần 9:

* **Về Tính năng:**
    * Tính năng **"Tử vi hằng ngày"** đã hoạt động tự động hoàn toàn: Hệ thống tự động thức dậy vào 6h sáng, tính toán vận hạn và gửi email cho người dùng mà không cần can thiệp thủ công.
    * Hệ thống xác thực người dùng (AuthN/AuthZ) đã được kiện toàn với Cognito.

* **Về Bảo mật:**
    * Loại bỏ hoàn toàn việc lưu trữ API Key trong code hoặc biến môi trường không an toàn nhờ **Secrets Manager**.

* **Về Tài liệu:**
    * Sơ đồ kiến trúc (Architecture Diagram) đã được cập nhật đầy đủ các thành phần mới (EventBridge, SES, Cognito) và khớp với thực tế triển khai.