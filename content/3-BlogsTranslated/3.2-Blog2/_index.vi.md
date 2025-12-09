---
title: "Blog 2"
weight: 1
chapter: false
pre: " <b> 3.2. </b> "
---

##### *The Internet of Things on AWS – Official Blog* 

# Sự tuân thủ của các dịch vụ AWS IoT với Đạo luật Khả năng chống chịu mạng của Liên minh Châu Âu (EU CRA)


**Tác giả:** Syed Rehan | 01 Tháng 9, 2025 | [AWS IoT Core](https://aws.amazon.com/blogs/iot/category/internet-of-things/aws-iot-platform/), [AWS IoT Device Defender](https://aws.amazon.com/blogs/iot/category/internet-of-things/aws-iot-device-defender/), [AWS IoT Greengrass](https://aws.amazon.com/blogs/iot/category/internet-of-things/aws-greengrass/), [Best Practices](https://aws.amazon.com/blogs/iot/category/post-types/best-practices/), [Business Intelligence](https://aws.amazon.com/blogs/iot/category/business-intelligence/), [Customer Solutions](https://aws.amazon.com/blogs/iot/category/post-types/customer-solutions/), [Europe](https://aws.amazon.com/blogs/iot/category/regions/europe/), [Regions](https://aws.amazon.com/blogs/iot/category/regions/), [Security](https://aws.amazon.com/blogs/iot/category/security-identity-compliance/security/), [Security & Governance](https://aws.amazon.com/blogs/iot/category/business-intelligence/security-governance/), [Technical How-to](https://aws.amazon.com/blogs/iot/category/post-types/technical-how-to/), [Thought Leadership](https://aws.amazon.com/blogs/iot/category/post-types/thought-leadership/)

## Giới thiệu

Trong kỷ nguyên số hiện nay, vấn đề bảo mật và tuân thủ của Internet of Things (IoT) không ngừng phát triển. Đạo luật Khả năng chống chịu mạng của Liên minh Châu Âu ([European Union’s Cyber Resilience Act – EU CRA](https://digital-strategy.ec.europa.eu/en/policies/cyber-resilience-act)) đang định hình lại cách các nhà sản xuất, nhà phát triển và nhà cung cấp dịch vụ IoT tiếp cận công việc của mình.

Bài viết này phân tích ý nghĩa của CRA đối với khách hàng AWS IoT và các nhà sản xuất đang sử dụng thiết bị kết nối.

## Hiểu về tác động của EU CRA

Đạo luật CRA được ban hành vào ngày 10/12/2024. Các nghĩa vụ báo cáo lỗ hổng bảo mật sẽ có hiệu lực từ tháng 9/2026, trong khi các yêu cầu tuân thủ đầy đủ bắt đầu từ tháng 12/2027.

Đạo luật này yêu cầu đảm bảo an ninh mạng toàn diện cho các sản phẩm có yếu tố kỹ thuật số, nhằm giải quyết rủi ro ngày càng tăng do việc số hóa các sản phẩm vật lý và sự gia tăng của các cuộc tấn công mạng nhắm vào thiết bị kết nối.

Trước đây, nhiều sản phẩm IoT tiêu dùng và công nghiệp được phát triển mà thiếu các biện pháp bảo mật phù hợp. Với nguyên tắc “bảo mật theo thiết kế” (security-by-design) và “bảo mật theo mặc định” (security-by-default), CRA hướng tới việc tăng cường niềm tin, khả năng chống chịu và trách nhiệm giải trình trong suốt vòng đời sản phẩm.

## Phân loại sản phẩm theo CRA

Theo Phụ lục III và IV của [tài liệu quy định chính thức cho CRA của EU](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32024R2847) (2024/2847), các sản phẩm được phân loại dựa trên chức năng liên quan đến an ninh mạng và mức độ rủi ro tiềm ẩn, thay vì chỉ “rủi ro thấp” hay “tới hạn”.

Hệ thống phân loại gồm:

1.  **Sản phẩm quan trọng có yếu tố kỹ thuật số (phụ lục III):**
    * Sản phẩm loại I
    * Sản phẩm loại II
2.  **Sản phẩm tới hạn có yếu tố kỹ thuật số (phụ lục IV)**

Phân loại này phản ánh chức năng an ninh mạng và khả năng gây rủi ro của sản phẩm bao gồm tác động đến sức khỏe, an toàn hoặc tính bảo mật của người dùng hay sản phẩm khác. Các sản phẩm không nằm trong phạm vi các danh mục này vẫn phải tuân thủ quy định, do đó các tổ chức cần đánh giá kỹ luật [EU CRA](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32024R2847) để xác định phạm vi áp dụng.

**Ví dụ về phân loại sản phẩm (không đầy đủ):**

* **Sản phẩm loại I:**
    * Hệ thống quản lý mạng
    * Hạ tầng khóa công khai (PKI) và phần mềm phát hành chứng chỉ số
    * Giao diện mạng vật lý và ảo
    * Bộ định tuyến, modem, switch kết nối Internet
    * Vi xử lý hoặc vi điều khiển có chức năng bảo mật
    * Trợ lý ảo dùng trong nhà thông minh
    * Sản phẩm smart home có chức năng bảo mật
    * Đồ chơi kết nối Internet có tính năng tương tác hoặc theo dõi vị trí
    * Thiết bị đeo cá nhân (wearables) có tính năng bảo mật đặc biệt

* **Sản phẩm loại II:**
    * Hypervisor và hệ thống chạy container
    * Firewall, hệ thống phát hiện và ngăn chặn xâm nhập (IDS/IPS)
    * Vi xử lý và vi điều khiển chống giả mạo (tamper-resistant)

* **Sản phẩm quan trọng có yếu tố kỹ thuật số:**
    * Thiết bị phần cứng với security boxes
    * Gateway đo điện thông minh (smart meter) và thiết bị an ninh nâng cao
    * Thẻ thông minh (smartcards) hoặc các sản phẩm tương tự, có yếu tố bảo mật

## Các yêu cầu chính đối với nhà sản xuất sản phẩm có yếu tố kỹ thuật số

Tham khảo [tài liệu quy định chính thức của EU CRA](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32024R2847), chúng ta hãy xem xét kỹ hơn các yêu cầu.

1.  **Yêu cầu an ninh mạng thiết yếu (dựa trên phụ lục phần I)**
    * Sản phẩm phải được:
        * Phân phối không có lỗ hổng bảo mật đã biết hoặc có thể khai thác
        * Cấu hình an toàn mặc định (secure-by-default)
        * Bảo vệ chống truy cập trái phép thông qua xác thực và kiểm soát truy cập
        * Mã hóa dữ liệu khi lưu trữ (at rest) và khi truyền (in transit)
        * Ngăn chặn thao túng hoặc sửa đổi dữ liệu
        * Giới hạn xử lý dữ liệu ở mức cần thiết (data minimization)
        * Đảm bảo tính sẵn sàng của các chức năng thiết yếu
        * Thiết kế giảm bề mặt tấn công và tác động của sự cố
        * Ghi log và giám sát hoạt động nội bộ liên quan đến an ninh mạng
        * Cho phép xóa và truyền dữ liệu an toàn

2.  **Yêu cầu về xử lý lỗ hổng bảo mật (dựa trên phụ lục phần I, phần II)**
    * Nhà sản xuất phải:
        * Xác định và ghi nhận các lỗ hổng, bao gồm Danh mục vật liệu phần mềm (SBOM)
        * Khắc phục lỗ hổng kịp thời, thực hiện kiểm thử bảo mật định kỳ
        * Chia sẻ thông tin về các lỗ hổng đã vá
        * Triển khai chính sách công bố lỗ hổng có phối hợp (CVD)
        * Phân phối bản vá an toàn, miễn phí và không trì hoãn

3.  **Đánh giá hợp chuẩn và gắn nhãn**
    * Dấu CE là bắt buộc để chứng minh sản phẩm tuân thủ quy định.
    * Các sản phẩm tới hạn phải được đánh giá bởi tổ chức thẩm định độc lập (third-party conformity assessment).

4.  **Mốc thời gian tuân thủ**
    * Các nghĩa vụ chính: có hiệu lực từ 11/12/2027
    * Nghĩa vụ xử lý lỗ hổng và báo cáo sự cố: bắt đầu từ 11/09/2026

5.  **Báo cáo sự cố:**
    * Thực hiện thông qua nền tảng một cửa của [ENISA (Cơ quan An ninh mạng Liên minh Châu Âu)](https://www.enisa.europa.eu/)
    * Báo cáo lỗ hổng bị khai thác trong vòng 24 giờ kể từ khi phát hiện
    * Thông báo sự cố trong 72 giờ, báo cáo hoàn chỉnh trong vòng 1 tháng
    * Thông tin cho người dùng về sự cố và các biện pháp khắc phục

6.  **Quản lý vòng đời sản phẩm, nhà sản xuất cần đảm bảo:**
    * Cung cấp hỗ trợ ít nhất 5 năm (hoặc trong vòng đời dự kiến nếu ngắn hơn)
    * Lưu trữ bản cập nhật bảo mật ít nhất 10 năm kể từ ngày phát hành
    * Bảo quản tài liệu kỹ thuật và tuyên bố hợp chuẩn EU ít nhất 10 năm
    * Duy trì quy trình đảm bảo sản phẩm luôn phù hợp với quy định
    * Theo dõi và cập nhật đánh giá rủi ro an ninh mạng định kỳ
    * Đánh giá kỹ lưỡng thành phần bên thứ ba trước khi tích hợp
    * Thông báo rõ ràng thời điểm kết thúc hỗ trợ cho người dùng tại thời điểm mua hàng

## AWS và Đạo luật CRA

AWS cung cấp một bộ dịch vụ IoT toàn diện giúp khách hàng triển khai các biện pháp kỹ thuật cần thiết để đáp ứng yêu cầu tuân thủ an ninh mạng thiết yếu của CRA trên mọi danh mục sản phẩm.

### Lập kế hoạch tuân thủ

Các dịch vụ AWS IoT hỗ trợ doanh nghiệp đáp ứng các yêu cầu CRA trong khi chuẩn bị cho lộ trình triển khai quy định này.

**Bảo mật yêu cầu:**
* AWS IoT Core với chứng chỉ X.509 để xác thực và kiểm soát truy cập
* Mã hóa TLS 1.2 cho dữ liệu truyền qua mạng
* Chính sách AWS IoT (IoT Policies) để kiểm soát truy cập và bảo vệ dữ liệu
* AWS IoT Device Defender để giám sát và đánh giá an ninh liên tục
* AWS IoT Device Management để quản lý cập nhật firmware an toàn

**Xử lý lỗ hổng bảo mật yêu cầu:**
* Sử dụng AWS Security Hub và Amazon Detective để phát hiện lỗ hổng
* Amazon EventBridge tự động hóa quy trình phản ứng sự cố
* AWS IoT Device Defender để giám sát bảo mật liên tục
* Amazon Security Lake để lưu trữ và quản lý dữ liệu sự cố

### Ví dụ triển khai: Thiết bị điều nhiệt thông minh (Smart Thermostat – Loại I)

Việc triển khai thiết bị điều nhiệt thông minh thuộc Hạng I (Important Product) theo CRA có thể thực hiện như sau:

* **Cấp phát an toàn:** sử dụng AWS IoT Core Just-in-Time Registration (JITR) và AWS Secrets Manager để quản lý chứng chỉ.
* **Kiểm soát truy cập:** cấu hình qua AWS IoT Policies theo chủ đề dữ liệu.
* **Bảo vệ dữ liệu:** mã hóa bằng TLS 1.2, giới hạn quyền truy cập chủ đề, giám sát liên tục bằng AWS IoT Device Defender.
* **Quản lý vòng đời thiết bị:** thông qua AWS IoT Device Management, bao gồm cập nhật OTA có chữ ký số, quản lý phiên bản phần mềm và tuân thủ thời gian hỗ trợ tối thiểu 5 năm.
* **Xử lý lỗ hổng và sự cố:**
    * Giám sát chỉ số bảo mật với Device Defender
    * EventBridge điều phối sự kiện và cảnh báo
    * CloudWatch và SNS gửi thông báo tự động
    * AWS Lambda thực hiện hành động khắc phục (ví dụ: thu hồi chứng chỉ hoặc cô lập thiết bị)
* **Báo cáo sự cố:** thông qua EventBridge, lưu hồ sơ trong Security Lake để đảm bảo tính toàn vẹn và khả năng truy xuất.

**Quy trình hợp chuẩn gồm 5 bước:**

1.  Xác định phân loại sản phẩm (Loại I, II, Critical) và tài liệu hóa căn cứ.
2.  Tiến hành đánh giá hợp chuẩn.
3.  Duy trì tài liệu kỹ thuật trên AWS (đánh giá rủi ro, biện pháp bảo mật, kết quả kiểm thử, cấu hình bảo mật).
4.  Gắn nhãn CE sau khi đạt chuẩn và lưu trữ tài liệu trong hệ thống AWS.
5.  Theo dõi và duy trì tuân thủ định kỳ.

## Tác động của CRA đối với an ninh IoT trong tương lai

Đối với khách hàng AWS IoT, CRA không chỉ là một yêu cầu tuân thủ mà còn là cơ hội chiến lược để nâng cao thực hành bảo mật và xây dựng niềm tin người dùng thông qua các chứng nhận hợp chuẩn.

CRA loại trừ một số lĩnh vực đã có quy định riêng, ví dụ:
* Thiết bị y tế theo Medical Devices Regulation (MDR)
* Hệ thống ô tô theo Quy định (EU) 2019/2144

Các thiết bị kết nối khác đều nằm trong phạm vi CRA, phản ánh định hướng tăng cường bảo mật cho toàn bộ hệ sinh thái IoT châu Âu.

Việc tuân thủ CRA nên được xem là một khoản đầu tư vào chất lượng và năng lực cạnh tranh, giúp hình thành một hệ sinh thái IoT an toàn và đáng tin cậy hơn, mang lại lợi ích lâu dài cho cả nhà sản xuất lẫn người tiêu dùng.

## Kết luận

Khi các nhà sản xuất phải đối mặt với yêu cầu mới về an ninh mạng theo CRA, AWS IoT cung cấp nền tảng bảo mật vững chắc với:
* Các tính năng bảo mật tích hợp sẵn
* Cơ chế giám sát tự động
* Hệ thống tài liệu hóa toàn diện

Điều này giúp doanh nghiệp đáp ứng đầy đủ các yêu cầu của CRA, đồng thời chuyển tuân thủ từ thách thức thành lợi thế cạnh tranh.

Khi tiến tới mốc thực thi năm 2027, việc áp dụng sớm các tính năng bảo mật AWS IoT sẽ giúp doanh nghiệp xây dựng hạ tầng tuân thủ vững chắc, đáp ứng các yêu cầu về xử lý lỗ hổng, báo cáo sự cố, và quản lý vòng đời sản phẩm – qua đó nâng cao an ninh tổng thể và củng cố lòng tin khách hàng trong thị trường kết nối toàn cầu.

⚠️ **Lưu ý quan trọng:** Mặc dù các dịch vụ AWS hỗ trợ triển khai biện pháp kỹ thuật, khách hàng vẫn chịu trách nhiệm hoàn toàn trong việc đảm bảo tuân thủ đầy đủ quy định CRA, bao gồm phân loại sản phẩm, đánh giá hợp chuẩn, và duy trì tài liệu pháp lý.

Ngay cả khi sản phẩm không thuộc danh mục cụ thể, doanh nghiệp vẫn có thể phải tuân thủ CRA, vì vậy cần nghiên cứu kỹ luật để hiểu rõ phạm vi áp dụng đối với từng trường hợp.

## Tài liệu tham khảo

* [AWS IoT Security Best Practices](https://docs.aws.amazon.com/iot/latest/developerguide/security-best-practices.html)
* [European Union Cyber Resilience Act Overview](https://digital-strategy.ec.europa.eu/en/policies/cyber-resilience-act)
* [AWS IoT Zero Trust Workshop](https://catalog.us-east-1.prod.workshops.aws/workshops/1d50f8ef-5030-42c9-9488-a2187472c9e6/en-US)
* [Internet of Things (IoT) Lens](https://docs.aws.amazon.com/wellarchitected/latest/iot-lens/iot-lens.html)
* [AWS IoT Greengrass for Edge Compliance](https://docs.aws.amazon.com/greengrass/)
* [AWS Compliance Programs](https://aws.amazon.com/compliance/programs/)
* [AWS Security Hub](https://docs.aws.amazon.com/securityhub/latest/userguide/what-is-securityhub.html)
* [AWS Audit Manager](https://aws.amazon.com/audit-manager/)
* [AWS Security Checklist](https://d1.awsstatic.com/whitepapers/Security/AWS_Security_Checklist.pdf)
* [AWS Well-Architected Framework – Security Pillar](https://docs.aws.amazon.com/wellarchitected/latest/security-pillar/welcome.html)
* [AWS Cloud Adoption Framework – Security Perspective](https://docs.aws.amazon.com/whitepapers/latest/overview-aws-cloud-adoption-framework/security-perspective.html)
* [Encrypting Data at Rest](https://docs.aws.amazon.com/whitepapers/latest/navigating-gdpr-compliance/encrypt-data-at-rest.html)
* [Setup Just-in-Time Provisioning with AWS IoT Core](https://aws.amazon.com/blogs/iot/setting-up-just-in-time-provisioning-with-aws-iot-core/)
* [Get Started with AWS IoT Workshop](https://catalog.us-east-1.prod.workshops.aws/workshops/6d30487a-48e1-4631-b6bc-5602582800b5/en-US/)
* [AWS IoT Greengrass Workshop](https://catalog.workshops.aws/greengrass)
* [Regulation of European Parliament on horizontal cybersecurity requirements for products with digital elements](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32024R2847)
* [US Cyber Trust Mark](https://aws.amazon.com/blogs/iot/aws-iot-and-us-cyber-trust-mark/)
* [UNECE WP.29 and AWS IoT for Connected Vehicle Cybersecurity](https://aws.amazon.com/blogs/iot/securing-the-future-of-mobility-unece-wp-29-and-aws-iot-for-connected-vehicle-cybersecurity/)

## Về tác giả

|||
|---|---|
| <img src="/images/syed.png" class="img-responsive" style="max-width:150px; display:block; margin:auto;"> | [Syed Rehan](https://www.linkedin.com/in/iamsyed/) là Kiến trúc sư Sản phẩm Bảo mật Trí tuệ nhân tạo cấp cao tại Amazon Web Services (AWS), thuộc tổ chức AWS AI Solutions. <br> Là [tác giả nhiều cuốn sách](https://link.springer.com/search?new-search=true&query=&content-type=Book&dateFrom=&dateTo=&contributor=%22Syed+Rehan%22&sortBy=newestFirst) về An ninh mạng, Học máy và IoT, ông có kinh nghiệm chuyên sâu trong việc giúp khách hàng toàn cầu - từ startup đến doanh nghiệp lớn - xây dựng giải pháp IoT, ML và AI an toàn trên nền tảng AWS. <br> Syed thường xuyên hợp tác với các chuyên gia bảo mật, CISO, nhà phát triển và nhà lãnh đạo an ninh, nhằm thúc đẩy việc áp dụng các dịch vụ bảo mật AWS và nâng cao khả năng chống chịu mạng trong môi trường đám mây hiện đại.   |