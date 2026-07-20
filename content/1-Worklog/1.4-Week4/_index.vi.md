
---
title: "Worklog Tuần 4"
date: 2026-05-17
weight: 1
chapter: false
pre: " <b> 1.4. </b> "

---

## Mục tiêu tuần 4

* Nghiên cứu phần đầu của Module 03 về dịch vụ điện toán và máy chủ ảo trên AWS.
* Hiểu kiến trúc, thành phần và vòng đời của Amazon EC2.
* Phân biệt các loại EC2 Instance, mô hình tính giá và trường hợp sử dụng.
* Tìm hiểu Amazon Machine Image, Key Pair và các phương án sao lưu EC2.
* Thực hành quản lý Amazon EBS, Snapshot và Instance Store.
* Triển khai ứng dụng cơ bản trên EC2 và làm quen với tự động hóa khởi tạo máy chủ.
* Tổ chức tài nguyên bằng AWS Tags và Resource Groups.
* Làm quen với Infrastructure as Code bằng AWS CloudFormation.
* Thiết lập giám sát EC2 bằng Amazon CloudWatch.
* Rèn luyện kỹ năng kiểm tra lỗi liên quan đến EC2, lưu trữ, quyền truy cập và monitoring.

---

## Các công việc thực hiện trong tuần

| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --- | --- | --- | --- |
| 1 | - Nghiên cứu Module 03-01 – Compute VM on AWS <br> - Tìm hiểu vai trò của dịch vụ Compute trên AWS <br> - Phân biệt máy chủ vật lý, máy ảo và mô hình Cloud Compute <br> - Tổng hợp các dịch vụ điện toán chính | 11/05/2026 | 11/05/2026 | https://www.youtube.com/watch?v=-t5h4N6vfBs&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=72 |
| 2 | - Nghiên cứu Module 03-01-01 về Amazon EC2 <br> - Tìm hiểu EC2 Instance Types, vòng đời Instance và mô hình tính giá <br> - Phân tích cách lựa chọn cấu hình EC2 theo workload | 12/05/2026 | 12/05/2026 | https://www.youtube.com/watch?v=e7XeKdOVq40&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=73 |
| 3 | - Nghiên cứu Module 03-01-02 về AMI, Backup và Key Pair <br> - Khởi tạo EC2 Instance <br> - Cấu hình Security Group và Key Pair <br> - Thực hành tạo AMI từ Instance | 13/05/2026 | 13/05/2026 | https://www.youtube.com/watch?v=yAR6QRT3N1k&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=74, https://000004.awsstudygroup.com/vi/ |
| 4 | - Nghiên cứu Module 03-01-03 về Amazon Elastic Block Store <br> - Tạo và gắn EBS Volume vào EC2 <br> - Định dạng, mount và kiểm tra Volume <br> - Tạo Snapshot và khôi phục Volume | 14/05/2026 | 14/05/2026 | https://www.youtube.com/watch?v=hKr_TfGP7NY&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=75, https://000004.awsstudygroup.com/vi/ |
| 5 | - Nghiên cứu Module 03-01-04 về EC2 Instance Store <br> - So sánh Instance Store và Amazon EBS <br> - Kiểm tra tính bền vững của dữ liệu <br> - Cấu hình Tags và tổ chức tài nguyên bằng Resource Groups | 15/05/2026 | 15/05/2026 | https://www.youtube.com/watch?v=6IHNDJ85aoQ&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=76, https://000027.awsstudygroup.com/vi/ |
| 6 | - Tiếp tục thực hành AWS Tags và Resource Groups <br> - Tổ chức tài nguyên theo Environment, Owner và Purpose <br> - Làm quen với cấu trúc CloudFormation Template <br> - Kiểm tra tài nguyên theo CloudFormation Stack | 16/05/2026 | 16/05/2026 | https://000027.awsstudygroup.com/vi/ |
| 7 | - Triển khai AWS CloudFormation Stack <br> - Theo dõi EC2 bằng CloudWatch Metrics <br> - Thực hành Search Expressions và Math Expressions <br> - Cấu hình CloudWatch Logs, Metric Filters, Alarms và Dashboards | 17/05/2026 | 17/05/2026 | https://000008.awsstudygroup.com/vi/ |

---

## Kết quả đạt được tuần 4

### 1. Hoàn thành phần đầu của Module 03

Các nội dung đã nghiên cứu:

| Module | Nội dung |
| --- | --- |
| Module 03-01 | Tổng quan Compute VM trên AWS |
| Module 03-01-01 | Amazon Elastic Compute Cloud |
| Module 03-01-02 | AMI, Backup và Key Pair |
| Module 03-01-03 | Amazon Elastic Block Store |
| Module 03-01-04 | EC2 Instance Store |

