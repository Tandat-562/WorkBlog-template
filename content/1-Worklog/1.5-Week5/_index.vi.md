---
title: "Worklog tuần 5"
date: 2026-05-24
weight: 1
chapter: false
pre: " <b> 1.5. </b> "

---

## Mục tiêu tuần 5

* Hoàn thành phần còn lại của Module 03 về dịch vụ Compute trên AWS.
* Tìm hiểu EC2 User Data và EC2 Instance Metadata.
* Hiểu quy trình tự động hóa cấu hình máy chủ khi khởi tạo.
* Nghiên cứu kiến trúc EC2 Auto Scaling và Elastic Load Balancing.
* Thực hành Launch Template, Target Group, Load Balancer và Auto Scaling Group.
* Phân biệt Manual, Scheduled, Dynamic và Predictive Scaling.
* Tìm hiểu Amazon EFS, Amazon FSx và các hệ thống File Storage.
* Thực hành triển khai ứng dụng bằng Amazon Lightsail.
* Tìm hiểu tổng quan AWS Application Migration Service.
* Rèn luyện kỹ năng monitoring, scaling và troubleshooting trong hệ thống có độ sẵn sàng cao.

---

## Các công việc thực hiện trong tuần

| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --- | --- | --- | --- |
| 1 | - Nghiên cứu Module 03-01-05 về EC2 User Data <br> - Viết Startup Script để cài đặt Web Server <br> - Kiểm tra Cloud-Init Log <br> - Ôn tập AMI, EBS và Snapshot | 05/18/2026 | 05/18/2026 | https://www.youtube.com/watch?v=_v_43Wi7zjo&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=77 |
| 2 | - Nghiên cứu Module 03-01-06 về EC2 Metadata <br> - Truy xuất Instance ID, Region, Private IP và Security Credentials <br> - Tìm hiểu Instance Metadata Service v1 và v2 <br> - Ôn tập CloudWatch Metrics và Logs | 05/19/2026 | 05/19/2026 | https://www.youtube.com/watch?v=Ew3QRaKJQSA&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=78 |
| 3 | - Nghiên cứu Module 03-01-07 về EC2 Auto Scaling <br> - Tìm hiểu Launch Template, Auto Scaling Group và Scaling Policy <br> - Phân tích Min, Desired và Max Capacity <br> - Ôn tập Security Group và EC2 Networking | 05/20/2026 | 05/20/2026 | https://www.youtube.com/watch?v=bbLcPitXJSY&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=79 |
| 4 | - Nghiên cứu Module 03-02 về EC2 Auto Scaling, EFS, FSx, Lightsail và MGN <br> - So sánh Block Storage với File Storage <br> - Tìm hiểu các phương án di chuyển máy chủ lên AWS | 05/21/2026 | 05/21/2026 | https://www.youtube.com/watch?v=hFVYG8WqfU0&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=80 |
| 5 | - Triển khai Launch Template <br> - Tạo Target Group và Application Load Balancer <br> - Tạo Auto Scaling Group <br> - Chuẩn bị CloudWatch Custom Metrics | 05/22/2026 | 05/22/2026 | https://000006.awsstudygroup.com/vi/ |
| 6 | - Tiếp tục Lab Auto Scaling <br> - Thực hành Manual, Scheduled, Dynamic và Predictive Scaling <br> - Kiểm tra Health Check và phân phối lưu lượng <br> - Theo dõi Scaling Activity | 05/23/2026 | 05/23/2026 | https://000006.awsstudygroup.com/vi/ |
| 7 | - Triển khai Amazon Lightsail Database <br> - Tạo WordPress và PrestaShop Instance <br> - Kiểm tra Static IP và Networking <br> - Xử lý lỗi Instance Limit và Quota Restriction | 05/24/2026 | 05/24/2026 | https://000045.awsstudygroup.com/vi/ |

---

## Kết quả đạt được tuần 5

