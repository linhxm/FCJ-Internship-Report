---
title: "Worklog Tuần 5"
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

### Mục tiêu tuần 5:

* **AWS Scaling & Load Balancing:** Hiểu và thực hành cấu hình Application Load Balancer (ALB) và Auto Scaling Group (ASG) để đảm bảo hệ thống chịu tải tốt.
* **Kỹ thuật dữ liệu (Data Engineering):** Hoàn thiện quy trình nạp dữ liệu (Data Ingestion Pipeline) và xử lý các file dữ liệu thô thành dạng vector.
* **Tối ưu hóa RAG:** Tinh chỉnh chiến lược cắt dữ liệu (Chunking) và cập nhật các mẫu câu lệnh (Prompts) chuyên sâu cho từng chủ đề (Tình yêu, Sự nghiệp).

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2 | - **Thực hành AWS:** Cấu hình ALB với Target Groups và tạo Launch Template cho Auto Scaling Group. <br> - Test khả năng tự động thêm/bớt EC2 khi CPU tăng cao (Stress test). | 06/10/2025 | 06/10/2025 | <https://aws.amazon.com/autoscaling/> |
| 3 | - Xử lý hàng loạt (Batch processing) bộ dữ liệu `dataset_v4.jsonl` để tạo vector embeddings. <br> - **21:00 Họp Team:** Đánh giá chi phí dự kiến của Pinecone/Neon khi nạp lượng dữ liệu lớn. | 07/10/2025 | 07/10/2025 | Nội bộ nhóm |
| 4 | - Tối ưu chiến lược **Chunking**: Thử nghiệm độ dài đoạn văn bản tối ưu để AI truy xuất ngữ cảnh tốt nhất từ file `dataset_v3.jsonl`. <br> - Review lại logic xử lý trong `lambda_functions.py` để chuẩn bị cho việc migration lên cloud. | 08/10/2025 | 08/10/2025 | Pinecone Docs |
| 5 | - Tinh chỉnh hệ thống Prompts: Cập nhật file `prompts_master.py` với các kịch bản chuyên sâu cho Tình yêu và Sự nghiệp. <br> - Viết script Python để tự động hóa việc update embeddings khi có dữ liệu mới. | 09/10/2025 | 09/10/2025 | `prompts_master.py` |
| 6 | - Nghiên cứu sâu về **Metadata Filtering** trong Pinecone để giúp RAG lọc kết quả chính xác hơn (ví dụ: chỉ tìm trong bộ bài Tarot, không tìm trong Tử vi). <br> - **21:00 Họp Team:** Chốt phương án lưu trữ Vector cuối cùng. | 10/10/2025 | 10/10/2025 | Nội bộ nhóm |
| 7 | - Tổng hợp kiến thức về Scaling. <br> - Viết Worklog tuần 5. | 11/10/2025 | 11/10/2025 | |

### Kết quả đạt được tuần 5:

* **Về Hạ tầng AWS:**
    * Đã kiểm chứng thành công logic tự động mở rộng (Auto Scaling) để đảm bảo hệ thống không bị sập khi lượng truy cập tăng đột biến.
    * Hiểu rõ cách phân phối tải thông qua Application Load Balancer.

* **Về Dữ liệu & AI (Project):**
    * Toàn bộ cơ sở tri thức (Knowledge Base) từ các file `dataset_v2.jsonl`, `dataset_v3.jsonl`, `dataset_v4.jsonl` đã được đánh chỉ mục (Indexed) thành công vào Vector DB.
    * Đạt độ chính xác cao khi truy vấn RAG nhờ tối ưu hóa Metadata và Chunking.
    * Đã chuẩn bị sẵn sàng bộ source code (`lambda_functions.py`, `prompts_master.py`) để tuần sau đẩy lên AWS Lambda.

* **Về Chi phí:**
    * Đã xác nhận tính hiệu quả về chi phí của giải pháp Serverless Vector DB so với việc tự host trên EC2/RDS cho giai đoạn khởi đầu.