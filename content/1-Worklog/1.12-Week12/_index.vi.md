---
title: "Worklog Tuần 12"
weight: 12
chapter: false
pre: " <b> 1.12. </b> "
---

### Mục tiêu tuần 12:

* **Tài liệu hóa (Documentation):** Hoàn thiện tài liệu kỹ thuật, hướng dẫn cài đặt và sơ đồ luồng dữ liệu (Data Flow) cho module AI.
* **Tổng duyệt & Demo:** Chuẩn bị Slide thuyết trình, quay video demo sản phẩm và chạy thử kịch bản báo cáo.
* **Bàn giao & Tổng kết:** Đóng gói source code, dọn dẹp tài nguyên thừa và đúc kết bài học kinh nghiệm (Retrospective).

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2 | - **Viết tài liệu kỹ thuật:** Cập nhật file `README.md` trên GitHub với hướng dẫn deploy chi tiết (bao gồm cách setup Secrets, chạy pipeline CI/CD). <br> - Vẽ lại biểu đồ luồng dữ liệu (Data Flow Diagram) chi tiết cho phần RAG để đưa vào báo cáo. | 24/11/2025 | 24/11/2025 | Nội bộ nhóm |
| 3 | - **Chuẩn bị Slide:** Soạn nội dung slide phần "AI Architecture & Challenges", nêu bật giải pháp dùng SQS để xử lý bất đồng bộ và Pinecone để tối ưu chi phí. <br> - Phối hợp với Frontend để quay video màn hình các tính năng chính (Tarot, Tử vi, Chatbot). | 25/11/2025 | 25/11/2025 | Slide mẫu của BTC |
| 4 | - **Dựng Video Demo:** Cắt ghép, lồng tiếng/phụ đề cho video demo sản phẩm. Đảm bảo show được khả năng trả lời tự nhiên của AI. <br> - **Tổng duyệt Team (Dry Run):** Chạy thử toàn bộ bài thuyết trình, canh thời gian và trả lời các câu hỏi phản biện giả định. | 26/11/2025 | 26/11/2025 | Công cụ edit video |
| 5 | - **Final Polish:** Rà soát lại giao diện lần cuối, đảm bảo không có lỗi chính tả hay lỗi hiển thị khi AI trả về kết quả dài. <br> - Kiểm tra lại các endpoint API trên Production để chắc chắn hệ thống đang sống (Live). | 27/11/2025 | 27/11/2025 | AWS Console |
| 6 | - **21:00 Báo cáo Cuối khóa:** Thuyết trình và Demo sản phẩm trực tiếp (Live Demo) trước Mentor/Ban giám khảo. <br> - **Team Retrospective:** Họp rút kinh nghiệm, đánh giá những điểm làm được và chưa được trong suốt 12 tuần. | 28/11/2025 | 28/11/2025 | Zoom/Meeting |
| 7 | - **Dọn dẹp tài nguyên:** Xóa các tài nguyên AWS không dùng đến (EC2 test, S3 bucket rác, Snapshot cũ) để tránh phát sinh chi phí sau dự án. <br> - Hoàn thiện Worklog tuần 12 và nộp báo cáo tổng kết. | 29/11/2025 | 29/11/2025 | AWS Billing |

### Kết quả đạt được tuần 12:

* **Về Sản phẩm:**
    * Ứng dụng Tâm linh tích hợp AI đã hoàn thiện 100% và chạy ổn định trên môi trường Production (AWS Serverless).
    * Video demo chất lượng cao, thể hiện rõ các tính năng nổi bật: RAG chính xác, Chatbot có hồn, hệ thống phản hồi nhanh.

* **Về Tài liệu & Tri thức:**
    * Bộ tài liệu kỹ thuật đầy đủ trên GitHub, giúp bất kỳ ai cũng có thể hiểu và tiếp tục phát triển dự án.
    * Sơ đồ kiến trúc (HLA) và Luồng dữ liệu (Data Flow) chuẩn chỉnh.

* **Tổng kết Hành trình:**
    * Đã hoàn thành xuất sắc vai trò **AI Engineer**: Từ việc không biết bắt đầu từ đâu với đống dữ liệu thô, đến nay đã xây dựng được một hệ thống RAG Serverless hoàn chỉnh, tự động hóa bằng CI/CD và tối ưu chi phí.