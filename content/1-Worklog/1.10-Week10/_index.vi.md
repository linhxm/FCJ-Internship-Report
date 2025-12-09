---
title: "Worklog Tuần 10"
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---

### Mục tiêu tuần 10:

* **Production Deployment:** Triển khai hạ tầng chính thức (Production Environment) bao gồm VPC, Security Groups và các Database instances.
* **Full Data Vectorization:** Xử lý và nạp toàn bộ dữ liệu từ các file dataset vào Cơ sở dữ liệu Vector (Pinecone/Neon).
* **Backend Logic Finalization:** Hoàn tất logic xử lý chính cho các tính năng Tarot và Tử vi trên môi trường Production.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2 | - **Setup Hạ tầng:** Triển khai VPC Production, cấu hình Security Groups chặt chẽ (chỉ cho phép API Gateway gọi Lambda, Lambda gọi DB) theo sơ đồ đã chốt. <br> - Thiết lập biến môi trường (Prod) cho Lambda. | 10/11/2025 | 10/11/2025 | AWS VPC |
| 3 | - **Xử lý Dữ liệu lớn:** Viết script chạy batch để vector hóa toàn bộ dữ liệu từ `dataset_v2.jsonl` (Tử vi), `dataset_v3.jsonl` (Thần số học) và `dataset_v4.jsonl` (Tarot). <br> - Đẩy dữ liệu vào Pinecone index (Prod). | 11/11/2025 | 11/11/2025 | Pinecone Docs |
| 4 | - **Merge Code:** Phối hợp với team để merge các nhánh tính năng (Feature branches) vào nhánh chính (Main). Giải quyết các xung đột code (Conflicts) trong `lambda_functions.py`. <br> - Chạy pipeline CI/CD để deploy bản build mới nhất. | 12/11/2025 | 12/11/2025 | GitHub Actions |
| 5 | - **Tối ưu RAG (Production):** Kiểm tra tốc độ truy xuất khi dữ liệu đã đầy đủ. Tinh chỉnh tham số `top_k` trong hàm `query_rag` để cân bằng giữa độ chính xác và tốc độ. <br> - Cập nhật `prompts_master.py` lần cuối để đảm bảo văn phong nhất quán. | 13/11/2025 | 13/11/2025 | `local_worker.py` |
| 6 | - **21:00 Họp Team:** Demo tính năng "Tử vi trọn đời" với dữ liệu đầy đủ. <br> - Rà soát lại các lỗi logic (Business Logic) trước khi bước vào tuần test tích hợp. | 14/11/2025 | 14/11/2025 | Nội bộ nhóm |
| 7 | - Backup cơ sở dữ liệu (Snapshot RDS/Export DynamoDB). <br> - Viết Worklog tuần 10. | 15/11/2025 | 15/11/2025 | |

### Kết quả đạt được tuần 10:

* **Về Hạ tầng:**
    * Môi trường Production đã sẵn sàng, tách biệt hoàn toàn với môi trường Dev/Test.
    * Hệ thống mạng và bảo mật đã được thiết lập theo đúng thiết kế High-Level Architecture (HLA).

* **Về Dữ liệu (Core AI):**
    * **100% Dữ liệu** từ các bộ dataset (`v2`, `v3`, `v4`) đã được làm sạch và đánh chỉ mục vào Vector DB. AI giờ đây có thể trả lời chi tiết về mọi lá bài Tarot và các cung hoàng đạo.
    * Logic RAG hoạt động mượt mà với lượng dữ liệu lớn.

* **Về Mã nguồn:**
    * Code base đã ổn định, các nhánh tính năng đã được hợp nhất (Merged) và sẵn sàng cho giai đoạn kiểm thử toàn diện (Integration Test) vào tuần sau.