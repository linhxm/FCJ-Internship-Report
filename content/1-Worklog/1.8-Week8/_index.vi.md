---
title: "Worklog Tuần 8"
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Mục tiêu tuần 8:

* **Decoupling (Phân tách hệ thống):** Áp dụng Amazon SQS và SNS để tách rời các thành phần ứng dụng, đảm bảo tính ổn định khi chịu tải cao.
* **Xử lý Bất đồng bộ (Asynchronous):** Chuyển đổi logic xử lý AI (RAG Inference) sang cơ chế hàng đợi (Queue) để tránh timeout cho API Gateway.
* **Tái cấu trúc dữ liệu (Data Pivot):** Thay đổi chiến lược nguồn dữ liệu cho tính năng Tử vi để cải thiện độ chính xác.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2 | - **Nghiên cứu SQS/SNS:** Tìm hiểu mô hình Pub/Sub và Queue (Standard vs FIFO). <br> - Thực hành: Tạo SQS Queue và kích hoạt Lambda function từ sự kiện trong hàng đợi (Event Source Mapping). | 27/10/2025 | 27/10/2025 | <https://aws.amazon.com/sqs/> |
| 3 | - **21:00 Họp Team (Pivot Discussion):** Thảo luận về việc thay đổi nguồn dữ liệu Tử vi. Quyết định chuyển từ file `dataset_v1.jsonl` cũ sang cấu trúc mới chi tiết hơn trong `dataset_v2.jsonl` để AI trả lời sâu sắc hơn. <br> - Đánh giá ảnh hưởng của việc đổi data đến quy trình RAG hiện tại. | 28/10/2025 | 28/10/2025 | Nội bộ nhóm |
| 4 | - **Cập nhật Kiến trúc:** Vẽ lại sơ đồ hệ thống trên draw.io, bổ sung SQS vào giữa API Gateway và Lambda xử lý AI. <br> - Refactor code: Tách hàm `lambda_handler` trong `lambda_functions.py` thành 2 phần: 1 hàm nhận request đẩy vào SQS, 1 hàm worker đọc SQS để xử lý AI. | 29/10/2025 | 29/10/2025 | `High_Level_System_Architecture.drawio.jpg` |
| 5 | - **Xử lý Data mới:** Viết script làm sạch và vector hóa lại bộ dữ liệu Tử vi mới (`dataset_v2.jsonl`) đẩy vào Pinecone/Neon. <br> - Cập nhật `prompts_master.py` để tương thích với các trường dữ liệu mới (ví dụ: thêm thông tin Cung Mọc, Cung Lặn). | 30/10/2025 | 30/10/2025 | `prompts_master.py` |
| 6 | - **Debug tích hợp:** Xử lý lỗi mất kết nối giữa Chatbot và Vector DB khi chuyển sang mô hình bất đồng bộ. <br> - **21:00 Họp Team:** Demo luồng xử lý mới: User gửi yêu cầu -> Nhận ID -> Hệ thống xử lý ngầm -> User nhận thông báo khi xong. | 31/10/2025 | 31/10/2025 | Nội bộ nhóm |
| 7 | - Review lại chi phí phát sinh từ SQS và Lambda (do chạy nhiều worker). <br> - Viết Worklog tuần 8. | 01/11/2025 | 01/11/2025 | |

### Kết quả đạt được tuần 8:

* **Về Kiến trúc (Architecture):**
    * Đã triển khai thành công **Amazon SQS** để làm vùng đệm (buffer) cho các yêu cầu xử lý AI, giúp hệ thống không bị quá tải.
    * Cải thiện trải nghiệm người dùng (UX): App phản hồi tức thì (trả về trạng thái "Đang xử lý") thay vì bắt người dùng chờ AI suy nghĩ 30-60s.

* **Về Dữ liệu (Data Pivot):**
    * Chuyển đổi thành công sang nguồn dữ liệu Tử vi chất lượng cao hơn (`dataset_v2.jsonl`), giúp câu trả lời của AI chi tiết và "thật" hơn.
    * Pipeline RAG đã hoạt động ổn định với cấu trúc dữ liệu mới.

* **Về Mã nguồn:**
    * Code trong `lambda_functions.py` đã được tối ưu cho mô hình xử lý bất đồng bộ.