### 1. Hoàn thành Module 03

Các nội dung được hoàn thành:

| Module | Nội dung |
| --- | --- |
| Module 03-01-05 | EC2 User Data |
| Module 03-01-06 | EC2 Instance Metadata |
| Module 03-01-07 | EC2 Auto Scaling |
| Module 03-02 | Auto Scaling, EFS, FSx, Lightsail và Application Migration Service |

Sau hai tuần, đã hoàn thành toàn bộ chuỗi nội dung Module 03 về máy chủ ảo, lưu trữ gắn với Compute, tự động hóa, mở rộng hệ thống và các dịch vụ Compute liên quan.

---

### 2. Tự động hóa EC2 bằng User Data

User Data cho phép chạy Script khi EC2 được khởi tạo.

Ví dụ:

```bash
#!/bin/bash
dnf update -y
dnf install httpd -y
systemctl enable httpd
systemctl start httpd
echo "<h1>FCJ Management Server</h1>" > /var/www/html/index.html
```

Luồng hoạt động:

```text
Launch EC2
    ↓
Operating System Starts
    ↓
Cloud-Init Reads User Data
    ↓
Install Packages
    ↓
Configure Application
    ↓
Start Services
```

Lợi ích:

* Giảm cấu hình thủ công.
* Chuẩn hóa máy chủ.
* Hỗ trợ tạo nhiều Instance có cấu hình giống nhau.
* Phù hợp với Launch Template và Auto Scaling.
* Rút ngắn thời gian triển khai.

---

### 3. Kiểm tra lỗi User Data

Các nội dung được kiểm tra:

* Shebang của Script.
* Quyền Root.
* Package Manager.
* Kết nối Internet.
* NAT Gateway hoặc Internet Gateway.
* Repository.
* Tên Service.
* Cloud-Init Log.

Các file Log:

```bash
/var/log/cloud-init.log
/var/log/cloud-init-output.log
```

Lệnh kiểm tra:

```bash
sudo cat /var/log/cloud-init-output.log
sudo systemctl status httpd
```

Hiểu rằng User Data thường chỉ chạy trong lần khởi tạo đầu tiên nếu không có cấu hình bổ sung.

---

### 4. EC2 Instance Metadata

Instance Metadata cung cấp thông tin về chính EC2 Instance đang chạy.

Ví dụ dữ liệu:

* Instance ID.
* Instance Type.
* Availability Zone.
* Region.
* Private IP.
* Public IP.
* IAM Role.
* Temporary Credentials.
* Network Interface.

Metadata không cần lưu cứng các thông tin Instance trong mã nguồn.

---

### 5. Instance Metadata Service v2

IMDSv2 sử dụng Session Token trước khi truy xuất Metadata.

Ví dụ:

```bash
TOKEN=$(curl -X PUT \
"http://169.254.169.254/latest/api/token" \
-H "X-aws-ec2-metadata-token-ttl-seconds: 21600")

curl \
-H "X-aws-ec2-metadata-token: $TOKEN" \
http://169.254.169.254/latest/meta-data/instance-id
```

Lợi ích của IMDSv2:

* Yêu cầu Token.
* Giảm nguy cơ khai thác Metadata thông qua SSRF.
* Có thể giới hạn Hop Limit.
* Phù hợp với yêu cầu bảo mật hiện đại hơn IMDSv1.

Không nên ghi Temporary Credentials từ Metadata vào Log hoặc chia sẻ ra ngoài Instance.

---

### 6. Kiến trúc EC2 Auto Scaling

Các thành phần chính:

```text
Launch Template
       ↓
Auto Scaling Group
       ↓
EC2 Instances
       ↓
Target Group
       ↓
Application Load Balancer
       ↓
Users
```

Auto Scaling Group duy trì số lượng Instance trong khoảng:

* Minimum Capacity.
* Desired Capacity.
* Maximum Capacity.

