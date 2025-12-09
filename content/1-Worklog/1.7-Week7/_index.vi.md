---
title: "Worklog Tuần 7"
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Mục tiêu tuần 7:

* **Triển khai CI/CD:** Thiết lập quy trình Tích hợp và Triển khai liên tục (CI/CD) sử dụng **GitHub Actions** để tự động hóa việc update code cho Lambda.
* **DNS & CDN:** Cấu hình tên miền tùy chỉnh (Custom Domain) với **Route 53** và tăng tốc độ tải tài nguyên với **CloudFront**.
* **Quản lý Môi trường:** Thiết lập các biến môi trường (Environment Variables) bảo mật trong quá trình deploy.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2 | - **Thiết lập GitHub Actions:** Viết file workflow `.yml` để tự động hóa các bước: Checkout code, cài đặt Python dependencies, và deploy lên AWS Lambda khi có commit vào nhánh `main`. <br> - Cấu hình **GitHub Secrets** để lưu trữ an toàn các khóa bí mật (AWS Credentials, Pinecone API Key, Neon DB URL). | 20/10/2025 | 20/10/2025 | Docs GitHub Actions |
| 3 | - **Test Pipeline:** Chạy thử nghiệm pipeline CI/CD với file `lambda_functions.py`. Kiểm tra xem code mới có được cập nhật tự động trên AWS Console hay không. <br> - Xử lý lỗi phân quyền IAM cho GitHub Actions Runner (cần quyền update Lambda code). | 21/10/2025 | 21/10/2025 | AWS IAM |
| 4 | - **Cấu hình Route 53:** Đăng ký/Cấu hình tên miền (Hosted Zone) cho API của dự án (ví dụ: `api.tamlinh.com`). <br> - Trỏ bản ghi DNS (A Record/Alias) về API Gateway. | 22/10/2025 | 22/10/2025 | <https://aws.amazon.com/route53/> |
| 5 | - **Cấu hình CloudFront:** Tạo Distribution để phân phối (CDN) cho các tài nguyên tĩnh như hình ảnh lá bài Tarot (đã lưu ở S3) nhằm giảm độ trễ tải ảnh cho người dùng cuối. <br> - Cấu hình SSL/TLS Certificate (ACM) để kích hoạt HTTPS. | 23/10/2025 | 23/10/2025 | <https://aws.amazon.com/cloudfront/> |
| 6 | - **21:00 Họp Team:** Demo quy trình "One-click Deploy" (chỉ cần push code là xong). Hướng dẫn các thành viên khác cách xem log build trên GitHub. <br> - Thống nhất quy tắc đặt tên branch và quy trình Merge Request (MR). | 24/10/2025 | 24/10/2025 | Nội bộ nhóm |
| 7 | - Rà soát lại bảo mật của Pipeline (đảm bảo không lộ Key trong log). <br> - Viết Worklog tuần 7. | 25/10/2025 | 25/10/2025 | |

### Kết quả đạt được tuần 7:

* **Về Quy trình (DevOps):**
    * Đã xây dựng thành công pipeline **CI/CD với GitHub Actions**. Từ giờ, việc cập nhật logic AI (như sửa prompt trong `prompts_master.py`) chỉ mất vài giây để push code và hệ thống tự động deploy.
    * Loại bỏ hoàn toàn rủi ro sai sót do thao tác thủ công (manual deployment).
    * Bảo mật hóa các thông tin nhạy cảm (API Keys) bằng GitHub Secrets thay vì hardcode trong file.

* **Về Hạ tầng mạng:**
    * API đã có tên miền chuyên nghiệp, dễ nhớ và được bảo mật bằng SSL.
    * Tốc độ tải ảnh bài Tarot và tài nguyên tĩnh tăng đáng kể nhờ CloudFront caching.