Qua phần học này, đã hiểu được cách AWS cung cấp tài nguyên máy chủ ảo, cách lựa chọn cấu hình Compute và cách quản lý lưu trữ gắn với EC2.

---

### 2. Tổng quan dịch vụ Compute trên AWS

Amazon EC2 cho phép khởi tạo máy chủ ảo theo nhu cầu mà không cần trực tiếp quản lý hạ tầng phần cứng.

Quy trình triển khai cơ bản:

```text
Chọn Amazon Machine Image
          ↓
Chọn Instance Type
          ↓
Chọn VPC và Subnet
          ↓
Gắn Storage
          ↓
Cấu hình Security Group
          ↓
Chọn Key Pair
          ↓
Khởi tạo EC2 Instance
```

Các lợi ích chính:

* Cấp phát tài nguyên theo nhu cầu.
* Thay đổi cấu hình linh hoạt.
* Hỗ trợ nhiều hệ điều hành.
* Tích hợp với VPC, IAM, EBS và CloudWatch.
* Có thể tự động mở rộng theo workload.
* Thanh toán dựa trên loại và thời gian sử dụng tài nguyên.

---

### 3. Kiến trúc và vòng đời Amazon EC2

Các trạng thái chính của EC2:

```text
Pending
   ↓
Running
   ↓
Stopping
   ↓
Stopped
   ↓
Shutting-down
   ↓
Terminated
```

Hiểu được:

* `Pending`: AWS đang chuẩn bị tài nguyên.
* `Running`: Instance đang hoạt động.
* `Stopping`: Instance đang được dừng.
* `Stopped`: Instance không chạy nhưng một số tài nguyên lưu trữ vẫn tồn tại.
* `Terminated`: Instance bị xóa và không thể khởi động lại.

Việc dừng Instance không đồng nghĩa mọi chi phí đều dừng vì EBS Volume, Snapshot và Elastic IP vẫn có thể tiếp tục tồn tại.

---

### 4. EC2 Instance Types

Các nhóm Instance Type được tìm hiểu:

| Nhóm | Trường hợp sử dụng |
| --- | --- |
| General Purpose | Ứng dụng web, development server và workload cân bằng |
| Compute Optimized | Xử lý tính toán, batch processing và high-performance computing |
| Memory Optimized | In-memory database và workload cần nhiều RAM |
| Storage Optimized | Hệ thống cần tốc độ đọc ghi dữ liệu cao |
| Accelerated Computing | Machine Learning, đồ họa và xử lý sử dụng GPU |

Khi lựa chọn Instance Type cần xem xét:

* Số lượng vCPU.
* Dung lượng RAM.
* Hiệu năng mạng.
* Loại Storage.
* Kiến trúc CPU.
* Chi phí vận hành.
* Khả năng mở rộng trong tương lai.

---

### 5. Mô hình tính giá EC2

#### On-Demand Instances

* Thanh toán theo mức sử dụng.
* Không yêu cầu cam kết dài hạn.
* Phù hợp với workload ngắn hạn hoặc chưa ổn định.

#### Reserved Instances và Savings Plans

* Yêu cầu cam kết sử dụng.
* Có thể giảm chi phí cho workload ổn định.
* Phù hợp với hệ thống hoạt động lâu dài.

#### Spot Instances

* Sử dụng phần tài nguyên EC2 còn dư.
* Có chi phí thấp hơn.
* AWS có thể thu hồi Instance.
* Phù hợp với workload có khả năng chịu gián đoạn.

---

### 6. Amazon Machine Image

AMI là mẫu dùng để khởi tạo EC2 Instance.

AMI có thể chứa:

* Hệ điều hành.
* Phần mềm đã cài đặt.
* Cấu hình ứng dụng.
* Thông tin Root Volume.
* Block Device Mapping.
* Quyền sử dụng Image.

Quy trình tạo AMI:

```text
Cấu hình EC2 Instance
        ↓
Kiểm tra ứng dụng
        ↓
Tạo Image
        ↓
Tạo Snapshot liên quan
        ↓
Sử dụng AMI để khởi tạo Instance mới
```

Lợi ích:

* Chuẩn hóa cấu hình máy chủ.
* Triển khai nhiều Instance giống nhau.
* Rút ngắn thời gian cài đặt.
* Hỗ trợ backup và disaster recovery.
* Có thể sử dụng với Launch Template và Auto Scaling.

---

### 7. Key Pair và truy cập EC2

Key Pair được sử dụng để xác thực khi kết nối đến EC2.

Đối với Linux:

* Private Key được sử dụng khi kết nối SSH.
* Public Key được lưu trên Instance.

Đối với Windows:

* Private Key được sử dụng để giải mã mật khẩu Administrator.
* Sau đó người dùng kết nối bằng Remote Desktop.

Các nguyên tắc bảo mật:

