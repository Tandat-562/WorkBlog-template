
---
title: "Worklog Tuần 3"
date: 2026-05-10
weight: 1
chapter: false
pre: " <b> 1.3. </b> "

---

## Mục tiêu tuần 3

* Tiếp tục nghiên cứu phần Multi-VPC và Hybrid Connectivity của Module 02.
* Quản trị EC2 trong Private Subnet mà không cần mở cổng trực tiếp ra Internet.
* Tìm hiểu và thực hành AWS Systems Manager Session Manager.
* Sử dụng Interface VPC Endpoint để truy cập dịch vụ AWS qua mạng private.
* Kết nối nhiều VPC bằng VPC Peering và AWS Transit Gateway.
* Nghiên cứu vai trò của Site-to-Site VPN, AWS Direct Connect và Load Balancer.
* Xây dựng mô hình Hybrid DNS bằng Route 53 Resolver.
* Kiểm soát truy cập bằng IAM Role, Security Group và Network ACL.
* Hoàn thiện quy trình troubleshooting theo IAM, DNS, routing, firewall và service agent.

---

## Các công việc thực hiện trong tuần

| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --- | --- | --- | --- |
| 1 | - Tiếp tục nghiên cứu phần Multi-VPC của Module 02-02 <br> - Thiết kế mạng gồm Public và Private Subnet <br> - Tạo Linux EC2 phục vụ quản trị và Windows EC2 làm máy chủ nội bộ <br> - Kiểm tra Public IP, Private IP và Network Interface | 05/04/2026 | 05/04/2026 | https://000058.awsstudygroup.com/vi/, https://www.youtube.com/watch?v=BPuD1l2hEQ4&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=26 |
| 2 | - Tạo IAM Role cho EC2 sử dụng Systems Manager <br> - Kiểm tra SSM Agent <br> - Cấu hình Security Group theo Least Privilege <br> - Kết nối EC2 bằng Session Manager thay cho SSH trực tiếp | 05/05/2026 | 05/05/2026 | https://000058.awsstudygroup.com/vi/, https://www.youtube.com/watch?v=BPuD1l2hEQ4&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=26 |
| 3 | - Tạo Interface Endpoint cho SSM, SSMMessages và EC2Messages <br> - Kết nối Private Windows EC2 không có Public IP <br> - Lưu lịch sử Session Manager vào S3 <br> - Thực hành Port Forwarding đến RDP | 05/06/2026 | 05/06/2026 | https://000058.awsstudygroup.com/vi/, https://www.youtube.com/watch?v=BPuD1l2hEQ4&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=26 |
| 4 | - Tạo thêm một VPC độc lập <br> - Thiết lập VPC Peering giữa hai VPC <br> - Cập nhật Route Table và Security Group ở hai phía <br> - Kiểm tra kết nối bằng Private IP | 05/07/2026 | 05/07/2026 | https://000019.awsstudygroup.com/vi/, https://www.youtube.com/watch?v=BPuD1l2hEQ4&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=26 |
| 5 | - Bật DNS Resolution cho VPC Peering <br> - Kiểm tra Private DNS Hostname giữa hai VPC <br> - Thay đổi Network ACL để đánh giá ảnh hưởng đến traffic <br> - So sánh Security Group với Network ACL | 05/08/2026 | 05/08/2026 | https://000019.awsstudygroup.com/vi/, https://www.youtube.com/watch?v=BPuD1l2hEQ4&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=26 |
| 6 | - Triển khai Transit Gateway theo mô hình hub-and-spoke <br> - Tạo Attachment cho nhiều VPC <br> - Cấu hình Association và Propagation <br> - Nghiên cứu tổng quan Direct Connect và các mô hình Hybrid Connectivity | 05/09/2026 | 05/09/2026 | https://000020.awsstudygroup.com/vi/, https://www.youtube.com/watch?v=CXU8D3kyxIc&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=27 |
| 7 | - Tạo môi trường Microsoft Active Directory <br> - Triển khai Route 53 Resolver Inbound và Outbound Endpoint <br> - Tạo Resolver Rule cho Domain nội bộ <br> - Nghiên cứu vai trò của Load Balancer trong phân phối lưu lượng <br> - Tổng hợp kiến thức Module 02 | 05/10/2026 | 05/10/2026 | https://000010.awsstudygroup.com/vi/, https://www.youtube.com/watch?v=CXU8D3kyxIc&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=27 |

