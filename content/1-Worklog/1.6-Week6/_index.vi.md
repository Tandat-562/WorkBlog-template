
---
title: "Worklog tuần 6"
date: 2026-05-30
weight: 1
chapter: false
pre: " <b> 1.6. </b> "

---

## Mục tiêu tuần 6

* Bắt đầu nghiên cứu Module 04 về các dịch vụ lưu trữ trên AWS.
* Hiểu sự khác nhau giữa Object Storage, Block Storage và File Storage.
* Nghiên cứu kiến trúc và cơ chế hoạt động của Amazon S3.
* Hiểu cấu trúc Bucket, Object, Object Key và Prefix trong Amazon S3.
* Tìm hiểu S3 Storage Classes và cách lựa chọn lớp lưu trữ theo nhu cầu truy cập.
* Tìm hiểu S3 Versioning, Lifecycle Rules và Access Point.
* Thực hành triển khai Static Website Hosting bằng Amazon S3.
* Tích hợp Amazon CloudFront để phân phối nội dung.
* Xây dựng kế hoạch sao lưu tập trung bằng AWS Backup.
* Nâng cao kỹ năng xử lý lỗi liên quan đến quyền truy cập, Versioning, Lifecycle và Backup.

---

## Các công việc thực hiện trong tuần

| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --- | --- | --- | --- |
| 1 | - Nghiên cứu Module 04-01 <br> - Tìm hiểu tổng quan các mô hình lưu trữ trên AWS <br> - Phân biệt Object Storage, Block Storage và File Storage <br> - Xác định trường hợp sử dụng của S3, EBS và EFS | 25/05/2026 | 25/05/2026 | https://www.youtube.com/watch?v=hsCfP0IxoaM&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=103 |
| 2 | - Nghiên cứu Module 04-02 <br> - Tìm hiểu Amazon S3, S3 Access Point và Storage Classes <br> - Phân tích cách lựa chọn lớp lưu trữ theo tần suất truy cập và chi phí | 26/05/2026 | 26/05/2026 | https://www.youtube.com/watch?v=_yunukwcAwc&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=104 |
| 3 | - Thực hành Lab 000057 <br> - Tạo S3 Bucket và Upload Object <br> - Cấu hình Static Website Hosting <br> - Kiểm tra Endpoint của Website | 27/05/2026 | 27/05/2026 | https://000057.awsstudygroup.com/vi/ |
| 4 | - Cấu hình S3 Versioning <br> - Thử nghiệm cập nhật và xóa Object <br> - Khôi phục phiên bản cũ <br> - Tìm hiểu Delete Marker và Version ID | 28/05/2026 | 28/05/2026 | https://000057.awsstudygroup.com/vi/ |
| 5 | - Tìm hiểu S3 Lifecycle Management <br> - Tạo Lifecycle Rule cho Object <br> - Phân tích chuyển đổi dữ liệu giữa các Storage Class <br> - Tìm hiểu Expiration và Noncurrent Version Expiration | 29/05/2026 | 29/05/2026 | https://www.youtube.com/watch?v=_yunukwcAwc&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=104 |
| 6 | - Thực hành AWS Backup <br> - Tạo Backup Vault và Backup Plan <br> - Cấu hình Backup Rule và Resource Assignment <br> - Theo dõi trạng thái Backup Job | 30/05/2026 | 30/05/2026 | https://000013.awsstudygroup.com/vi/ |
| 7 | - Cấu hình CloudFront Distribution cho nội dung S3 <br> - Ôn tập Module 04-01 và 04-02 <br> - Kiểm tra quyền truy cập Bucket <br> - Rà soát và xóa tài nguyên không còn sử dụng | 31/05/2026 | 31/05/2026 | https://000057.awsstudygroup.com/vi/ |

---

## Kết quả đạt được tuần 6

### 1. Hoàn thành phần đầu của Module 04

Các nội dung đã nghiên cứu:

| Nội dung | Kiến thức chính |
| --- | --- |
| Module 04-01 | Tổng quan các mô hình lưu trữ và dịch vụ lưu trữ trên AWS |
| Module 04-02 | Amazon S3, S3 Access Point và S3 Storage Classes |
| Bài thực hành | S3 Static Website, Versioning, Lifecycle, CloudFront và AWS Backup |

