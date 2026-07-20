
---
title: "Worklog tuần 2"
date: 2026-05-03
weight: 1
chapter: false
pre: " <b> 1.2. </b> "

---

## Mục tiêu tuần 2

* Nghiên cứu phần đầu của Module 02 về Amazon Virtual Private Cloud.
* Hiểu cách thiết kế mạng riêng trên AWS bằng VPC, Subnet và CIDR.
* Phân biệt Public Subnet và Private Subnet.
* Tìm hiểu vai trò của Route Table, Internet Gateway, NAT Gateway, Elastic IP và ENI.
* Nghiên cứu cơ chế bảo mật mạng bằng Security Group và Network ACL.
* Thực hành xây dựng kết nối AWS Site-to-Site VPN.
* Sử dụng EC2 và Libreswan để mô phỏng Customer Gateway.
* Rèn luyện kỹ năng kiểm tra lỗi liên quan đến routing, firewall và IPsec VPN.

---

## Các công việc thực hiện trong tuần

| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --- | --- | --- | --- |
| 1 | - Hoàn tất quá trình kích hoạt AWS Account <br> - Kiểm tra và xác nhận 100 USD AWS Credit <br> - Thiết lập MFA để tăng cường bảo mật tài khoản <br> - Chuẩn bị môi trường cho các bài thực hành Networking | 05/01/2026 | 05/01/2026 | https://www.youtube.com/watch?v=2QSXYi6Ofmc&list=PLgT9f4ZU9cncuJ5ACqQxook4yKO1xuZP6&index=10, https://www.youtube.com/watch?v=dCs6UWGMe_A&list=PLgT9f4ZU9cncuJ5ACqQxook4yKO1xuZP6&index=11 |
| 2 | - Nghiên cứu Module 02-01 về Amazon VPC <br> - Tìm hiểu VPC, Subnet, CIDR, ENI và Elastic IP <br> - Thực hành chia dải `10.0.0.0/16` thành các Subnet `/24` | 05/02/2026 | 05/02/2026 | https://www.youtube.com/watch?v=O9Ac_vGHquM&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=25 |
| 3 | - Tạo VPC và các Public/Private Subnet <br> - Gắn Internet Gateway vào VPC <br> - Cấu hình Route Table cho Public Subnet <br> - Khởi tạo EC2 và kiểm tra kết nối Internet | 05/02/2026 | 05/02/2026 | https://000003.awsstudygroup.com/vi/6-cleanup/, https://www.youtube.com/watch?v=O9Ac_vGHquM&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=25 |
| 4 | - Cấp phát Elastic IP và tạo NAT Gateway <br> - Cập nhật Route Table cho Private Subnet <br> - Kiểm tra kết nối outbound từ Private EC2 <br> - Theo dõi tài nguyên có khả năng phát sinh chi phí | 05/02/2026 | 05/02/2026 | https://000003.awsstudygroup.com/vi/6-cleanup/, https://www.youtube.com/watch?v=O9Ac_vGHquM&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=25 |
| 5 | - Nghiên cứu phần VPC Security của Module 02-02 <br> - Thiết lập Security Group và Network ACL <br> - So sánh cơ chế Stateful và Stateless <br> - Kiểm tra lưu lượng SSH, ICMP và các Ephemeral Port | 05/03/2026 | 05/03/2026 | https://000003.awsstudygroup.com/vi/6-cleanup/, https://www.youtube.com/watch?v=BPuD1l2hEQ4&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=26 |
| 6 | - Nghiên cứu phần VPN của Module 02-03 <br> - Sử dụng EC2 làm Customer Gateway <br> - Tạo Virtual Private Gateway và VPN Connection <br> - Tải cấu hình cho hai VPN Tunnel | 05/03/2026 | 05/03/2026 | https://000003.awsstudygroup.com/vi/6-cleanup/, https://www.youtube.com/watch?v=CXU8D3kyxIc&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=27 |
| 7 | - Cài đặt và cấu hình Libreswan IPsec trên EC2 <br> - Kiểm tra IKE Phase 1 và IPsec Phase 2 <br> - Xử lý lỗi liên quan đến Security Group, Route Table và NAT Traversal <br> - Tổng hợp kiến thức phần đầu của Module 02 | 05/03/2026 | 05/03/2026 | https://000003.awsstudygroup.com/vi/6-cleanup/, https://www.youtube.com/watch?v=CXU8D3kyxIc&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=27 |

---