Khi một Instance không đạt Health Check, Auto Scaling có thể thay thế Instance đó.

---

### 7. Launch Template

Launch Template lưu cấu hình dùng để tạo EC2:

* AMI.
* Instance Type.
* Key Pair.
* Security Group.
* IAM Instance Profile.
* Storage.
* User Data.
* Network Configuration.
* Tags.

Phân biệt:

| AMI | Launch Template |
| --- | --- |
| Chứa hệ điều hành và phần mềm | Chứa cấu hình triển khai EC2 |
| Dùng làm Image nguồn | Tham chiếu đến AMI |
| Có thể tạo từ EC2 | Có thể tạo nhiều Version |
| Không tự quy định Scaling | Được sử dụng bởi Auto Scaling Group |

---

### 8. Elastic Load Balancing

Application Load Balancer phân phối HTTP/HTTPS Traffic đến nhiều Target.

Luồng xử lý:

```text
Client
   ↓
Application Load Balancer
   ↓
Target Group
   ↓
Healthy EC2 Instances
```

Các thành phần:

* Listener.
* Listener Rule.
* Target Group.
* Health Check.
* Registered Targets.
* Security Group.

Load Balancer chỉ chuyển Traffic đến các Target được đánh giá là Healthy.

---

### 9. Target Group và Health Check

Target Group quản lý danh sách Backend Target.

Health Check có thể kiểm tra:

* Protocol.
* Port.
* Path.
* Interval.
* Timeout.
* Healthy Threshold.
* Unhealthy Threshold.
* Expected Status Code.

Nguyên nhân Target Unhealthy:

* Web Server chưa chạy.
* Sai Health Check Path.
* Security Group chặn Traffic.
* Ứng dụng trả về Status Code không phù hợp.
* Port của Target Group không đúng.
* User Data chưa hoàn tất.
* Route hoặc NACL chưa đúng.

---

### 10. Các phương thức Scaling

#### Manual Scaling

Administrator thay đổi Desired Capacity thủ công.

#### Scheduled Scaling

Thay đổi Capacity theo lịch định trước.

Ví dụ:

```text
08:00 – Tăng lên 4 Instances
22:00 – Giảm còn 1 Instance
```

#### Dynamic Scaling

Thay đổi Capacity theo Metric thời gian thực.

Ví dụ:

* Target Tracking.
* Step Scaling.
* Simple Scaling.

#### Predictive Scaling

Sử dụng dữ liệu lịch sử để dự đoán nhu cầu trong tương lai và chuẩn bị Capacity trước khi lưu lượng tăng.

---

### 11. CloudWatch Custom Metrics

Custom Metrics được sử dụng khi Metric mặc định chưa đủ để phản ánh workload.

Ví dụ:

* Số lượng Request.
* Độ dài Queue.
* Số User đang hoạt động.
* Số Job chờ xử lý.
* Application Latency.

Ví dụ gửi Metric bằng AWS CLI:

```bash
aws cloudwatch put-metric-data \
  --namespace FCJManagement \
  --metric-name ActiveUsers \
  --value 25 \
  --unit Count
```

Custom Metric có thể được sử dụng trong CloudWatch Alarm và Scaling Policy.

---

### 12. Amazon EFS

Amazon EFS cung cấp File Storage được quản lý và hỗ trợ NFS.

Đặc điểm:

* Nhiều EC2 có thể mount cùng File System.
* Tự động mở rộng dung lượng.
* Có thể triển khai Mount Target trong nhiều Availability Zone.
* Phù hợp với Linux workload.
* Hỗ trợ lưu trữ dữ liệu dùng chung.

Trường hợp sử dụng:

* Shared Web Content.
* Content Management System.
* Home Directory.
* Shared Application Data.
* Container Storage.

---

### 13. Amazon FSx

Amazon FSx cung cấp các hệ thống File Storage được quản lý.

Một số lựa chọn:

| Dịch vụ | Trường hợp sử dụng |
| --- | --- |
| FSx for Windows File Server | Windows workload, SMB và Active Directory |
| FSx for Lustre | High-performance computing và Machine Learning |
| FSx for NetApp ONTAP | Workload doanh nghiệp và Data Management |
| FSx for OpenZFS | Workload cần tính năng ZFS |

Việc lựa chọn phụ thuộc vào hệ điều hành, giao thức, hiệu năng và yêu cầu tích hợp.

---

### 14. Amazon Lightsail

Lightsail cung cấp môi trường triển khai đơn giản với chi phí theo gói.

Đã thực hành:

* Tạo Linux Instance.
* Tạo WordPress Instance.
* Tạo PrestaShop Instance.
* Tạo Lightsail Database.
* Gắn Static IP.
* Kiểm tra Firewall.
* Theo dõi Metric.
* Xóa tài nguyên sau khi hoàn thành.

Lightsail phù hợp với:

* Website nhỏ.
* Blog.
* Demo.
* Development Environment.
* Ứng dụng không yêu cầu kiến trúc AWS phức tạp.

---

### 15. AWS Application Migration Service

AWS Application Migration Service hỗ trợ di chuyển máy chủ lên AWS.

Quy trình tổng quan:

```text
Source Server
      ↓
Install Replication Agent
      ↓
Replicate Data to AWS
      ↓
Launch Test Instance
      ↓
Validate Application
      ↓
Perform Cutover
      ↓
Launch Production Instance
```

Lợi ích:

* Giảm thời gian gián đoạn.
* Hỗ trợ kiểm thử trước khi Cutover.
* Tự động hóa quá trình Replication.
* Phù hợp với chiến lược Rehost.

---

### 16. High Availability và khả năng phục hồi

Mô hình triển khai:

```text
                 Internet
                    ↓
       Application Load Balancer
              /             \
     Availability Zone A   Availability Zone B
             ↓                    ↓
        EC2 Instance          EC2 Instance
              \               /
               Auto Scaling Group
```

Lợi ích:

* Không phụ thuộc một Instance duy nhất.
* Có thể thay thế Instance bị lỗi.
* Phân phối Traffic giữa nhiều Availability Zone.
* Tự động thay đổi Capacity.
* Cải thiện Availability và Fault Tolerance.

---

## Các lỗi thực tế đã xử lý

### 1. User Data không cài đặt được ứng dụng

Các nguyên nhân được kiểm tra:

* Script sai cú pháp.
* Instance không có Internet.
* Repository không truy cập được.
* Sai Package Manager.
* Service Name không chính xác.
* User Data chưa chạy với quyền Root.
* Script phụ thuộc tài nguyên chưa sẵn sàng.

---

### 2. Load Balancer Target ở trạng thái Unhealthy

Cách xử lý:

* Kiểm tra ứng dụng trên EC2.
* Kiểm tra Port.
* Kiểm tra Health Check Path.
* Kiểm tra Security Group của EC2.
* Cho phép Traffic từ Security Group của Load Balancer.
* Kiểm tra Status Code.
* Kiểm tra User Data và Application Log.

---

### 3. Auto Scaling không tạo Instance

Các nguyên nhân được rà soát:

* Launch Template sai cấu hình.
* AMI không tồn tại.
* Không đủ quyền IAM.
* Instance Type không khả dụng.
* Vượt Service Quota.
* Subnet không đủ địa chỉ IP.
* Key Pair hoặc Security Group sai.
* User Data gây lỗi khi khởi tạo.

---

### 4. Predictive Scaling chưa có đủ dữ liệu

Hiểu được:

* Predictive Scaling cần dữ liệu Metric lịch sử.
* Metric phải có chu kỳ và xu hướng đủ rõ.
* Custom Metric phải được gửi ổn định.
* Namespace và Dimension phải nhất quán.
* Không nên đánh giá Predictive Scaling chỉ sau một khoảng thời gian ngắn.