* Không chia sẻ Private Key.
* Giới hạn quyền đọc file Key.
* Không lưu Key trong source code.
* Chỉ mở cổng SSH hoặc RDP cho IP cần thiết.
* Ưu tiên Session Manager trong môi trường cần bảo mật cao.

---

### 8. Amazon Elastic Block Store

Amazon EBS cung cấp Block Storage bền vững cho EC2.

Đã thực hành:

* Tạo EBS Volume.
* Gắn Volume vào EC2.
* Xác định tên thiết bị.
* Tạo File System.
* Mount Volume.
* Ghi dữ liệu thử nghiệm.
* Tạo Snapshot.
* Khôi phục Volume từ Snapshot.

Luồng thực hành:

```text
Create EBS Volume
        ↓
Attach to EC2
        ↓
Format File System
        ↓
Mount Volume
        ↓
Store Data
        ↓
Create Snapshot
```

---

### 9. EBS Volume Types

Các loại Volume phổ biến:

| Loại | Mục đích |
| --- | --- |
| gp3 | SSD đa dụng, phù hợp với phần lớn workload |
| gp2 | SSD đa dụng thế hệ trước |
| io1/io2 | Workload cần IOPS cao và ổn định |
| st1 | HDD tối ưu cho throughput |
| sc1 | HDD chi phí thấp cho dữ liệu ít truy cập |

Các yếu tố cần xem xét:

* Dung lượng.
* IOPS.
* Throughput.
* Độ trễ.
* Khả năng mã hóa.
* Mức độ quan trọng của dữ liệu.
* Chi phí.

---

### 10. Snapshot và Backup

Snapshot là bản sao dữ liệu tại một thời điểm của EBS Volume.

Hiểu được:

* Snapshot được lưu trữ do AWS quản lý.
* Snapshot đầu tiên chứa toàn bộ dữ liệu cần thiết.
* Các Snapshot tiếp theo hoạt động theo cơ chế tăng dần.
* Snapshot có thể dùng để tạo Volume mới.
* Snapshot có thể được sao chép sang Region khác.
* Snapshot có thể hỗ trợ quy trình Disaster Recovery.

Phân biệt:

| Thành phần | Vai trò |
| --- | --- |
| EBS Volume | Lưu trữ Block Storage đang được EC2 sử dụng |
| Snapshot | Bản sao dữ liệu của EBS tại một thời điểm |
| AMI | Mẫu triển khai EC2 |
| AWS Backup | Dịch vụ quản lý Backup tập trung |
| Instance Store | Lưu trữ tạm thời gắn với máy chủ vật lý |

---

### 11. EC2 Instance Store

Instance Store là lưu trữ tạm thời được gắn trực tiếp với máy chủ vật lý chạy EC2.

Đặc điểm:

* Có hiệu năng cao.
* Phù hợp với dữ liệu tạm thời.
* Dữ liệu không được bảo đảm tồn tại lâu dài.
* Dữ liệu có thể mất khi Instance bị dừng, terminate hoặc chuyển sang máy chủ khác.
* Không thể detach và gắn sang Instance khác như EBS.

Trường hợp sử dụng:

* Cache.
* Buffer.
* Dữ liệu trung gian.
* Temporary processing.
* Dữ liệu có thể được tái tạo.

Không nên sử dụng Instance Store làm nơi duy nhất lưu dữ liệu quan trọng.

---

### 12. AWS Tags và Resource Groups

Tags được cấu tạo theo cặp Key–Value.

Ví dụ:

```text
Environment = Development
Owner       = Tier-S-Team
Project     = FCJ-Management
Purpose     = Web-Server
```

Lợi ích:

* Tổ chức tài nguyên.
* Tìm kiếm và lọc tài nguyên.
* Phân loại chi phí.
* Xác định người quản lý.
* Hỗ trợ automation.
* Kiểm soát truy cập dựa trên Tag.

Resource Groups hỗ trợ nhóm các tài nguyên có cùng Tag hoặc cùng CloudFormation Stack.

---

### 13. Infrastructure as Code với CloudFormation

CloudFormation cho phép mô tả hạ tầng bằng Template.

Cấu trúc tổng quát:

```text
Template
   ↓
CloudFormation Stack
   ↓
AWS Resources
```

Đã thực hành:

* Tạo Stack.
* Kiểm tra Template.
* Theo dõi Stack Events.
* Kiểm tra tài nguyên được tạo.
* Cập nhật Stack.
* Xóa Stack và tài nguyên liên quan.

Lợi ích:

* Triển khai lặp lại.
* Giảm sai sót do cấu hình thủ công.
* Quản lý hạ tầng theo phiên bản.
* Duy trì cấu hình nhất quán giữa các môi trường.

---

### 14. Giám sát bằng Amazon CloudWatch

