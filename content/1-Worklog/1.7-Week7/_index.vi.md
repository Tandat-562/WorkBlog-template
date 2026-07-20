
---
title: "Worklog tuần 7"
date: 2026-06-06
weight: 1
chapter: false
pre: " <b> 1.7. </b> "

---

## Mục tiêu tuần 7

* Hoàn thành các nội dung còn lại của Module 04.
* Tìm hiểu S3 Static Website, CORS và các phương pháp kiểm soát truy cập.
* Hiểu cơ chế tổ chức Object Key và tối ưu hiệu năng Amazon S3.
* Nghiên cứu Amazon S3 Glacier và quy trình khôi phục dữ liệu lưu trữ dài hạn.
* Tìm hiểu AWS Snow Family và các phương án di chuyển dữ liệu quy mô lớn.
* Thực hành VM Import/Export để di chuyển máy ảo giữa môi trường nội bộ và AWS.
* Triển khai AWS Storage Gateway theo mô hình Hybrid Cloud.
* Tạo SMB File Share kết nối với Amazon S3.
* Củng cố kiến thức về Backup, Restore, Disaster Recovery, RTO và RPO.
* Hoàn thiện kỹ năng xử lý lỗi liên quan đến lưu trữ, Migration và Hybrid Connectivity.

---

## Các công việc thực hiện trong tuần

| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --- | --- | --- | --- |
| 1 | - Nghiên cứu Module 04-03 <br> - Tìm hiểu S3 Static Website, CORS và Access Control <br> - Phân tích Object Key, Prefix và hiệu năng truy cập S3 | 01/06/2026 | 01/06/2026 | https://www.youtube.com/watch?v=mPBjB6Ltl_Q&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=105 |
| 2 | - Nghiên cứu Module 04-04 <br> - Tìm hiểu Amazon S3 Glacier, AWS Snow Family và Storage Gateway <br> - Phân tích các phương án di chuyển dữ liệu lên AWS | 02/06/2026 | 02/06/2026 | https://www.youtube.com/watch?v=YXn8Q_Hpsu4&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=106 |
| 3 | - Thực hành Lab 000014 <br> - Chuẩn bị Image máy ảo <br> - Tạo IAM Role `vmimport` <br> - Upload Image lên S3 và thực hiện VM Import | 03/06/2026 | 03/06/2026 | https://000014.awsstudygroup.com/vi/ |
| 4 | - Tiếp tục Lab VM Import/Export <br> - Tạo AMI từ máy ảo được Import <br> - Khởi tạo EC2 từ AMI <br> - Tìm hiểu quy trình Export Instance và Export Image | 04/06/2026 | 04/06/2026 | https://000014.awsstudygroup.com/vi/ |
| 5 | - Thực hành Lab 000024 <br> - Triển khai AWS Storage Gateway <br> - Kích hoạt File Gateway <br> - Tạo SMB File Share sử dụng Amazon S3 làm Backend | 05/06/2026 | 05/06/2026 | https://000024.awsstudygroup.com/vi/ |
| 6 | - Kết nối SMB File Share từ Client <br> - Kiểm tra dữ liệu được đồng bộ lên S3 <br> - Xử lý lỗi Gateway và File Share <br> - Theo dõi Cache và trạng thái kết nối | 06/06/2026 | 06/06/2026 | https://000024.awsstudygroup.com/vi/ |
| 7 | - Ôn tập toàn bộ Module 04 <br> - So sánh S3, Glacier, Snow Family, Storage Gateway và AWS Backup <br> - Tổng hợp chiến lược Disaster Recovery <br> - Kiểm tra và xóa tài nguyên không còn sử dụng | 07/06/2026 | 07/06/2026 | https://www.youtube.com/watch?v=YXn8Q_Hpsu4&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=106 |

---

## Kết quả đạt được tuần 7

### 1. Hoàn thành Module 04

Các nội dung đã hoàn thành trong hai tuần:

