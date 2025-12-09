---
title: "Các bài blogs đã dịch"
weight: 3
chapter: false
pre: " <b> 3. </b> "
---

### **[Blog 1 – Tổng hợp hàng tuần AWS](3.1-Blog1/)**  
Blog này tổng hợp các thông báo và cập nhật dịch vụ quan trọng nhất của AWS trong tuần. Nổi bật nhất là việc ra mắt các họ EC2 mới, bao gồm I8ge sử dụng Graviton4 với hiệu năng lưu trữ vượt trội và M8i/M8i-flex dựa trên Intel Xeon 6, mang lại hiệu năng/chi phí tối ưu hơn. AWS cũng mở rộng hỗ trợ IPv6 cho App Runner, Client VPN và RDS Data API.  

Ngoài ra, blog đề cập đến hai cải tiến lớn dành cho EC2 Mac Dedicated Hosts—Host Recovery và Reboot-based Maintenance—giúp tăng tính sẵn sàng và đơn giản hóa vận hành.  

Bài viết cũng điểm lại các sự kiện AWS sắp diễn ra, chương trình cộng đồng, tài nguyên học tập và các phân tích kỹ thuật liên quan, mang đến góc nhìn toàn diện về hệ sinh thái AWS trong tuần.

---

### **[Blog 2 – AWS IoT & Đạo luật Khả năng chống chịu mạng của EU (EU CRA)](3.2-Blog2/)**  
Bài viết phân tích sâu Đạo luật Cyber Resilience Act (CRA) của Liên minh Châu Âu, quy định mới nhằm tăng cường an ninh mạng cho các sản phẩm có yếu tố kỹ thuật số. Blog giải thích cách phân loại sản phẩm theo CRA, các yêu cầu bảo mật thiết yếu (secure-by-design, secure-by-default), nghĩa vụ vá lỗ hổng, quy trình báo cáo sự cố, thời hạn tuân thủ và yêu cầu lưu trữ tài liệu kỹ thuật.  

Bên cạnh phân tích pháp lý, bài viết mô tả cách AWS IoT cung cấp bộ công cụ hỗ trợ doanh nghiệp đáp ứng tiêu chuẩn CRA: xác thực bằng chứng chỉ X.509, mã hóa TLS, giám sát an ninh bằng Device Defender, cập nhật firmware an toàn qua OTA, và tự động hóa phản ứng sự cố sử dụng EventBridge và Lambda.  

Thông qua ví dụ về triển khai thermostat thông minh (smart thermostat), blog minh họa cách doanh nghiệp có thể xây dựng giải pháp IoT tuân thủ, an toàn trong suốt vòng đời sản phẩm, từ vận hành, giám sát đến quản lý bản vá.

---

### **[Blog 3 – Amazon ngăn chặn chiến dịch watering-hole của APT29](3.3-Blog3/)**  
Blog thuộc AWS Security Blog này mô tả cách Amazon phát hiện và triệt phá chiến dịch watering-hole tinh vi do APT29 thực hiện. Nhóm tấn công đã xâm phạm nhiều website hợp pháp, chèn mã JavaScript được làm rối nhằm chuyển hướng có chọn lọc người dùng đến hạ tầng độc hại, lợi dụng luồng xác thực mã thiết bị của Microsoft để đánh cắp thông tin định danh.  

Bài viết phân tích kỹ các kỹ thuật mà APT29 sử dụng: mã hóa payload bằng base64, ngẫu nhiên hóa tỷ lệ chuyển hướng để né phát hiện, thiết lập cookie để tránh lặp lại tấn công, và xoay vòng hạ tầng khi bị vô hiệu hóa. Amazon cũng chia sẻ IOC, cấu trúc hạ tầng độc hại và toàn bộ quá trình phối hợp với Cloudflare, Microsoft và các đối tác khác.  

Cuối cùng, blog đưa ra khuyến nghị thiết thực cho người dùng (bật MFA, cảnh giác khi cấp phép thiết bị, kiểm tra redirect bất thường) và cho quản trị viên (giám sát đăng nhập, triển khai Conditional Access, vô hiệu hóa device code auth khi không cần thiết) nhằm giảm thiểu nguy cơ bị tấn công.