---
title: "Blog 3"
weight: 1
chapter: false
pre: " <b> 3.3. </b> "
---

##### *AWS Security Blog* 

# Amazon ngăn chặn chiến dịch “watering hole” do APT29 (Nga) thực hiện

**Tác giả:** CJ Moses | 29 Tháng 8, 2025 | [Announcements](https://aws.amazon.com/blogs/security/category/post-types/announcements/), [Intermediate (200)](https://aws.amazon.com/blogs/security/category/learning-levels/intermediate-200/), [Security, Identity & Compliance](https://aws.amazon.com/blogs/security/category/security-identity-compliance/), [Thought Leadership](https://aws.amazon.com/blogs/security/category/post-types/thought-leadership/)

Amazon vừa phát hiện và triệt phá một chiến dịch watering hole do APT29 (còn gọi là Midnight Blizzard), nhóm đe dọa có liên hệ với Cơ quan Tình báo Đối ngoại Nga (SVR), đứng sau. Cuộc điều tra cho thấy chiến dịch mang tính cơ hội (opportunistic), lợi dụng các website hợp pháp bị xâm phạm để chuyển hướng (redirect) người truy cập đến hạ tầng độc hại. Ở đó, kẻ tấn công tìm cách đánh lừa người dùng cấp phép cho thiết bị do chúng kiểm soát thông qua luồng xác thực bằng mã thiết bị của Microsoft (Microsoft device code authentication flow). Cách tiếp cận này thể hiện sự thích nghi và mở rộng quy mô của APT29 nhằm mở rộng lưới thu thập tình báo.

## Chiến thuật đang tiến hóa của APT29

Chiến dịch hiện tại phù hợp với mô hình hoạt động mà chúng tôi từng quan sát:

* **10/2024:** [Amazon đã phá vỡ nỗ lực của APT29 sử dụng tên miền giả mạo](https://aws.amazon.com/blogs/security/amazon-identified-internet-domains-abused-by-apt29/) AWS để lừa người dùng tải tệp RDP trỏ đến hạ tầng do tác nhân kiểm soát.
* **06/2025:** Google Threat Intelligence Group [báo cáo](https://cloud.google.com/blog/topics/threat-intelligence/creative-phishing-academics-critics-of-russia) APT29 lừa đảo (phishing) nhắm vào giới học thuật và những người chỉ trích Nga bằng cách lạm dụng application-specific passwords (ASP).

Chiến dịch lần này tiếp tục tập trung vào thu thập thông tin định danh (credential harvesting) và thu thập tình báo, đồng thời tinh chỉnh kỹ thuật, thể hiện sự tiến hóa của APT29 qua khả năng:

1.  Xâm phạm website hợp pháp và ban đầu nhúng JavaScript được làm rối (obfuscated).
2.  Thích ứng hạ tầng nhanh khi bị gián đoạn.
3.  Trên hạ tầng mới, chuyển từ redirect bằng JavaScript sang redirect phía server.

## Chi tiết kỹ thuật

Amazon phát hiện hoạt động nhờ một phân tích (analytic) dành cho hạ tầng APT29, từ đó lần ra các tên miền do tác nhân kiểm soát. Điều tra tiếp cho thấy kẻ tấn công đã:

* Xâm phạm nhiều website hợp pháp, chèn JavaScript để chuyển hướng \~10% khách truy cập sang tên miền độc hại do chúng điều khiển.
* Các tên miền như `findcloudflare[.]com` giả mạo trang xác minh của Cloudflare để tạo vẻ hợp lệ.
* Mục tiêu cuối cùng là luồng xác thực mã thiết bị của Microsoft.

> ⮕ **Lưu ý:** Không có bất kỳ xâm phạm hệ thống AWS nào, và không ghi nhận ảnh hưởng trực tiếp tới các dịch vụ hay hạ tầng AWS.

### Kỹ thuật né tránh phát hiện

Phân tích mã đã tiết lộ các kỹ thuật né tránh phát hiện, bao gồm:

* Ngẫu nhiên hóa để chỉ chuyển hướng một tỷ lệ nhỏ người truy cập.
* Mã hóa base64 nhằm che giấu mã độc hại.
* Đặt cookie để tránh chuyển hướng lặp lại cùng một người dùng.
* Xoay vòng sang hạ tầng mới khi bị chặn.

![Blog3-1](/images/blog3-1.png) 
*(Hình minh họa trang bị xâm phạm – đã ẩn tên miền)*

## Hoạt động triệt phá của Amazon

Amazon cam kết bảo vệ an ninh Internet bằng việc chủ động săn tìm và vô hiệu hóa các tác nhân đe dọa tinh vi, đồng thời hợp tác với đối tác trong ngành và cộng đồng an ninh để chia sẻ tình báo và giảm thiểu rủi ro.

Ngay khi phát hiện chiến dịch, chúng tôi đã:

* Cô lập các EC2 instance bị ảnh hưởng.
* Phối hợp với Cloudflare và các nhà cung cấp khác để vô hiệu hóa tên miền của tác nhân.
* Chia sẻ thông tin liên quan với Microsoft.

Mặc dù kẻ tấn công chuyển sang hạ tầng mới, thậm chí rời AWS sang nhà cung cấp đám mây khác, nhóm chúng tôi vẫn theo dõi và gián đoạn liên tục. Sau can thiệp, chúng tôi ghi nhận chúng đăng ký thêm tên miền như `cloudflare[.]redirectpartners[.]com`, tiếp tục dụ nạn nhân đi vào luồng xác thực mã thiết bị của Microsoft.

## Khuyến nghị bảo vệ người dùng và tổ chức

Chúng tôi khuyến nghị các tổ chức thực hiện các biện pháp bảo vệ sau:

### Đối với người dùng cuối:

1.  Cảnh giác với các chuỗi chuyển hướng đáng ngờ, đặc biệt các trang giả mạo xác minh bảo mật.
2.  Xác minh tính xác thực của yêu cầu cấp phép thiết bị trước khi chấp thuận.
3.  Bật MFA cho mọi tài khoản (tương tự như AWS yêu cầu MFA cho tài khoản root).
4.  Cảnh giác với trang web yêu cầu copy–paste lệnh hoặc thao tác trong hộp thoại Windows Run (Win+R).
    * Điều này tương đồng kỹ thuật “ClickFix” đã được mô tả gần đây, nơi kẻ tấn công dụ người dùng chạy lệnh độc hại.

### Đối với quản trị viên CNTT:

1.  Tuân theo hướng dẫn bảo mật của Microsoft về device code auth flows; cân nhắc vô hiệu hóa nếu không cần thiết.
2.  Thực thi Conditional Access dựa trên mức tuân thủ thiết bị, vị trí, và yếu tố rủi ro.
3.  Ghi log & giám sát chặt chẽ sự kiện xác thực, đặc biệt là ủy quyền thiết bị mới.

## Chỉ số báo xâm nhập (IOCs)

* `findcloudflare[.]com`
* `cloudflare[.]redirectpartners[.]com`

### Mẫu code JavaScript

![Blog3-2](/images/blog3-2.png) 
*(Đoạn JS đã giải mã, đã loại bỏ tên miền bị xâm phạm: “`[removed_domain]`”)*

## Về tác giả

|||
|---|---|
| <img src="/images/moses.jpeg" class="img-responsive" style="max-width:150px; display:block; margin:auto;"> | **CJ Moses** là Giám đốc An ninh Thông tin CISO của Amazon Integrated Security. Ông lãnh đạo kỹ thuật và vận hành an ninh trên toàn Amazon, với sứ mệnh biến lợi ích của bảo mật trở thành con đường ít ma sát nhất cho các đơn vị kinh doanh của Amazon. CJ gia nhập Amazon từ 12/2007, từng đảm nhiệm nhiều vị trí, bao gồm Consumer CISO, AWS CISO, và từ 09/2023 là CISO của Amazon Integrated Security. <br> Trước đó, CJ phụ trách phân tích kỹ thuật các cuộc xâm nhập tại Cục Điều tra Liên bang (FBI) – Khối Tác chiến Không gian mạng, và từng là Đặc vụ tại Air Force Office of Special Investigations (AFOSI). Ông dẫn dắt nhiều cuộc điều tra xâm nhập máy tính mang tính nền tảng cho ngành an ninh mạng ngày nay. <br> CJ có bằng Khoa học Máy tính và Tư pháp Hình sự, đồng thời là tay đua SRO GT America hạng GT2. |

**TAGS:** [Security](https://aws.amazon.com/blogs/security/tag/security/), [Security Blog](https://aws.amazon.com/blogs/security/tag/security-blog/)