| Module | Nội dung |
| --- | --- |
| Module 04-01 | Tổng quan các dịch vụ lưu trữ trên AWS |
| Module 04-02 | Amazon S3, Access Point và Storage Classes |
| Module 04-03 | Static Website, CORS, Access Control, Object Key, Performance và Glacier |
| Module 04-04 | Snow Family, Storage Gateway và các phương án di chuyển dữ liệu |
| Thực hành | S3, AWS Backup, VM Import/Export và Storage Gateway |

Sau Module 04, đã hiểu được toàn bộ vòng đời dữ liệu từ tạo mới, lưu trữ, truy cập, sao lưu, lưu trữ dài hạn, di chuyển và khôi phục.

---

### 2. S3 Static Website và CORS

CORS cho phép một ứng dụng từ Domain này gửi Request đến tài nguyên trên Domain khác.

Ví dụ:

```text
Frontend: https://app.example.com
        ↓
Request đến Amazon S3
        ↓
S3 kiểm tra CORS Configuration
        ↓
Cho phép hoặc từ chối Request
```

CORS Configuration có thể quy định:

* Allowed Origins.
* Allowed Methods.
* Allowed Headers.
* Exposed Headers.
* Max Age.

Ví dụ:

```json
[
  {
    "AllowedOrigins": ["https://app.example.com"],
    "AllowedMethods": ["GET"],
    "AllowedHeaders": ["*"],
    "ExposeHeaders": ["ETag"],
    "MaxAgeSeconds": 3000
  }
]
```

Hiểu rằng CORS không thay thế IAM Policy hoặc Bucket Policy. Request vẫn phải có quyền truy cập phù hợp.

---

### 3. Kiểm soát truy cập Amazon S3

Các cơ chế đã tìm hiểu:

* IAM Identity-Based Policy.
* S3 Bucket Policy.
* Access Point Policy.
* ACL.
* Block Public Access.
* VPC Endpoint Policy.
* KMS Key Policy.
* Pre-Signed URL.

Quy trình đánh giá quyền:

```text
Request
   ↓
Authentication
   ↓
IAM Policy
   ↓
Bucket hoặc Access Point Policy
   ↓
Block Public Access
   ↓
KMS Permission nếu có mã hóa
   ↓
Allow hoặc Deny
```

Nguyên tắc quan trọng:

* Explicit Deny luôn được ưu tiên.
* Chỉ cấp quyền cần thiết.
* Tránh công khai Bucket nếu không thực sự cần.
* Nên sử dụng CloudFront cho nội dung công khai.
* Sử dụng Pre-Signed URL khi cần cấp quyền tạm thời cho Object.

---

### 4. Object Key và Prefix

Ví dụ Object Key:

```text
reports/2026/06/architecture-review.pdf
```

Trong đó:

* `reports/` là Prefix cấp đầu.
* `2026/06/` là Prefix tiếp theo.
* `architecture-review.pdf` là tên tệp.

Thiết kế Object Key hợp lý giúp:

* Tổ chức dữ liệu.
* Lọc Object.
* Áp dụng Lifecycle Rule.
* Phân quyền theo Prefix.
* Phân tích chi phí.
* Hỗ trợ ứng dụng tìm kiếm dữ liệu.

---

### 5. Hiệu năng Amazon S3

Các phương pháp được tìm hiểu:

* Sử dụng Multipart Upload cho tệp lớn.
* Sử dụng Byte-Range Fetch.
* Sử dụng Transfer Acceleration khi Upload từ vị trí xa.
* Sử dụng CloudFront khi phân phối nội dung.
* Thực hiện Request song song.
* Sử dụng SDK có Retry và Exponential Backoff.
* Theo dõi lỗi `4xx` và `5xx`.
* Chọn Region gần ứng dụng và người dùng.

Luồng Multipart Upload:

```text
Large File
   ↓
Split into Parts
   ↓
Upload Parts in Parallel
   ↓
Complete Multipart Upload
   ↓
Amazon S3 Object
```