---

## Kết quả đạt được tuần 3

### 1. Hoàn thành phần tiếp theo của Module 02

Nội dung Module 02 được tiếp tục trong Week 3:

| Nội dung | Phạm vi nghiên cứu |
| --- | --- |
| Module 02-02 – Phần 2 | VPC Endpoint, VPC Peering, Multi-VPC Networking và Transit Gateway |
| Module 02-03 – Phần 2 | Hybrid Connectivity, Direct Connect, Load Balancing và DNS Integration |

Các bài thực hành tập trung vào quản trị tài nguyên private, kết nối nhiều VPC và xây dựng luồng DNS giữa các môi trường.

---

### 2. Quản trị EC2 không cần Public IP

* Triển khai EC2 trong Private Subnet.
* Không gán Public IP cho máy chủ nội bộ.
* Không mở trực tiếp SSH hoặc RDP ra Internet.
* Sử dụng AWS Systems Manager để quản trị tài nguyên.
* Kiểm soát quyền truy cập bằng IAM.

Các thành phần ảnh hưởng đến trạng thái Managed Node:

* SSM Agent.
* IAM Instance Profile.
* Kết nối đến Systems Manager.
* DNS Resolution.
* VPC Endpoint hoặc NAT Gateway.
* Security Group của Endpoint.

Hiểu rằng EC2 ở trạng thái `Running` không có nghĩa Session Manager đã sẵn sàng hoạt động.

---

### 3. Truy cập máy chủ bằng Session Manager

Session Manager được sử dụng để thay thế SSH hoặc RDP trực tiếp trong một số trường hợp.

Lợi ích:

* Không cần mở cổng quản trị ra Internet.
* Không cần phân phối SSH Key cho nhiều người.
* Quyền truy cập được quản lý bằng IAM.
* Có thể ghi lại lịch sử Session.
* Hỗ trợ quản trị máy chủ trong Private Subnet.
* Giảm nguy cơ tấn công vào cổng SSH và RDP.

Phân biệt:

* Quyền thao tác EC2 không tự động cho phép bắt đầu Session.
* Người dùng cần quyền Systems Manager phù hợp.
* EC2 cũng cần IAM Role để đăng ký với Systems Manager.

---

### 4. Kết nối private bằng Interface VPC Endpoint

Các Endpoint đã tạo:

```text
com.amazonaws.<region>.ssm
com.amazonaws.<region>.ssmmessages
com.amazonaws.<region>.ec2messages
```

Luồng kết nối:

```text
Private EC2
    ↓
Private DNS
    ↓
Interface VPC Endpoint
    ↓
AWS Systems Manager
```

Lợi ích:

* EC2 có thể gọi Systems Manager qua Private IP.
* Không cần Public IP.
* Có thể giảm phụ thuộc vào NAT Gateway cho traffic được hỗ trợ.
* Traffic không cần đi qua Public Internet.

Điều kiện cần thiết:

* Endpoint được đặt trong Subnet phù hợp.
* Security Group cho phép TCP 443.
* VPC bật DNS Support và DNS Hostnames.
* Private DNS được cấu hình đúng.
* IAM Role có quyền cần thiết.

---

### 5. Kiểm soát quyền bằng IAM Role

Đã thực hiện:

* Tạo IAM Role cho EC2.
* Gắn Managed Policy phục vụ Systems Manager.
* Gán Role thông qua Instance Profile.
* Kiểm tra trạng thái sau khi thay đổi Role.
* Xác định lỗi khi EC2 thiếu quyền đăng ký Managed Node.

Lợi ích của Temporary Credentials:

* Không lưu Access Key trên EC2.
* Credentials được tự động làm mới.
* Có thể thay đổi hoặc thu hồi quyền qua Role.
* Giảm nguy cơ lộ thông tin xác thực.
* Hỗ trợ nguyên tắc Least Privilege.

---

### 6. Ghi log phiên quản trị