Sau tuần học, đã hiểu cách lựa chọn dịch vụ lưu trữ dựa trên loại dữ liệu, phương thức truy cập, độ bền, hiệu năng và chi phí.

---

### 2. Phân biệt các mô hình lưu trữ

#### Object Storage

Dữ liệu được lưu dưới dạng Object, mỗi Object gồm:

* Dữ liệu.
* Metadata.
* Object Key.
* Version ID nếu bật Versioning.

Amazon S3 là dịch vụ Object Storage, phù hợp với:

* Hình ảnh và video.
* Static Website.
* Backup.
* Log.
* Data Lake.
* Tệp ứng dụng.
* Nội dung phân phối qua CloudFront.

#### Block Storage

Dữ liệu được tổ chức thành các Block và thường được gắn trực tiếp vào máy chủ.

Amazon EBS phù hợp với:

* Root Volume của EC2.
* Database.
* File System.
* Ứng dụng cần độ trễ thấp.

#### File Storage

Dữ liệu được truy cập theo cấu trúc thư mục và tệp.

Amazon EFS hoặc Amazon FSx phù hợp với:

* Shared File System.
* Nhiều máy chủ cần truy cập chung.
* Ứng dụng sử dụng NFS hoặc SMB.

---

### 3. Kiến trúc Amazon S3

Cấu trúc cơ bản:

```text
AWS Account
    ↓
S3 Bucket
    ↓
Prefix hoặc Folder
    ↓
Object
```

Mỗi Object được xác định bằng:

* Bucket Name.
* Object Key.
* Version ID nếu Versioning được bật.

Ví dụ:

```text
Bucket: fcj-storage-lab
Object Key: images/architecture/aws-diagram.png
```

Hiểu rằng thư mục trong giao diện S3 thực chất được mô phỏng bằng Prefix trong Object Key.

---

### 4. Đặc điểm của Amazon S3

Amazon S3 cung cấp:

* Khả năng mở rộng dung lượng linh hoạt.
* Lưu trữ Object với độ bền cao.
* Truy cập dữ liệu qua API, Console, CLI hoặc SDK.
* Quản lý quyền bằng IAM Policy và Bucket Policy.
* Hỗ trợ Versioning.
* Hỗ trợ Lifecycle.
* Tích hợp với CloudFront.
* Hỗ trợ mã hóa dữ liệu.
* Phát Event khi Object được tạo, cập nhật hoặc xóa.

Các trường hợp sử dụng chính:

* Static Website.
* Backup và Archive.
* Data Lake.
* Lưu trữ tài liệu.
* Phân phối nội dung.
* Lưu Log.
* Lưu File Upload của ứng dụng.

---

### 5. S3 Storage Classes

| Storage Class | Trường hợp sử dụng |
| --- | --- |
| S3 Standard | Dữ liệu được truy cập thường xuyên |
| S3 Intelligent-Tiering | Không dự đoán được tần suất truy cập |
| S3 Standard-IA | Dữ liệu ít truy cập nhưng cần lấy nhanh |
| S3 One Zone-IA | Dữ liệu ít truy cập và có thể tái tạo |
| S3 Glacier Instant Retrieval | Dữ liệu lưu trữ dài hạn nhưng cần truy xuất nhanh |
| S3 Glacier Flexible Retrieval | Dữ liệu lưu trữ dài hạn, chấp nhận thời gian khôi phục |
| S3 Glacier Deep Archive | Dữ liệu lưu rất lâu và rất ít truy cập |

Việc lựa chọn Storage Class cần dựa trên:

* Tần suất truy cập.
* Thời gian lưu dữ liệu.
* Yêu cầu truy xuất.
* Khả năng tái tạo dữ liệu.
* Mức độ quan trọng.
* Chi phí lưu trữ và truy xuất.

---

### 6. S3 Intelligent-Tiering

S3 Intelligent-Tiering phù hợp khi chưa thể dự đoán chính xác tần suất truy cập dữ liệu.

Dịch vụ tự động theo dõi Access Pattern và chuyển Object giữa các tầng phù hợp.

Lợi ích:

* Giảm thao tác quản lý thủ công.
* Hạn chế việc chọn sai Storage Class.
* Phù hợp với dữ liệu có tần suất truy cập thay đổi.
* Có thể tối ưu chi phí mà không thay đổi ứng dụng.

---

### 7. S3 Access Point

S3 Access Point cung cấp một Endpoint riêng để truy cập Bucket.

Ví dụ:

```text
S3 Bucket
├── Access Point cho ứng dụng A
├── Access Point cho ứng dụng B
└── Access Point cho nhóm phân tích
```

Mỗi Access Point có thể có:

* Tên riêng.
* Access Point Policy.
* Cấu hình Public Access.
* Network Origin.
* Quyền truy cập riêng cho từng ứng dụng.

Lợi ích:

* Đơn giản hóa Bucket Policy.
* Tách quyền theo ứng dụng hoặc nhóm.
* Hỗ trợ quản lý Bucket có nhiều đối tượng sử dụng.
* Có thể giới hạn truy cập từ một VPC.

---

### 8. S3 Versioning

Versioning lưu nhiều phiên bản của cùng một Object.

Ví dụ:

```text
report.pdf
├── Version 1
├── Version 2
└── Version 3
```

Lợi ích:

* Khôi phục khi ghi đè nhầm.
* Khôi phục khi xóa nhầm.
* Theo dõi lịch sử thay đổi.
* Hỗ trợ bảo vệ dữ liệu trước lỗi người dùng hoặc ứng dụng.

Khi xóa Object trong Bucket đã bật Versioning, S3 thường tạo Delete Marker thay vì xóa ngay tất cả phiên bản.

Để khôi phục Object có thể:

* Xóa Delete Marker.
* Tải lại phiên bản cũ.
* Sao chép phiên bản cũ thành phiên bản hiện tại.

---

### 9. S3 Lifecycle Management

Lifecycle Rule giúp tự động quản lý dữ liệu theo tuổi của Object.

Ví dụ:

```text
Ngày 0: S3 Standard
   ↓
Ngày 30: S3 Standard-IA
   ↓
Ngày 90: S3 Glacier Flexible Retrieval
   ↓
Ngày 365: Xóa Object
```

Lifecycle có thể áp dụng cho:

* Current Version.
* Noncurrent Version.
* Object có Prefix cụ thể.
* Object có Tag cụ thể.
* Incomplete Multipart Upload.

Lợi ích:

* Tối ưu chi phí.
* Giảm thao tác thủ công.
* Tự động xử lý dữ liệu cũ.
* Hỗ trợ chính sách lưu trữ của tổ chức.

---

### 10. Static Website Hosting bằng Amazon S3

Đã thực hiện:

* Tạo Bucket.
* Upload HTML, CSS và hình ảnh.
* Bật Static Website Hosting.
* Cấu hình Index Document.
* Cấu hình Error Document.
* Kiểm tra Website Endpoint.
* Điều chỉnh quyền truy cập.

Luồng truy cập:

```text
Người dùng
    ↓
S3 Website Endpoint
    ↓
index.html
    ↓
CSS, JavaScript và hình ảnh
```

S3 Static Website phù hợp với:

* Portfolio.
* Landing Page.
* Tài liệu dự án.
* Website giới thiệu.
* Frontend không yêu cầu Server-Side Processing.

---

### 11. Tích hợp Amazon CloudFront

CloudFront được sử dụng để phân phối nội dung S3 đến người dùng thông qua hệ thống Edge Location.

Luồng xử lý:

```text
Người dùng
    ↓
CloudFront Edge Location
    ↓
CloudFront Cache
    ↓
Amazon S3 Origin
```

Lợi ích:

* Giảm độ trễ.
* Cache nội dung gần người dùng.
* Giảm số Request trực tiếp đến S3.
* Hỗ trợ HTTPS.
* Có thể giữ S3 Bucket ở chế độ Private.
* Hỗ trợ kiểm soát truy cập đến Origin.

---

### 12. Tổng quan AWS Backup

AWS Backup cung cấp cơ chế quản lý sao lưu tập trung.

Các thành phần chính:

```text
Backup Plan
    ↓
Backup Rule
    ↓
Resource Assignment
    ↓
Backup Job
    ↓
Recovery Point
    ↓
Backup Vault
```

Đã thực hành:

* Tạo Backup Vault.
* Tạo Backup Plan.
* Cấu hình lịch Backup.
* Chọn tài nguyên.
* Theo dõi Backup Job.
* Kiểm tra Recovery Point.
* Tìm hiểu Restore Job.

Lợi ích:

* Quản lý Backup tập trung.
* Tự động hóa lịch sao lưu.
* Áp dụng Retention Period.
* Theo dõi trạng thái Backup.
* Hỗ trợ nhiều dịch vụ AWS.

---

## Các lỗi thực tế đã xử lý

### 1. Không truy cập được S3 Static Website

Các nội dung được kiểm tra:

* Static Website Hosting đã được bật.
* Index Document đúng tên.
* Object đã được Upload.
* Bucket Policy.
* Block Public Access.
* URL Website Endpoint.
* Object Key có đúng chữ hoa và chữ thường.

---

### 2. Object bị Access Denied

Các nguyên nhân được kiểm tra:

* IAM Policy không cho phép.
* Bucket Policy không cho phép.
* Explicit Deny.
* Block Public Access.
* Object Ownership.
* KMS Key Policy.
* Truy cập sai Bucket hoặc Object Key.

---

### 3. Versioning không khôi phục được dữ liệu

Các nội dung được kiểm tra:

* Bucket đã bật Versioning trước khi Object được cập nhật hay chưa.
* Version ID.
* Delete Marker.
* Quyền `s3:GetObjectVersion`.
* Quyền `s3:ListBucketVersions`.

---

### 4. Lifecycle Rule không hoạt động như mong đợi

Các nguyên nhân được rà soát:

* Prefix hoặc Tag Filter không đúng.
* Object chưa đủ tuổi.
* Rule chưa Enabled.
* Minimum Storage Duration.
* Current Version và Noncurrent Version được cấu hình khác nhau.
* Quá trình chuyển đổi không diễn ra ngay lập tức.

---

### 5. Backup Job thất bại

Các thành phần được kiểm tra:

* IAM Role của AWS Backup.
* Resource Assignment.
* Backup Vault.
* Backup Window.
* Service Permission.
* Trạng thái tài nguyên.
* CloudWatch Event và SNS Notification.

---

## Kỹ năng đạt được

* Phân biệt Object, Block và File Storage.
* Thiết kế cấu trúc Bucket và Object Key.
* Lựa chọn S3 Storage Class.
* Tạo và quản lý S3 Access Point.
* Cấu hình S3 Versioning.
* Xây dựng Lifecycle Rule.
* Triển khai Static Website trên S3.
* Tích hợp CloudFront với S3.
* Tạo Backup Vault và Backup Plan.
* Xử lý lỗi truy cập và quản lý dữ liệu trên S3.

---

## Tự đánh giá

* Hiểu rõ hơn về kiến trúc Amazon S3.
* Có khả năng lựa chọn Storage Class theo nhu cầu.
* Biết cách sử dụng Versioning để bảo vệ Object.
* Có thể thiết lập Lifecycle Rule để tối ưu chi phí.
* Có thể triển khai Website tĩnh bằng Amazon S3.
* Hiểu vai trò của CloudFront trong phân phối nội dung.
* Có thể xây dựng Backup Plan cơ bản.
* Cải thiện kỹ năng kiểm tra IAM Policy, Bucket Policy và trạng thái Backup.

Nội dung cần cải thiện:

* Tìm hiểu sâu hơn về S3 Encryption.
* Thực hành S3 Access Point qua VPC.
* Tìm hiểu S3 Object Lock.
* Thực hành Cross-Region Replication.
* Thiết kế Lifecycle Rule cho dữ liệu có nhiều phiên bản.
* Kiểm thử Restore Job bằng AWS Backup.

---

## Kế hoạch tiếp theo

* Tiếp tục Module 04 với:

  * S3 Static Website và CORS.
  * S3 Access Control.
  * S3 Performance.
  * Amazon S3 Glacier.
  * AWS Snow Family.
  * AWS Storage Gateway.
  * VM Import/Export.
  * Disaster Recovery.
  * RTO và RPO.

* Tiếp tục thực hành:

  * VM Import/Export.
  * SMB File Share.
  * Storage Gateway.
  * Backup và Restore.
  * Hybrid Cloud Storage.

---