---

### 6. Amazon S3 Glacier

Glacier được sử dụng cho dữ liệu lưu trữ dài hạn.

Các trường hợp sử dụng:

* Hồ sơ pháp lý.
* Dữ liệu tuân thủ.
* Backup dài hạn.
* Media Archive.
* Dữ liệu ít truy cập.
* Bản sao Disaster Recovery.

Khi sử dụng Glacier cần xem xét:

* Thời gian truy xuất.
* Chi phí Retrieval.
* Minimum Storage Duration.
* Mức độ thường xuyên sử dụng dữ liệu.
* Yêu cầu RTO.

Lifecycle Rule có thể tự động chuyển dữ liệu từ S3 Standard sang Glacier.

---

### 7. AWS Snow Family

AWS Snow Family hỗ trợ di chuyển dữ liệu khi:

* Dung lượng dữ liệu quá lớn.
* Băng thông Internet hạn chế.
* Kết nối không ổn định.
* Chi phí truyền dữ liệu qua mạng cao.
* Thời gian truyền qua Internet không đáp ứng yêu cầu.

Các thiết bị được tìm hiểu:

| Thiết bị | Trường hợp sử dụng |
| --- | --- |
| AWS Snowcone | Dữ liệu quy mô nhỏ và Edge Computing |
| AWS Snowball Edge | Di chuyển lượng dữ liệu lớn và xử lý tại Edge |
| AWS Snowmobile | Di chuyển lượng dữ liệu cực lớn |

Quy trình tổng quát:

```text
Tạo Snow Job
     ↓
AWS gửi thiết bị
     ↓
Sao chép dữ liệu vào thiết bị
     ↓
Gửi thiết bị về AWS
     ↓
AWS Import dữ liệu
     ↓
Dữ liệu xuất hiện trên Amazon S3
```

---

### 8. VM Import/Export

VM Import/Export hỗ trợ đưa máy ảo từ môi trường hiện tại lên AWS.

Quy trình Import:

```text
On-Premises Virtual Machine
          ↓
Export Virtual Disk
          ↓
Upload Image to Amazon S3
          ↓
VM Import/Export Service
          ↓
Create Amazon Machine Image
          ↓
Launch EC2 Instance
```

Các thành phần cần thiết:

* Image máy ảo.
* S3 Bucket.
* IAM Role `vmimport`.
* Trust Policy.
* Service Role Permission.
* Import Task.
* AMI.
* EC2 Instance.

---

### 9. IAM Role cho VM Import/Export

Role `vmimport` cho phép dịch vụ:

* Đọc Image từ S3.
* Ghi dữ liệu liên quan.
* Tạo Snapshot.
* Tạo AMI.
* Thực hiện các thao tác Import hoặc Export.

Các lỗi thường gặp:

* Sai tên Role.
* Trust Policy không cho phép dịch vụ VM Import/Export.
* Role thiếu quyền S3.
* Sai Bucket Name.
* Image Format không được hỗ trợ.
* Region của S3 Bucket và Import Task không phù hợp.

---

### 10. AWS Storage Gateway

Storage Gateway kết nối hệ thống tại chỗ với dịch vụ lưu trữ AWS.

Kiến trúc:

```text
On-Premises Client
        ↓
SMB hoặc NFS
        ↓
Storage Gateway
        ↓
Local Cache
        ↓
Amazon S3
```

Các loại Gateway được tìm hiểu:

* Amazon S3 File Gateway.
* Amazon FSx File Gateway.
* Volume Gateway.
* Tape Gateway.

Lợi ích:

* Ứng dụng tiếp tục sử dụng giao thức File truyền thống.
* Dữ liệu được lưu trên AWS.
* Hỗ trợ mô hình Hybrid Cloud.
* Có Local Cache để cải thiện tốc độ truy cập.
* Hỗ trợ Backup và Archive.

---

### 11. File Gateway và SMB File Share

Đã thực hiện:

* Triển khai Gateway Appliance.
* Kích hoạt Gateway.
* Gắn Local Cache Disk.
* Chọn S3 Bucket.
* Tạo SMB File Share.
* Cấu hình Guest Access hoặc Authentication.
* Kết nối File Share từ Client.
* Tạo và chỉnh sửa tệp.
* Kiểm tra Object trên Amazon S3.

Luồng dữ liệu:

```text
Windows Client
      ↓
SMB File Share
      ↓
File Gateway
      ↓
Amazon S3 Object
```

---

### 12. Local Cache trong Storage Gateway

Local Cache lưu những dữ liệu được truy cập thường xuyên.

Lợi ích:

* Giảm độ trễ.
* Hạn chế việc tải lại dữ liệu từ AWS.
* Tăng trải nghiệm cho ứng dụng tại chỗ.
* Cho phép sử dụng Cloud Storage với giao diện File Storage.

Cần theo dõi:

* Dung lượng Cache.
* Cache Hit.
* Cache Miss.
* Gateway Health.
* Network Throughput.
* Upload Buffer nếu sử dụng loại Gateway yêu cầu.

---

### 13. Backup và Restore

Quy trình sao lưu:

```text
Production Resource
        ↓
Backup Plan
        ↓
Backup Job
        ↓
Recovery Point
        ↓
Backup Vault
```

Quy trình khôi phục:

```text
Recovery Point
        ↓
Restore Job
        ↓
New Resource
        ↓
Validation
        ↓
Return to Operation
```

Điều quan trọng là Backup chỉ có giá trị khi có thể khôi phục và kiểm tra dữ liệu thành công.

---

### 14. Disaster Recovery

Các chiến lược được tìm hiểu:

#### Backup and Restore

* Chi phí thấp.
* Thời gian phục hồi lâu hơn.
* Phù hợp với hệ thống không yêu cầu khôi phục tức thời.

#### Pilot Light

* Duy trì các thành phần cốt lõi trên AWS.
* Mở rộng hệ thống khi xảy ra sự cố.

#### Warm Standby

* Duy trì phiên bản hệ thống có quy mô nhỏ.
* Có thể nhanh chóng mở rộng khi cần.

#### Multi-Site Active-Active

* Hệ thống hoạt động tại nhiều địa điểm.
* RTO thấp.
* Chi phí và độ phức tạp cao.

---

### 15. Recovery Time Objective và Recovery Point Objective

#### Recovery Time Objective

Khoảng thời gian tối đa hệ thống được phép ngừng hoạt động.

#### Recovery Point Objective

Lượng dữ liệu tối đa có thể chấp nhận mất, được tính theo thời gian.

Ví dụ:

```text
RTO = 2 giờ
RPO = 15 phút
```

Điều này có nghĩa:

* Hệ thống cần được khôi phục trong vòng hai giờ.
* Có thể chấp nhận mất tối đa 15 phút dữ liệu.

Tần suất Backup ảnh hưởng trực tiếp đến RPO, trong khi kiến trúc khôi phục ảnh hưởng đến RTO.

---

## Các lỗi thực tế đã xử lý

### 1. VM Import Task thất bại

Các nội dung được kiểm tra:

* Image Format.
* S3 Bucket.
* Object Key.
* IAM Role `vmimport`.
* Trust Relationship.
* Service Permission.
* Region.
* Log của Import Task.

---

### 2. Không thể khởi tạo EC2 từ AMI đã Import

Các nguyên nhân được rà soát:

* AMI chưa ở trạng thái Available.
* Snapshot chưa hoàn thành.
* Driver hệ điều hành chưa phù hợp.
* Boot Mode không tương thích.
* Instance Type không hỗ trợ.
* Network Configuration của hệ điều hành chưa đúng.

---

### 3. Storage Gateway không kích hoạt được

Các thành phần được kiểm tra:

* Gateway VM đang chạy.
* Network Connectivity.
* DNS Resolution.
* NTP và thời gian hệ thống.
* Activation Key.
* Region.
* Security Group.
* Internet hoặc VPC Endpoint.

---

### 4. SMB File Share ở trạng thái Unavailable

Các nguyên nhân được kiểm tra:

* Gateway chưa ở trạng thái Running.
* IAM Role không đủ quyền truy cập S3.
* S3 Bucket không tồn tại.
* File Share Configuration không đúng.
* Network Connectivity bị gián đoạn.
* Authentication không chính xác.
* Local Cache Disk chưa được cấu hình.

---

### 5. Client không kết nối được SMB Share

Các nội dung được kiểm tra:

* Địa chỉ Gateway.
* Tên File Share.
* TCP Port 445.
* Windows Firewall.
* Security Group.
* Routing.
* DNS.
* Username và Password.
* Guest Access.

Ví dụ:

```text
\\gateway-ip\share-name
```

---

### 6. Dữ liệu chưa xuất hiện trên S3

Các nguyên nhân được rà soát:

* File chưa đóng hoàn toàn.
* Gateway chưa hoàn tất Upload.
* Cache chưa được đồng bộ.
* IAM Role thiếu quyền.
* Sai Bucket hoặc Prefix.
* Network bị gián đoạn.
* Cần Refresh Cache khi dữ liệu thay đổi trực tiếp trên S3.

---

## Kỹ năng đạt được

* Cấu hình S3 CORS.
* Phân tích cơ chế S3 Access Control.
* Tổ chức Object bằng Key và Prefix.
* Hiểu các phương pháp tối ưu hiệu năng S3.
* Lựa chọn lớp lưu trữ Glacier.
* Phân biệt các thiết bị AWS Snow Family.
* Thực hiện VM Import/Export.
* Tạo IAM Role cho dịch vụ Migration.
* Triển khai AWS Storage Gateway.
* Tạo và sử dụng SMB File Share.
* Phân tích Backup, Restore, RTO và RPO.
* Xử lý lỗi trong Hybrid Storage.

---

## Tự đánh giá

* Đã hoàn thành toàn bộ nội dung Module 04.
* Hiểu rõ vòng đời dữ liệu trên AWS.
* Có thể lựa chọn dịch vụ lưu trữ theo nhu cầu.
* Có khả năng triển khai Static Website và quản lý quyền truy cập S3.
* Hiểu quy trình lưu trữ dài hạn bằng Glacier.
* Nắm được phương án di chuyển dữ liệu bằng Snow Family.
* Có thể thực hiện các bước cơ bản của VM Import/Export.
* Có thể triển khai File Gateway và SMB File Share.
* Hiểu rõ hơn về Backup, Restore và Disaster Recovery.
* Cải thiện kỹ năng troubleshooting liên quan đến IAM, Network và Storage.

Nội dung cần cải thiện:

* Thực hành S3 Cross-Region Replication.
* Tìm hiểu Object Lock và Legal Hold.
* Thực hành Restore dữ liệu từ Glacier.
* Tìm hiểu AWS DataSync và Transfer Family.
* Thực hành Storage Gateway với Active Directory.
* Thực hiện bài kiểm thử Disaster Recovery hoàn chỉnh.
* Đo lường RTO và RPO thực tế.

---

## Kế hoạch tiếp theo

* Chuẩn bị cho Module tiếp theo.
* Nghiên cứu thêm:

  * AWS IAM.
  * IAM Policy.
  * IAM Role.
  * Permission Boundary.
  * AWS Organizations.
  * IAM Identity Center.
  * AWS KMS.
  * AWS Security Hub.

* Tiếp tục áp dụng kiến thức lưu trữ vào các dự án:

  * Lưu File Upload trên S3.
  * Quản lý báo cáo trên S3.
  * Tạo Backup Plan.
  * Xây dựng Lifecycle Rule.
  * Thiết kế phương án Disaster Recovery.
  * Bảo vệ dữ liệu bằng Encryption và Least Privilege.

---