## Kết quả đạt được tuần 2

### 1. Hoàn thành phần đầu của Module 02

Nội dung Module 02 được phân chia trong Week 2 như sau:

| Nội dung | Phạm vi nghiên cứu |
| --- | --- |
| Module 02-01 | Amazon VPC, Subnet, CIDR, ENI, Elastic IP, Internet Gateway và NAT Gateway |
| Module 02-02 – Phần 1 | VPC Security với Security Group và Network ACL |
| Module 02-03 – Phần 1 | AWS Site-to-Site VPN, Customer Gateway và IPsec Tunnel |

Qua phần học này, đã hình thành được kiến thức nền tảng về cách tổ chức mạng riêng, kết nối Internet và bảo vệ lưu lượng trong AWS.

---

### 2. Thiết kế mạng bằng Amazon VPC

* Hiểu Amazon VPC cung cấp một môi trường mạng riêng biệt trên AWS.
* Có thể tự lựa chọn CIDR Block cho VPC và Subnet.
* Thực hành chia dải mạng:

```text
VPC: 10.11.0.0/16
├── Public Subnet: 10.11.1.0/24
└── Private Subnet: 10.11.2.0/24
```

* Hiểu mỗi Subnet chỉ thuộc một Availability Zone.
* Biết cách lựa chọn dải CIDR không chồng lấn để chuẩn bị cho kết nối nhiều VPC.
* Phân biệt tài nguyên được triển khai trong Public Subnet và Private Subnet.

---

### 3. Public Subnet và Internet Gateway

Đã thực hiện:

* Tạo Internet Gateway.
* Gắn Internet Gateway vào VPC.
* Tạo Public Route Table.
* Thêm Default Route:

```text
Destination: 0.0.0.0/0
Target: Internet Gateway
```

* Liên kết Route Table với Public Subnet.
* Khởi tạo EC2 có Public IP.
* Kiểm tra SSH và kết nối Internet.

Hiểu rằng một Subnet được xem là Public Subnet khi Route Table của nó có đường đi đến Internet Gateway. Việc chỉ gán Public IP cho EC2 chưa đủ nếu Route Table chưa được cấu hình đúng.

---

### 4. Private Subnet và NAT Gateway

Đã thực hiện:

* Cấp phát Elastic IP.
* Tạo NAT Gateway trong Public Subnet.
* Tạo Private Route Table.
* Cấu hình Default Route của Private Subnet đến NAT Gateway.
* Kiểm tra khả năng truy cập Internet theo chiều outbound của Private EC2.

Luồng kết nối:

```text
Private EC2
    ↓
Private Route Table
    ↓
NAT Gateway
    ↓
Internet Gateway
    ↓
Internet
```

Rút ra được:

* NAT Gateway phải nằm trong Public Subnet.
* NAT Gateway cần được gắn Elastic IP.
* Public Subnet chứa NAT Gateway phải có Route đến Internet Gateway.
* NAT Gateway cho phép Private EC2 kết nối outbound nhưng không cho phép Internet chủ động kết nối trực tiếp vào EC2.

---

### 5. Elastic Network Interface và Elastic IP

#### Elastic Network Interface

Hiểu ENI chứa các thông tin mạng của EC2:

* Primary Private IP.
* Secondary Private IP.
* MAC Address.
* Security Group.
* Thông tin gắn với Subnet.

#### Elastic IP

Elastic IP được sử dụng để:

* Cung cấp Public IP tĩnh cho NAT Gateway.
* Gán địa chỉ ổn định cho EC2 làm Customer Gateway.
* Hạn chế việc thay đổi Public IP sau khi dừng hoặc khởi động lại tài nguyên.

Rút ra được:

* Elastic IP không được sử dụng đúng cách vẫn có thể phát sinh chi phí.
* Cần Disassociate trước khi Release trong một số trường hợp.
* Sau khi hoàn thành bài thực hành phải kiểm tra lại danh sách Elastic IP còn tồn tại.

---

### 6. Bảo mật bằng Security Group

* Hiểu Security Group được gắn với ENI hoặc tài nguyên.
* Security Group hoạt động theo cơ chế Stateful.
* Khi một request được cho phép đi vào, response tương ứng được tự động cho phép đi ra.

Các rule đã thực hành:

* TCP 22 cho SSH.
* ICMP cho quá trình kiểm tra kết nối.
* UDP 500 cho IKE.
* UDP 4500 cho NAT Traversal.
* Các rule nội bộ giữa những EC2 trong VPC.

