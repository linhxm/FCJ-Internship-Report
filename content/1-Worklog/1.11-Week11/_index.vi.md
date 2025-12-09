---
title: "Worklog Tuần 11"
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---

### Mục tiêu tuần 11:

* **Kiểm thử tích hợp (Integration Testing):** Đảm bảo Frontend kết nối mượt mà với Backend (API Gateway/Lambda) và hệ thống AI phản hồi chính xác dưới áp lực truy cập.
* **Tinh chỉnh AI (AI Polish):** Cải thiện giọng văn, văn phong của AI để tạo cảm giác huyền bí, thấu cảm (Persona Tuning).
* **Tối ưu hóa chi phí (Cost Optimization):** Rà soát và điều chỉnh tài nguyên AWS/Pinecone để giảm chi phí vận hành.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2 | - **Load Testing:** Sử dụng công cụ (như Locust/JMeter) để giả lập lượng truy cập lớn vào API xem bói. Theo dõi CloudWatch để phát hiện điểm nghẽn (bottleneck). <br> - Xử lý các lỗi Timeout ở API Gateway khi AI suy nghĩ quá lâu. | 17/11/2025 | 17/11/2025 | AWS CloudWatch |
| 3 | - **Tinh chỉnh Prompt:** Dựa trên feedback test, cập nhật lại file `prompts_master.py` để AI không trả lời cụt lủn mà đưa ra lời khuyên sâu sắc hơn, đậm chất tâm linh. <br> - Thêm các ví dụ (Few-shot prompting) vào `prompts.py` để định hướng câu trả lời tốt hơn. | 18/11/2025 | 18/11/2025 | `prompts.py` |
| 4 | - **Tối ưu hóa Code:** Rà soát lại `lambda_functions.py`, loại bỏ các đoạn log thừa (print statements) để tiết kiệm dung lượng lưu trữ CloudWatch Logs. <br> - Cấu hình Caching trên API Gateway cho các yêu cầu giống nhau (ví dụ: Tử vi cùng một ngày của cùng một cung). | 19/11/2025 | 19/11/2025 | AWS API Gateway |
| 5 | - **Tối ưu chi phí:** Giảm Pod size của Pinecone hoặc chuyển sang Serverless mode để tiết kiệm chi phí khi không sử dụng. <br> - Rà soát lại dung lượng bộ nhớ (Memory) của Lambda, giảm xuống mức tối thiểu cần thiết để chạy được code `local_worker.py` logic. | 20/11/2025 | 20/11/2025 | Pinecone Console |
| 6 | - **21:00 Họp Team:** Chốt phiên bản sản phẩm (Code Freeze). Không thêm tính năng mới, chỉ sửa lỗi (Bug fix). <br> - Phân công người quay video demo và người viết slide thuyết trình. | 21/11/2025 | 21/11/2025 | Nội bộ nhóm |
| 7 | - Kiểm tra lại toàn bộ luồng CI/CD trên GitHub Actions để đảm bảo bản deploy cuối cùng không bị lỗi. <br> - Viết Worklog tuần 11. | 22/11/2025 | 22/11/2025 | |

### Kết quả đạt được tuần 11:

* **Về Hiệu năng & Ổn định:**
    * Hệ thống chịu tải tốt với 500+ concurrent requests giả lập.
    * Giải quyết triệt để vấn đề độ trễ (latency) bằng caching và tối ưu hóa code Python.

* **Về Chất lượng AI:**
    * AI ("Thầy bói ảo") giờ đây có giọng văn tự nhiên, huyền bí và nhất quán nhờ bộ prompt đã được tinh chỉnh kỹ lưỡng trong `prompts_master.py`.
    * Các trường hợp biên (như người dùng hỏi sai chủ đề) được xử lý khéo léo.

* **Về Chi phí:**
    * Giảm được ~30% chi phí dự kiến hàng tháng nhờ tối ưu hóa tài nguyên Lambda và Vector DB.