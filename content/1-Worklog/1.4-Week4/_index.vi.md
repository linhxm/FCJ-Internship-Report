---
title: "Worklog Tuần 4"
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

### Mục tiêu tuần 4:

* **Bảo mật & Giám sát:** Hoàn thiện lớp bảo mật hạ tầng và thiết lập hệ thống giám sát cảnh báo (CloudWatch) để kiểm soát chi phí và hiệu năng ngay từ đầu.
* **Khởi động dự án (Kick-off):** Thống nhất phạm vi tính năng (Scope), phân chia vai trò và quy trình làm việc nhóm.
* **AI Prototyping:** Xây dựng phiên bản AI chạy cục bộ (Local Prototype) để kiểm chứng logic RAG và Prompt Engineering cho tính năng Tarot/Chatbot.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2 | - Cấu hình **AWS CloudWatch Alarms** để giám sát Billing (tránh vượt ngân sách) và hiệu năng EC2/RDS. <br> - Kích hoạt **CloudTrail** để ghi lại nhật ký hoạt động (Audit logs) của tài khoản. | 29/09/2025 | 29/09/2025 | <https://aws.amazon.com/cloudwatch/> |
| 3 | - Chuẩn bị danh sách tính năng chi tiết: Tarot (1 lá/3 lá), Tử vi, Thần số học. <br> - **21:00 Họp Team:** Kick-off dự án, chốt Tech stack (BE: Lambda, DB: Pinecone/RDS) và quy trình Gitflow. | 30/09/2025 | 30/09/2025 | Nội bộ nhóm |
| 4 | - **Code AI:** Xây dựng script Python chạy local để giả lập quy trình rút bài Tarot và sinh lời giải đoán (sử dụng OpenAI API + Prompt templates). <br> - Thử nghiệm các kỹ thuật Prompt Engineering để AI đóng vai "Thầy bói" (Persona). | 01/10/2025 | 01/10/2025 | File `prompts.py` |
| 5 | - **Code RAG:** Tích hợp Pinecone vào script local để truy xuất ý nghĩa lá bài từ dữ liệu vector đã chuẩn bị tuần trước. <br> - Đánh giá độ chính xác của câu trả lời khi có và không có RAG. | 02/10/2025 | 02/10/2025 | Pinecone Docs |
| 6 | - Thiết kế logic cho **Chatbot**: Xác định rào chắn (Guardrails) để bot chỉ trả lời các câu hỏi tâm linh, từ chối câu hỏi ngoài lề. <br> - **21:00 Họp Team:** Phân chia task cụ thể trên Jira/Trello. Nhận role **AI Lead**. | 03/10/2025 | 03/10/2025 | Nội bộ nhóm |
| 7 | - Document lại luồng xử lý AI (AI Logic Flow) để team Backend nắm được cách tích hợp. <br> - Viết Worklog tuần 4. | 04/10/2025 | 04/10/2025 | |

### Kết quả đạt được tuần 4:

* **Về Hạ tầng & Quản lý:**
    * Đã thiết lập Dashboard giám sát hoạt động và cảnh báo chi phí trên AWS.
    * Đã thống nhất quy trình làm việc và chốt danh sách tính năng cho MVP (Minimum Viable Product).

* **Về AI & Ứng dụng (Local):**
    * Đã xây dựng thành công **Prototype AI chạy local**:
        * Input: Câu hỏi người dùng + Lá bài rút được.
        * Process: RAG (Pinecone) lấy ý nghĩa lá bài -> LLM (OpenAI) sinh lời khuyên.
        * Output: Câu trả lời mang văn phong tâm linh, huyền bí.
    * Đã xác định rõ phạm vi của Chatbot: Hạn chế trả lời các câu hỏi trùng lặp với chức năng gieo quẻ (VD: Chatbot không tự bói mà hướng dẫn user dùng chức năng bói).

* **Về Teamwork:**
    * Đã nhận role chính thức và các đầu việc liên quan đến AI/Data cho Sprint đầu tiên.