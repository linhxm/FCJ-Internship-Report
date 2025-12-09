---
title: "Blog 1"
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---

##### *AWS News Blog*

# Tổng hợp hàng tuần AWS:
# Amazon EC2, Amazon Q Developer, cập nhật IPv6 và nhiều hơn nữa (01 Tháng 9, 2025)

**Tác giả:** Sébastien Stormacq | 01 Tháng 9, 2025 | [Amazon API Gateway](https://aws.amazon.com/blogs/aws/category/application-services/amazon-api-gateway-application-services/), [Amazon DynamoDB](https://aws.amazon.com/blogs/aws/category/database/amazon-dynamodb/), [Amazon EC2](https://aws.amazon.com/blogs/aws/category/compute/amazon-ec2/), [Amazon EC2 Mac Instances](https://aws.amazon.com/blogs/aws/category/compute/amazon-ec2-mac-instances/), [AWS Client VPN](https://aws.amazon.com/blogs/aws/category/networking-content-delivery/aws-vpn/aws-client-vpn/), [AWS Training and Certification](https://aws.amazon.com/blogs/aws/category/aws-training-and-certification/)

[audio.mp3](https://drive.google.com/file/d/1-J6dFFkW5mBkXELjP_mZSG3eboFqLZ1I/view?usp=sharing) - Giọng nói của Amazon Polly

Tuần này, bảng tin LinkedIn của tôi (Sébastien Stormacq) tràn ngập hình ảnh từ sự kiện AWS Heroes Summit được tổ chức tại Seattle. Thật ấm lòng khi thấy rất nhiều gương mặt quen thuộc cùng những thành viên mới trong cộng đồng Heroes quy tụ tại đây.

![Blog1-1](/images/blog1-1.jpg)

Đối với những ai chưa quen với [chương trình AWS Heroes](https://builder.aws.com/connect/community/heroes), đây là một sáng kiến toàn cầu nhằm vinh danh những cá nhân có đóng góp xuất sắc cho cộng đồng AWS. Các Heroes này chia sẻ kiến thức chuyên sâu thông qua việc sáng tạo nội dung, diễn thuyết tại sự kiện, tổ chức các buổi gặp mặt cộng đồng và đóng góp cho các dự án mã nguồn mở.

Sự kiện AWS Heroes Summit mang những lãnh đạo cộng đồng xuất sắc này lại với nhau, tạo nên một nền tảng độc đáo cho việc trao đổi kiến thức, kết nối và hợp tác. Với tư cách là người thường xuyên tương tác với Heroes trong các sáng kiến AWS, tôi (Sébastien Stormacq) luôn xem những hội nghị này là vô giá — nơi diễn ra các cuộc thảo luận kỹ thuật chuyên sâu, truy cập sớm vào lộ trình dịch vụ AWS, và trao đổi phản hồi trực tiếp với các nhóm phát triển dịch vụ.

Những hiểu biết và kết nối đạt được tại đây thường được chuyển hóa thành các nguồn tài nguyên và hướng dẫn tốt hơn cho toàn cộng đồng AWS.

## Các dịch vụ ra mắt tuần qua

Bên cạnh sự kiện truyền cảm hứng từ cộng đồng, dưới đây là những ra mắt mới của AWS trong tuần vừa qua mà tôi (Sébastien Stormacq) đặc biệt chú ý:

**1. AWS mở rộng hỗ trợ Internet Protocol v6 (IPv6) cho [AWS App Runner](https://aws.amazon.com/apprunner/), [AWS Client VPN](https://aws.amazon.com/vpn/), và [RDS Data API](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/data-api.html)**

* [AWS App Runner hiện hỗ trợ lưu lượng IPv6 inbound/outbound](https://aws.amazon.com/about-aws/whats-new/2025/08/aws-app-runner-expands-support-ipv6/) trên cả endpoint công khai và riêng tư.
* [AWS Client VPN hỗ trợ truy cập từ xa đến tài nguyên IPv6](https://aws.amazon.com/about-aws/whats-new/2025/08/aws-client-vpn-connectivity-ipv6-resources/) trong VPC, cho phép thiết lập kết nối VPN an toàn đến các workload kích hoạt IPv6.
* [RDS Data API hỗ trợ cấu hình dual-stack (IPv4 + IPv6)](https://aws.amazon.com/about-aws/whats-new/2025/08/rds-data-api-ipv6/) cho cơ sở dữ liệu Amazon Aurora, giúp tăng khả năng tương thích mạng.

⮕ Ba dịch vụ AWS mới nay đã hỗ trợ kết nối IPv6, giúp người dùng đáp ứng yêu cầu tuân thủ và loại bỏ nhu cầu chuyển đổi địa chỉ giữa IPv4 và IPv6.

**2. Hai họ máy chủ EC2 mới: I8ge (lưu trữ tối ưu) và M8i (đa dụng)**

AWS ra mắt I8ge instances, sử dụng bộ xử lý AWS Graviton4, mang lại hiệu năng tính toán cao hơn 60% so với thế hệ Graviton2 trước đó.

Các phiên bản này tích hợp AWS Nitro SSD thế hệ thứ ba, cung cấp hiệu năng lưu trữ theo thời gian thực cao hơn 55% trên mỗi TB và độ trễ I/O thấp hơn đáng kể.

Với dung lượng lên tới 120 TB và kích thước tối đa 48xlarge (gồm 2 tùy chọn metal), đây là dòng máy có mật độ lưu trữ cao nhất trong các instance Graviton-based.

Cùng với đó, AWS giới thiệu M8i và M8i-flex, sử dụng bộ xử lý Intel Xeon 6 tùy chỉnh, mang lại hiệu năng/chi phí tốt hơn 15% và băng thông bộ nhớ lớn hơn 2,5 lần so với thế hệ trước.

* M8i-flex phù hợp cho workload tổng quát (từ large đến 16xlarge).
* M8i dành cho ứng dụng chuyên biệt, được chứng nhận cho SAP, hỗ trợ 13 kích thước, gồm 2 tùy chọn bare metal và kích thước mới 96xlarge.

**3. Amazon EC2 Mac Dedicated Hosts hỗ trợ Host Recovery và Reboot-based Maintenance**

Hai tính năng mới giúp tăng độ sẵn sàng và đơn giản hóa bảo trì cho máy chủ EC2 Mac Dedicated Host:

* Host Recovery: tự động phát hiện sự cố phần cứng tiềm ẩn và di chuyển instance Mac sang host thay thế mà không gây gián đoạn đáng kể.
* Reboot-based Host Maintenance: tự động dừng và khởi động lại instance khi có sự kiện bảo trì định kỳ, giúp loại bỏ thao tác thủ công trong các đợt bảo trì theo lịch.

**4. Amazon Q Developer hỗ trợ quản trị MCP Admin Control**

Các quản trị viên giờ đây có thể bật/tắt tính năng MCP cho tất cả người dùng Amazon Q Developer trong tổ chức.

Khi bị vô hiệu hóa, người dùng không thể thêm hoặc khởi tạo bất kỳ MCP server nào, giúp doanh nghiệp kiểm soát chặt chẽ quyền truy cập và tuân thủ chính sách nội bộ.

## Các tin tức AWS khác

Ngoài những bản cập nhật trên, dưới đây là một số bài viết và dự án nổi bật mà bạn có thể quan tâm:

**1. [Mastering Amazon Q Developer with Rules](https://aws.amazon.com/blogs/devops/mastering-amazon-q-developer-with-rules/)**

Bài viết thú vị về tính năng “Rules” trong Amazon Q Developer — cho phép định nghĩa các quy tắc mã hóa (coding rules) một lần bằng file Markdown.

Q Developer sẽ tự động tuân thủ các quy tắc đó trong mọi tương tác, giúp duy trì tính nhất quán trong tiêu chuẩn mã mà không cần lặp lại hướng dẫn cho AI assistant.

Tính năng này tăng cường sự minh bạch, hiển thị rõ các quy tắc đang được áp dụng, và giúp giảm tải nhận thức cho nhóm phát triển.

**2. [Chiến lược chinh phục chứng chỉ AWS Certified Machine Learning – Specialty](https://aws.amazon.com/blogs/training-and-certification/strategies-for-excelling-across-all-four-exam-domains-of-the-aws-certified-machine-learning-specialty-certification/)**

Đội ngũ AWS Training & Certification chia sẻ hướng dẫn chuẩn bị cho chứng chỉ AWS Machine Learning – Specialty, bao gồm lộ trình, điều kiện tiên quyết, và chiến lược học hiệu quả cho cả người mới và người đã có chứng chỉ AWS khác.

Bài viết giúp xác định kỹ năng cần thiết để xây dựng giải pháp học máy (ML) trên AWS, đồng thời định hướng lộ trình phát triển chuyên môn cho kỹ sư dữ liệu và nhà nghiên cứu AI.

**3. [Amazon Prime Day 2025 – Thành công lịch sử nhờ sức mạnh AI và khả năng mở rộng của AWS](https://aws.amazon.com/blogs/aws/aws-services-scale-to-new-heights-for-prime-day-2025-key-metrics-and-milestones/)**

Như truyền thống sau mỗi kỳ Prime Day, AWS công bố số liệu cho thấy dịch vụ AWS đã mở rộng quy mô như thế nào để hỗ trợ một trong những sự kiện mua sắm lớn nhất thế giới.

Prime Day 2025 lập kỷ lục về doanh số và số lượng đơn hàng.

Đặc biệt, năm nay chứng kiến sự bùng nổ của trải nghiệm mua sắm do AI sinh sinh (Generative AI), với Alexa+, Rufus, và AI Shopping Guides hỗ trợ người dùng khám phá ưu đãi.

Con số ấn tượng:

* [Amazon DynamoDB](https://aws.amazon.com/dynamodb/) xử lý hàng chục nghìn tỷ API call, duy trì độ trễ chỉ vài mili-giây, đạt đỉnh 151 triệu yêu cầu/giây.
* [Amazon API Gateway](http://aws.amazon.com/apigateway) xử lý hơn 1 nghìn tỷ yêu cầu nội bộ, tăng 30% so với Prime Day 2024.

## Sự kiện AWS sắp tới

Hãy đánh dấu lịch và đăng ký tham gia các sự kiện AWS sắp diễn ra:

* [AWS Summits](https://aws.amazon.com/events/summits/?trk=ba8b32c9-8088-419f-9258-82e9375ad130&sc_channel=el) – Chuỗi sự kiện trực tiếp và trực tuyến miễn phí quy tụ cộng đồng điện toán đám mây để kết nối và học hỏi về AWS.
    * Địa điểm: [Toronto](https://aws.amazon.com/events/summits/toronto/?trk=a0051fdc-5b89-46a6-acfd-4881a84205f8&utm_custom=a0051fdc-5b89-46a6-acfd-4881a84205f8&sc_channel=el) (4/9), [Los Angeles](https://aws.amazon.com/events/summits/los-angeles/?trk=94c10076-a44d-4e29-a4a2-9a2f8d5e0238&utm_custom=94c10076-a44d-4e29-a4a2-9a2f8d5e0238&sc_channel=el) (17/9), [Bogotá](https://aws.amazon.com/es/events/summits/bogota/?utm_custom=258165ef-0951-435c-9dd0-3de2cde89563) (9/10).
* [AWS re:Invent 2025](https://reinvent.awsevents.com/?trk=ba8b32c9-8088-419f-9258-82e9375ad130&sc_channel=ell) – Hội nghị thường niên lớn nhất của AWS sẽ diễn ra tại Las Vegas, từ ngày 1–5/12/2025. [Danh mục sự kiện](https://registration.awsevents.com/flow/awsevents/reinvent2025/eventcatalog/page/eventcatalog??trk=ba8b32c9-8088-419f-9258-82e9375ad130&sc_channel=el) hiện đã được công bố – đừng bỏ lỡ cơ hội tham gia gặp gỡ cộng đồng AWS toàn cầu.
* [AWS Community Days](https://aws.amazon.com/events/community-day/?trk=e61dee65-4ce8-4738-84db-75305c9cd4fe&sc_channel=el&?trk=ba8b32c9-8088-419f-9258-82e9375ad130&sc_channel=el) – Sự kiện do cộng đồng dẫn dắt, gồm hội thảo, workshop và thực hành trực tiếp cùng chuyên gia AWS từ khắp nơi: [Adria](https://awscommunityadria.com/) (5/9), [Baltic](https://awsbaltic.eu/) (10/9), [Aotearoa](https://aws-community-day.nz/inperson.html) (18/9), [South Africa](https://www.awscommunityday.co.za/) (20/9), [Bolivia](https://www.facebook.com/awscommunitydaybolivia/) (20/9), [Portugal](https://awscommunityday.pt/) (27/9).

Ngoài ra, hãy tham gia [AWS Builder Center](https://builder.aws.com/) để học hỏi, xây dựng và kết nối cùng các nhà phát triển trong cộng đồng AWS – bao gồm nhiều [sự kiện ảo](https://aws.amazon.com/developer/events/?trk=ba8b32c9-8088-419f-9258-82e9375ad130&sc_channel=el) và [trực tiếp](https://aws.amazon.com/events/explore-aws-events/?trk=ba8b32c9-8088-419f-9258-82e9375ad130&sc_channel=el) dành riêng cho lập trình viên.

Đó là tất cả những tin nổi bật của tuần này!

Hẹn gặp lại bạn vào thứ Hai tuần tới với [AWS Weekly Roundup](https://aws.amazon.com/blogs/aws/tag/week-in-review/?trk=ba8b32c9-8088-419f-9258-82e9375ad130&sc_channel=el) tiếp theo!

[— seb](https://linktr.ee/sebsto)

TAGS: [Week in Review](https://aws.amazon.com/blogs/aws/tag/week-in-review/)

### Về tác giả

|||
| --- | --- |
| <img src="/images/seb.png" class="img-responsive" style="max-width:150px; display:block; margin:auto;"> | [Sébastien Stormacq](https://aws.amazon.com/blogs/aws/author/stormacq/) (Seb) bắt đầu viết code từ khi chạm vào chiếc Commodore 64 vào giữa thập niên 1980. Anh truyền cảm hứng cho cộng đồng builder AWS khai phá giá trị của điện toán đám mây bằng sự kết hợp giữa đam mê, tò mò, sáng tạo và tinh thần advocacy vì khách hàng. <br> Anh đặc biệt quan tâm đến kiến trúc phần mềm, công cụ dành cho lập trình viên và điện toán di động. |