Nguyên tắc áp dụng:

* Chỉ mở cổng cần thiết.
* Giới hạn Source CIDR.
* Không sử dụng `0.0.0.0/0` cho cổng quản trị nếu không cần thiết.
* Tách Security Group theo vai trò của từng tài nguyên.

---

### 7. Kiểm soát Subnet bằng Network ACL

* Hiểu Network ACL hoạt động ở cấp độ Subnet.
* Network ACL là Stateless.
* Cần cấu hình cả Inbound Rule và Outbound Rule.
* Network ACL hỗ trợ cả `ALLOW` và `DENY`.
* Rule được đánh giá theo thứ tự từ số nhỏ đến số lớn.

Phân biệt:

| Security Group | Network ACL |
| --- | --- |
| Hoạt động ở ENI hoặc tài nguyên | Hoạt động ở Subnet |
| Stateful | Stateless |
| Chỉ có Allow Rule | Có Allow và Deny Rule |
| Không cần mở riêng response traffic | Phải cho phép cả hai chiều |
| Mọi rule được đánh giá | Dừng tại rule đầu tiên phù hợp |

---

### 8. Xây dựng AWS Site-to-Site VPN

Mô hình được triển khai:

```text
Private Network
      ↓
EC2 Customer Gateway
      ↓
Encrypted IPsec Tunnel
      ↓
Virtual Private Gateway
      ↓
AWS VPC
```

Các thành phần chính:

* Customer Gateway.
* Virtual Private Gateway.
* Site-to-Site VPN Connection.
* Hai IPsec Tunnel.
* Static Route hoặc Dynamic Routing.
* Route Table của VPC.

Hiểu rằng:

* Site-to-Site VPN kết nối mạng riêng bên ngoài với Amazon VPC.
* Dữ liệu được mã hóa khi truyền qua Internet.
* AWS tạo hai Tunnel để tăng khả năng dự phòng.
* Tunnel ở trạng thái `UP` chưa đảm bảo traffic hoạt động nếu Route Table hoặc firewall chưa đúng.

---

### 9. Cấu hình Customer Gateway bằng EC2

* Sử dụng EC2 có Elastic IP làm Customer Gateway mô phỏng.
* Tắt Source/Destination Check để EC2 có thể chuyển tiếp traffic.
* Bật IP Forwarding trong hệ điều hành.
* Cho phép các cổng phục vụ VPN trên Security Group.
* Gắn Route phù hợp cho các mạng private.

Các yếu tố cần kiểm tra:

* Public IP của Customer Gateway.
* CIDR của mạng phía Customer Gateway.
* CIDR của Amazon VPC.
* Virtual Private Gateway Attachment.
* Route Table ở hai phía.
* Security Group và Network ACL.

---

### 10. Cấu hình Libreswan IPsec

Đã chỉnh sửa các file:

* `/etc/ipsec.conf`
* `/etc/ipsec.d/aws.conf`
* `/etc/ipsec.secrets`

Các thành phần được cấu hình:

* IKE cho quá trình thương lượng Phase 1.
* ESP và thuật toán mã hóa cho Phase 2.
* Pre-shared Key.
* Local Subnet và Remote Subnet.
* Tunnel Endpoint.
* Dead Peer Detection.

Các lệnh kiểm tra:

```bash
sudo systemctl status ipsec
sudo systemctl restart ipsec
sudo ipsec status
sudo ipsec verify
```

---

### 11. Phân biệt IKE Phase 1 và IPsec Phase 2

#### Phase 1

* Xác thực hai VPN Endpoint.
* Thương lượng thuật toán mã hóa.
* Thiết lập IKE Security Association.
* Sử dụng Pre-shared Key hoặc Certificate.

#### Phase 2

* Thương lượng cách bảo vệ dữ liệu thực tế.
* Xác định Local và Remote Subnet.
* Thiết lập IPsec Security Association.
* Sử dụng ESP để mã hóa lưu lượng.

Hiểu rằng:

* Phase 1 thành công chưa có nghĩa Phase 2 thành công.
* Hai phía phải thống nhất thuật toán và thông số Tunnel.
* CIDR hoặc Route sai có thể làm Tunnel được thiết lập nhưng không truyền được dữ liệu.

---

## Các lỗi thực tế đã xử lý

### 1. VPN Tunnel không chuyển sang trạng thái UP

Trạng thái quan sát được:

```text
STATE_MAIN_I1
```

Các nguyên nhân được kiểm tra:

* Public IP của Customer Gateway.
* Pre-shared Key.
* UDP 500.
* UDP 4500.
* IKE Version.
* Thuật toán mã hóa.
* NAT Traversal.
* Dịch vụ Libreswan.

---

### 2. Security Group chưa cho phép VPN Traffic

Cách xử lý:

* Cho phép UDP 500 từ VPN Endpoint phù hợp.
* Cho phép UDP 4500 khi sử dụng NAT Traversal.
* Kiểm tra Outbound Rule.
* Không mở cổng VPN cho toàn bộ Internet nếu có thể giới hạn Source.

---

### 3. EC2 không chuyển tiếp Traffic

Nguyên nhân:

* Source/Destination Check chưa được tắt.
* IP Forwarding chưa được bật.
* Route Table chưa trỏ đến EC2 Customer Gateway.
* Security Group hoặc NACL chặn traffic.

Các nội dung được kiểm tra:

```bash
sysctl net.ipv4.ip_forward
```

---

### 4. Cấu hình Libreswan không đúng

Lỗi liên quan đến việc sử dụng:

```text
auth=esp
```

Cách xử lý:

* Kiểm tra lại cú pháp tương thích với phiên bản Libreswan.
* Sử dụng `phase2alg` để khai báo thuật toán Phase 2.
* So sánh cấu hình với file VPN Configuration tải từ AWS.
* Khởi động lại dịch vụ sau khi thay đổi.

---

### 5. Ping một chiều

Kết quả:

* Ping từ một phía đến EC2 thành công.
* Chiều ngược lại chưa hoạt động.

Phương pháp xử lý:

* Kiểm tra Route Table hai chiều.
* Kiểm tra Local và Remote Subnet trong Libreswan.
* Kiểm tra Security Group.
* Kiểm tra NACL.
* Kiểm tra IP Forwarding.
* Kiểm tra trạng thái Phase 2.

---

## Kỹ năng đạt được

* Thiết kế VPC và chia dải CIDR.
* Xây dựng Public và Private Subnet.
* Cấu hình Internet Gateway và NAT Gateway.
* Quản lý Elastic IP và ENI.
* Thiết kế Security Group theo Least Privilege.
* Cấu hình Network ACL.
* Triển khai Site-to-Site VPN cơ bản.
* Sử dụng EC2 làm Customer Gateway.
* Cài đặt và kiểm tra Libreswan.
* Phân tích lỗi theo routing, firewall và IPsec.

---

## Tự đánh giá

* Đã hiểu rõ hơn về:

  * Amazon VPC.
  * CIDR và Subnet.
  * Route Table.
  * Internet Gateway.
  * NAT Gateway.
  * Security Group.
  * Network ACL.
  * Customer Gateway.
  * Virtual Private Gateway.
  * Site-to-Site VPN.
  * IKE và IPsec.

* Có khả năng:

  * Xây dựng mô hình VPC cơ bản.
  * Tách Public và Private Network.
  * Cung cấp kết nối outbound cho Private EC2.
  * Thiết lập rule bảo mật ở cấp tài nguyên và Subnet.
  * Cấu hình Site-to-Site VPN cơ bản.
  * Kiểm tra trạng thái Tunnel và khoanh vùng lỗi.

* Nội dung cần tiếp tục cải thiện:

  * Hoàn thiện kết nối hai chiều qua VPN.
  * Hiểu sâu hơn về Dynamic Routing và BGP.
  * Thực hành VPN với thiết bị Customer Gateway thực tế.
  * Sử dụng VPC Flow Logs để phân tích traffic.
  * Tối ưu chi phí của NAT Gateway và Elastic IP.

---

## Kế hoạch tiếp theo

* Tiếp tục nghiên cứu phần Multi-VPC của Module 02-02.
* Nghiên cứu phần tiếp theo của Module 02-03.
* Thực hành:

  * AWS Systems Manager Session Manager.
  * Interface VPC Endpoint.
  * VPC Peering.
  * AWS Transit Gateway.
  * Route 53 Resolver.
  * Hybrid DNS.
  * Microsoft Active Directory.

* So sánh các mô hình kết nối:

  * VPC Peering.
  * Transit Gateway.
  * Site-to-Site VPN.
  * AWS Direct Connect.

* Tiếp tục hoàn thiện kỹ năng troubleshooting theo từng lớp mạng.

---