* Tạo S3 Bucket để lưu Session Manager Log.
* Cấu hình Session Manager Preferences.
* Kiểm tra quyền ghi Object của EC2 Role.
* Kiểm tra Bucket Policy.
* Xác minh dữ liệu sau khi Session kết thúc.

Session Logging hỗ trợ:

* Điều tra sự cố.
* Theo dõi thao tác quản trị.
* Kiểm tra tuân thủ.
* Xác định người truy cập.
* Lưu bằng chứng phục vụ Audit.

Các nguyên nhân khiến log không xuất hiện:

* IAM Role thiếu quyền.
* Bucket Policy chặn truy cập.
* Session Preferences sai.
* Bucket sử dụng cấu hình mã hóa chưa được cấp quyền.
* Phiên kết thúc trước khi dữ liệu được ghi hoàn tất.

---

### 7. Port Forwarding đến Windows EC2

Đã sử dụng Session Manager để tạo Tunnel đến Windows EC2:

```bash
aws ssm start-session \
--target <instance-id> \
--document-name AWS-StartPortForwardingSession \
--parameters portNumber="3389",localPortNumber="9999"
```

Kết nối Remote Desktop qua:

```text
localhost:9999
```

Kết quả:

* Windows EC2 không cần Public IP.
* Không cần mở cổng 3389 cho toàn bộ Internet.
* Traffic quản trị đi qua Session Manager.
* Quyền tạo Tunnel được giới hạn bằng IAM Policy.

---

### 8. Kết nối hai VPC bằng VPC Peering

Đã thực hiện:

* Tạo VPC Peering Connection.
* Chấp nhận kết nối từ VPC đích.
* Cập nhật Route Table ở hai phía.
* Cấu hình Security Group.
* Kiểm tra kết nối bằng Private IP.
* Bật DNS Resolution qua Peering.

Luồng kết nối:

```text
EC2 in VPC A
     ↓
Route Table A
     ↓
VPC Peering Connection
     ↓
Route Table B
     ↓
EC2 in VPC B
```

Giới hạn của VPC Peering:

* Không hỗ trợ Transitive Routing.
* CIDR của hai VPC không được chồng lấn.
* Mỗi kết nối phải được quản lý riêng.
* Số lượng Route và Peering tăng nhanh khi có nhiều VPC.

VPC Peering phù hợp với số lượng VPC nhỏ và yêu cầu kết nối trực tiếp.

---

### 9. DNS Resolution qua VPC Peering

* Bật tùy chọn DNS Resolution cho Peering Connection.
* Kiểm tra Private DNS Hostname từ VPC khác.
* Kiểm tra DNS Support và DNS Hostnames.
* Phân biệt lỗi DNS với lỗi routing hoặc firewall.

Các trường hợp có thể xảy ra:

* Kết nối bằng IP thành công nhưng Hostname không Resolve.
* DNS Resolve thành công nhưng Security Group chặn Traffic.
* Route đã có nhưng DNS Hostnames chưa được bật.
* Peering ở trạng thái Active nhưng Route Table chưa có đường đi hai chiều.

Hiểu rằng DNS và routing phải được kiểm tra độc lập.

---

### 10. Security Group và Network ACL trong Multi-VPC

Đã kiểm tra traffic ở hai cấp độ:

* Security Group tại ENI.
* Network ACL tại Subnet.

Các loại traffic được thử nghiệm:

* TCP 443 cho Interface Endpoint.
* ICMP.
* RDP.
* SSH.
* DNS trên TCP/UDP 53.
* Ephemeral Port phục vụ Response Traffic.

Rút ra được:

* Security Group là Stateful.
* Network ACL là Stateless.
* NACL cần cho phép cả chiều đi và chiều về.
* Một NACL Rule sai có thể làm kết nối thất bại dù Security Group đã cho phép.

---

### 11. Kết nối tập trung bằng Transit Gateway

Transit Gateway được triển khai theo mô hình:

```text
              VPC A
                |
VPC B ─── Transit Gateway ─── VPC C
                |
              VPC D
```

Đã thực hiện:

* Tạo Transit Gateway.
* Tạo Attachment cho các VPC.
* Cập nhật VPC Route Table.
* Tạo Transit Gateway Route Table.
* Cấu hình Association.
* Cấu hình Propagation.
* Kiểm tra traffic giữa nhiều VPC.

Lợi ích:

* Quản lý kết nối tập trung.
* Hỗ trợ Transitive Routing.
* Giảm số lượng kết nối Pair-to-Pair.
* Phù hợp với nhiều VPC và nhiều AWS Account.
* Dễ mở rộng hơn Full-Mesh Peering.

Điểm cần lưu ý:

* Có chi phí Attachment và xử lý dữ liệu.
* Cần kiểm tra nhiều lớp Route Table.
* Thiết kế Association và Propagation phải phù hợp với yêu cầu cô lập mạng.

---

### 12. Association và Propagation

#### Association

Xác định Transit Gateway Route Table được sử dụng để xử lý traffic đi vào từ một Attachment.

#### Propagation

Cho phép Route của Attachment được tự động đưa vào Transit Gateway Route Table.

Ba lớp Route cần kiểm tra:

```text
Source VPC Route Table
          ↓
Transit Gateway Route Table
          ↓
Destination VPC Route Table
```

Attachment ở trạng thái `Available` chưa đảm bảo hai VPC có thể giao tiếp nếu Route hoặc Firewall chưa đúng.

---

### 13. Tổng quan về AWS Direct Connect

Đã nghiên cứu vai trò của AWS Direct Connect trong mô hình Hybrid Cloud:

* Cung cấp kết nối mạng riêng từ môi trường doanh nghiệp đến AWS.
* Không truyền lưu lượng chính qua Public Internet.
* Có thể cung cấp băng thông và độ ổn định cao hơn VPN qua Internet.
* Thường được sử dụng cho hệ thống cần truyền lượng dữ liệu lớn hoặc kết nối ổn định.

So sánh tổng quan:

| Site-to-Site VPN | AWS Direct Connect |
| --- | --- |
| Sử dụng kết nối Internet | Sử dụng kết nối mạng riêng |
| Triển khai nhanh hơn | Cần thời gian thiết lập lâu hơn |
| Chi phí ban đầu thấp hơn | Có chi phí Port và kết nối vật lý |
| Phù hợp làm kết nối dự phòng | Phù hợp với lưu lượng ổn định, quy mô lớn |
| Có mã hóa IPsec | Không tự động cung cấp mã hóa như IPsec |

Trong nhiều kiến trúc, Direct Connect có thể được kết hợp với VPN để tăng bảo mật và khả năng dự phòng.

---

### 14. Tổng quan về Load Balancer

Đã tìm hiểu vai trò của Elastic Load Balancing:

* Phân phối Traffic đến nhiều Target.
* Kiểm tra trạng thái bằng Health Check.
* Tăng khả năng mở rộng và độ sẵn sàng.
* Hạn chế việc người dùng truy cập trực tiếp từng EC2.

Phân biệt cơ bản:

| Load Balancer | Trường hợp sử dụng |
| --- | --- |
| Application Load Balancer | HTTP/HTTPS, Host-Based và Path-Based Routing |
| Network Load Balancer | TCP/UDP, hiệu năng cao và độ trễ thấp |
| Gateway Load Balancer | Triển khai thiết bị mạng hoặc bảo mật ảo |

Load Balancer là thành phần quan trọng khi triển khai ứng dụng trên nhiều Availability Zone.

---

### 15. Xây dựng Hybrid DNS bằng Route 53 Resolver

Đã triển khai:

* Inbound Resolver Endpoint.
* Outbound Resolver Endpoint.
* Resolver Rule.
* Target DNS Server.
* Rule Association với VPC.

Luồng truy vấn:

```text
On-Premises DNS
       ↓
Inbound Resolver Endpoint
       ↓
Amazon Route 53 Resolver
       ↓
Private Hosted Zone
```

Và:

```text
AWS Workload
      ↓
Outbound Resolver Endpoint
      ↓
Resolver Rule
      ↓
On-Premises DNS Server
```

Điều kiện cần kiểm tra:

* Security Group cho phép TCP/UDP 53.
* Route đến DNS Server đích.
* Resolver Rule đúng Domain.
* Endpoint được triển khai trên Subnet phù hợp.
* VPC được Association với Resolver Rule.

---

### 16. Microsoft Active Directory và DNS

* Tạo môi trường Microsoft Active Directory.
* Kiểm tra Domain Controller và DNS Server.
* Thử phân giải bản ghi của Domain nội bộ.
* Kiểm tra khả năng Remote Desktop.
* Phân tích luồng DNS giữa AWS và môi trường Hybrid.

Hiểu rằng:

* Active Directory phụ thuộc mạnh vào DNS.
* Domain Join có thể thất bại nếu DNS sai.
* Ping thành công chưa chứng minh Active Directory hoạt động đúng.
* Cần kiểm tra DNS Record và các cổng dịch vụ liên quan.
* DNS Server mà máy Client sử dụng phải có khả năng Resolve Domain nội bộ.

---

### 17. So sánh các giải pháp kết nối

| Giải pháp | Trường hợp phù hợp | Điểm cần lưu ý |
| --- | --- | --- |
| VPC Peering | Kết nối trực tiếp giữa số lượng nhỏ VPC | Không hỗ trợ Transitive Routing |
| Transit Gateway | Kết nối tập trung giữa nhiều VPC | Có chi phí và nhiều lớp Route |
| Interface VPC Endpoint | Truy cập private đến AWS Services | Cần kiểm tra DNS, Endpoint và Security Group |
| Session Manager | Quản trị EC2 không mở cổng public | Phụ thuộc IAM Role, Agent và Network |
| Site-to-Site VPN | Kết nối AWS với mạng ngoài qua Internet | Phải quản lý IPsec Tunnel và Routing |
| AWS Direct Connect | Kết nối Hybrid ổn định, băng thông lớn | Cần kết nối vật lý và thời gian triển khai |
| Route 53 Resolver | Kết nối DNS giữa AWS và môi trường ngoài AWS | Phụ thuộc Route và DNS Forwarding |
| Load Balancer | Phân phối Traffic đến nhiều Target | Cần Health Check và thiết kế Multi-AZ |

---

## Các lỗi thực tế đã xử lý

### 1. EC2 không xuất hiện trong Managed Nodes

Các nội dung được kiểm tra:

* SSM Agent.
* IAM Role.
* Instance Profile.
* DNS Resolution.
* Interface Endpoint.
* Security Group TCP 443.
* Kết nối đến Systems Manager.

Lệnh kiểm tra:

```bash
sudo systemctl status amazon-ssm-agent
sudo systemctl restart amazon-ssm-agent
```

---

### 2. Private EC2 không kết nối được Systems Manager

Nguyên nhân có thể:

* Thiếu Endpoint.
* Private DNS chưa bật.
* Endpoint Security Group chặn HTTPS.
* Subnet chưa có NAT Gateway.
* IAM Role không đủ quyền.
* SSM Agent chưa chạy.

---

### 3. Port Forwarding hoạt động nhưng RDP thất bại

Các nội dung được kiểm tra:

* Windows EC2 đang chạy.
* RDP Service.
* Cổng đích `3389`.
* Local Port chưa bị ứng dụng khác sử dụng.
* Security Group giữa Managed Instance và Windows EC2.
* Route giữa hai Subnet hoặc VPC.
* Windows Firewall.

---

### 4. Session Log không xuất hiện trên S3

Các nguyên nhân được rà soát:

* IAM Role thiếu `s3:PutObject`.
* Bucket Policy chưa cho phép.
* Session Manager Preferences sai.
* KMS Key Policy chưa cho phép mã hóa.
* Session chưa kết thúc hoàn toàn.

---

### 5. VPC Peering Active nhưng không có kết nối

Cách xử lý:

* Kiểm tra CIDR không chồng lấn.
* Thêm Route ở cả hai phía.
* Kiểm tra Security Group.
* Kiểm tra NACL.
* Bật DNS Resolution khi sử dụng Hostname.
* Kiểm tra đúng Private IP.

---

### 6. Transit Gateway Attachment Available nhưng Traffic thất bại

Các thành phần được kiểm tra:

* Source VPC Route Table.
* Transit Gateway Association.
* Transit Gateway Propagation.
* Transit Gateway Route Table.
* Destination VPC Route Table.
* Security Group.
* Network ACL.
* Return Route.

---

### 7. Resolver Endpoint hoạt động nhưng DNS Timeout

Các nguyên nhân được kiểm tra:

* TCP/UDP 53 bị chặn.
* Resolver Rule sai Domain.
* Sai Target DNS Server IP.
* Thiếu Route đến DNS Server.
* Rule chưa được Association với VPC.
* DNS Server không có bản ghi cần tìm.

---

## Quy trình troubleshooting đã hình thành

Khi xảy ra lỗi kết nối, thực hiện theo thứ tự:

1. Xác định Source và Destination.
2. Kiểm tra Private IP, ENI và Subnet.
3. Kiểm tra Route Table tại Source.
4. Kiểm tra VPC Peering hoặc Transit Gateway.
5. Kiểm tra Route Table tại Destination.
6. Kiểm tra Security Group ở hai phía.
7. Kiểm tra Network ACL.
8. Kiểm tra DNS nếu sử dụng Hostname.
9. Kiểm tra IAM Role nếu sử dụng AWS Service.
10. Kiểm tra Agent hoặc Service trên EC2.
11. Kiểm tra Log và Flow Log nếu chưa xác định được lỗi.

Quy trình này giúp tránh thay đổi nhiều cấu hình cùng lúc và hỗ trợ khoanh vùng nguyên nhân chính xác hơn.

---

## Kỹ năng đạt được

* Quản trị EC2 bằng Session Manager.
* Sử dụng IAM Role cho EC2.
* Tạo Interface VPC Endpoint.
* Ghi Session Log vào S3.
* Tạo Port Forwarding đến Windows EC2.
* Kết nối VPC bằng VPC Peering.
* Thiết kế Multi-VPC bằng Transit Gateway.
* Cấu hình Association và Propagation.
* Xây dựng Route 53 Resolver Endpoint.
* Phân tích vai trò của Direct Connect và Load Balancer.
* Xử lý lỗi liên quan đến IAM, DNS, Route và Firewall.

---

## Tự đánh giá

* Đã hiểu rõ hơn về:

  * Systems Manager Session Manager.
  * Interface VPC Endpoint.
  * VPC Peering.
  * Transit Gateway.
  * Hybrid Connectivity.
  * AWS Direct Connect.
  * Elastic Load Balancing.
  * Route 53 Resolver.
  * Microsoft Active Directory và DNS.

* Có khả năng:

  * Quản trị EC2 không sử dụng Public IP.
  * Kết nối Windows EC2 bằng Port Forwarding.
  * Kết nối hai VPC bằng Peering.
  * Thiết kế kết nối tập trung bằng Transit Gateway.
  * Phân tích luồng DNS trong Hybrid Cloud.
  * Kiểm tra lỗi dựa trên IAM, DNS, routing và firewall.

* Nội dung cần cải thiện:

  * Hiểu sâu hơn về Endpoint Policy.
  * Thực hành đọc Transit Gateway Route Table.
  * Nghiên cứu thêm các cổng dịch vụ Active Directory.
  * Thực hành Load Balancer với Auto Scaling.
  * Tìm hiểu quy trình triển khai Direct Connect thực tế.
  * Tối ưu chi phí của Interface Endpoint và Transit Gateway.

---

## Kế hoạch tiếp theo

* Nghiên cứu thêm:

  * BGP Routing.
  * Direct Connect Gateway.
  * AWS Network Firewall.
  * VPC Flow Logs.
  * AWS Cloud WAN.
  * Gateway Load Balancer.

* Tiếp tục thực hành:

  * Thu thập VPC Flow Logs.
  * Xây dựng Centralized Inspection VPC.
  * Kết nối Transit Gateway giữa nhiều Region.
  * Tách môi trường Development, Testing và Production.
  * Triển khai Application Load Balancer.
  * Thiết lập DNS Forwarding có tính sẵn sàng cao.
  * Xây dựng mô hình Hybrid Cloud kết hợp VPN, Direct Connect và Route 53 Resolver.

---