---

### 5. AWS CLI không gửi được Custom Metric

Các nội dung được kiểm tra:

* AWS CLI Profile.
* Region.
* IAM Permission.
* Namespace.
* Metric Name.
* Unit.
* Credential.
* Thời gian hệ thống.

---

### 6. Lightsail không tạo thêm Instance

Các nguyên nhân được kiểm tra:

* Lightsail Instance Limit.
* Account Restriction.
* Region Availability.
* Blueprint.
* Bundle.
* Service Quota.
* Billing hoặc Account Verification.

Nhận thấy giới hạn thực tế của Lightsail có thể khác với một số Service Quota hiển thị. Trong trường hợp cần thiết phải tạo AWS Support Case để xác minh giới hạn tài khoản.

---

### 7. Không hoàn thành đầy đủ Stress Test

Hạn chế:

* Chưa tải và cấu hình thành công công cụ kiểm thử tải dự kiến.
* Không tạo được lượng Traffic ổn định để quan sát toàn bộ Scaling Activity.

Kết quả vẫn đạt được:

* Hiểu quy trình Scale-out và Scale-in.
* Theo dõi được Health Check.
* Phân tích được Metric dùng cho Scaling.
* Hiểu cách Load Balancer phối hợp với Auto Scaling Group.

---

## Kỹ năng đạt được

* Viết EC2 User Data Script.
* Kiểm tra Cloud-Init Log.
* Truy xuất EC2 Metadata bằng IMDSv2.
* Tạo Launch Template.
* Cấu hình Target Group và Load Balancer.
* Tạo Auto Scaling Group.
* Phân biệt các phương thức Scaling.
* Gửi CloudWatch Custom Metric.
* Hiểu Amazon EFS và Amazon FSx.
* Triển khai ứng dụng bằng Lightsail.
* Hiểu quy trình Migration bằng AWS MGN.
* Kiểm tra lỗi Monitoring, Scaling và High Availability.

---

## Tự đánh giá

* Đã hoàn thành toàn bộ nội dung Module 03.
* Hiểu cách tự động hóa quá trình khởi tạo EC2.
* Biết sử dụng Metadata mà không lưu cứng thông tin Instance.
* Hiểu vai trò của Launch Template, Load Balancer và Auto Scaling Group.
* Phân biệt được Manual, Scheduled, Dynamic và Predictive Scaling.
* Hiểu sự khác nhau giữa EBS, EFS, FSx và Instance Store.
* Có khả năng triển khai ứng dụng đơn giản bằng Amazon Lightsail.
* Cải thiện tư duy troubleshooting trong kiến trúc nhiều thành phần.

Nội dung cần cải thiện:

* Thực hành Auto Scaling với Traffic thực tế.
* Tìm hiểu sâu hơn về Scaling Cooldown và Instance Warmup.
* Thực hành HTTPS Listener và AWS Certificate Manager.
* Tìm hiểu EFS Performance Mode và Throughput Mode.
* Thực hành FSx for Windows với Active Directory.
* Thực hành Migration bằng AWS Application Migration Service.
* Tối ưu chi phí cho Load Balancer và Auto Scaling.

---

## Kế hoạch tiếp theo

* Bắt đầu Module 04 về AWS Storage Services.
* Nghiên cứu:

  * Amazon S3.
  * S3 Storage Classes.
  * S3 Versioning.
  * S3 Lifecycle.
  * Amazon S3 Glacier.
  * AWS Backup.
  * AWS Storage Gateway.
  * AWS Snow Family.
  * VM Import/Export.

* Tiếp tục thực hành:

  * Backup và Restore.
  * Disaster Recovery.
  * RTO và RPO.
  * Static Website Hosting.
  * CloudFront.
  * Hybrid Storage.
  * Quản lý vòng đời dữ liệu.

---