Các thành phần đã thực hành:

* CloudWatch Metrics.
* CloudWatch Logs.
* Metric Filters.
* CloudWatch Alarms.
* CloudWatch Dashboards.
* Search Expressions.
* Math Expressions.

Các Metric EC2 phổ biến:

* CPUUtilization.
* NetworkIn.
* NetworkOut.
* DiskReadOps.
* DiskWriteOps.
* StatusCheckFailed.

CloudWatch giúp theo dõi hoạt động, phát hiện bất thường và hỗ trợ troubleshooting.

---

## Các lỗi thực tế đã xử lý

### 1. Không kết nối được EC2

Các nội dung được kiểm tra:

* Instance State.
* Public IP hoặc Private IP.
* Route Table.
* Internet Gateway.
* Security Group.
* Network ACL.
* Key Pair.
* Quyền của Private Key.
* SSH hoặc RDP Service.

---

### 2. EBS Volume không hiển thị trong hệ điều hành

Các nội dung được kiểm tra:

* Volume và Instance có cùng Availability Zone.
* Trạng thái Attachment.
* Tên thiết bị.
* File System.
* Mount Point.
* `/etc/fstab` nếu cần tự động mount.

Các lệnh được sử dụng:

```bash
lsblk
df -h
sudo file -s /dev/xvdf
```

---

### 3. Không tạo được AMI hoặc Snapshot

Các nguyên nhân được rà soát:

* Thiếu quyền IAM.
* EBS Volume đang có hoạt động ghi dữ liệu.
* KMS Key không cho phép sử dụng.
* Snapshot đang ở trạng thái Pending.
* AMI phụ thuộc vào Snapshot chưa hoàn thành.

---

### 4. CloudFormation Stack triển khai thất bại

Phương pháp xử lý:

* Kiểm tra Stack Events.
* Xác định Resource đầu tiên bị lỗi.
* Kiểm tra quyền IAM.
* Kiểm tra tên tài nguyên đã tồn tại.
* Kiểm tra Region và Availability Zone.
* Kiểm tra cú pháp Template.
* Xem lại Dependency giữa các tài nguyên.

---

### 5. CloudWatch không hiển thị dữ liệu mong muốn

Các nguyên nhân được kiểm tra:

* Sai Namespace.
* Sai Metric Name.
* Sai Dimension.
* Không có dữ liệu trong khoảng thời gian đã chọn.
* Period không phù hợp.
* CloudWatch Agent chưa gửi Custom Metric.
* Search Expression chưa đúng cú pháp.

---

## Kỹ năng đạt được

* Hiểu kiến trúc và vòng đời EC2.
* Lựa chọn Instance Type theo workload.
* Phân biệt các mô hình giá EC2.
* Tạo và sử dụng AMI.
* Quản lý Key Pair.
* Tạo, gắn và mount EBS Volume.
* Tạo và khôi phục Snapshot.
* Phân biệt EBS và Instance Store.
* Tổ chức tài nguyên bằng Tags.
* Triển khai CloudFormation Stack.
* Theo dõi tài nguyên bằng CloudWatch.
* Kiểm tra lỗi EC2, Storage và Monitoring.

---

## Tự đánh giá

* Đã nắm được kiến thức nền tảng của Module 03 về Amazon EC2.
* Hiểu mối quan hệ giữa EC2, AMI, EBS, Snapshot và Instance Store.
* Có thể khởi tạo và quản lý một EC2 Instance cơ bản.
* Có thể gắn thêm Storage và tạo bản sao dữ liệu.
* Có khả năng tổ chức tài nguyên bằng Tags và Resource Groups.
* Hiểu vai trò ban đầu của CloudFormation và CloudWatch.
* Cải thiện khả năng kiểm tra lỗi theo từng thành phần.

Nội dung cần cải thiện:

* Thực hành thêm EC2 Metadata và User Data.
* Tìm hiểu sâu hơn về mã hóa EBS.
* Thực hành sao chép AMI giữa các Region.
* Chuẩn hóa CloudFormation Template.
* Cài đặt CloudWatch Agent để thu thập Memory và Disk Metrics.
* Tìm hiểu thêm về Auto Scaling và High Availability.

---

## Kế hoạch tiếp theo

* Tiếp tục nghiên cứu các phần còn lại của Module 03:

  * EC2 User Data.
  * EC2 Metadata.
  * EC2 Auto Scaling.
  * Amazon EFS.
  * Amazon FSx.
  * Amazon Lightsail.
  * AWS Application Migration Service.

* Thực hành:

  * Launch Template.
  * Target Group.
  * Application Load Balancer.
  * Auto Scaling Group.
  * Dynamic Scaling.
  * Scheduled Scaling.
  * Predictive Scaling.
  * CloudWatch Custom Metrics.

---

