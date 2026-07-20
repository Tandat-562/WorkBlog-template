
---
title: "Worklog tuần 9"
date: 2026-06-21
weight: 1
chapter: false
pre: " <b> 1.9. </b> "

---

## Mục tiêu tuần 9

* Hoàn thành Module 06 về các dịch vụ cơ sở dữ liệu trên AWS.
* Ôn tập các khái niệm cơ bản về hệ quản trị cơ sở dữ liệu.
* Phân biệt cơ sở dữ liệu quan hệ, phi quan hệ, cơ sở dữ liệu giao dịch và kho dữ liệu phân tích.
* Hiểu cách lựa chọn dịch vụ cơ sở dữ liệu phù hợp với từng loại workload.
* Nghiên cứu kiến trúc và cơ chế vận hành của Amazon RDS.
* Tìm hiểu Amazon Aurora, Aurora Cluster và các loại Database Endpoint.
* Phân biệt Multi-AZ Deployment và Read Replica.
* Tìm hiểu cơ chế Automated Backup, Manual Snapshot và Point-in-Time Recovery.
* Nghiên cứu Amazon Redshift và kiến trúc Data Warehouse trên AWS.
* Tìm hiểu Amazon ElastiCache và vai trò của bộ nhớ đệm trong việc tăng hiệu năng ứng dụng.
* Phân biệt Valkey, Redis OSS và Memcached.
* Rèn luyện kỹ năng kiểm tra lỗi kết nối, quyền truy cập, routing, Security Group và cấu hình cơ sở dữ liệu.

---

## Các công việc thực hiện trong tuần

| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --- | --- | --- | --- |
| 1 | - Nghiên cứu Module 06-01 về các khái niệm cơ sở dữ liệu <br> - Phân biệt dữ liệu có cấu trúc, bán cấu trúc và phi cấu trúc <br> - Tìm hiểu Database Management System và các loại Database phổ biến <br> - Phân tích sự khác nhau giữa SQL và NoSQL | 15/06/2026 | 15/06/2026 | https://www.youtube.com/watch?v=OOD2RwWuLRw&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=217 |
| 2 | - Tiếp tục Module 06-01 <br> - Tìm hiểu Primary Key, Foreign Key, Index và Relationship <br> - Phân biệt OLTP và OLAP <br> - Phân tích cách lựa chọn Purpose-Built Database theo từng loại workload | 16/06/2026 | 16/06/2026 | https://www.youtube.com/watch?v=OOD2RwWuLRw&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=217 |
| 3 | - Nghiên cứu Module 06-02 về Amazon RDS và Amazon Aurora <br> - Tìm hiểu các Database Engine được Amazon RDS hỗ trợ <br> - Phân tích DB Instance, Storage, Subnet Group, Parameter Group và Option Group <br> - Tìm hiểu cơ chế Multi-AZ và Read Replica | 17/06/2026 | 17/06/2026 | https://www.youtube.com/watch?v=qbrobQZrokY&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=218 |
| 4 | - Thực hành khởi tạo Amazon RDS Database <br> - Cấu hình VPC, DB Subnet Group và Security Group <br> - Kết nối EC2 với RDS bằng Private Endpoint <br> - Tạo Database, Table và thực hiện các câu lệnh SQL cơ bản <br> - Kiểm tra Automated Backup và Manual Snapshot | 18/06/2026 | 18/06/2026 | https://www.youtube.com/watch?v=qbrobQZrokY&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=218 |
| 5 | - Tìm hiểu kiến trúc Amazon Aurora <br> - Phân biệt Writer Instance và Reader Instance <br> - Tìm hiểu Cluster Endpoint, Reader Endpoint và Instance Endpoint <br> - Phân tích Aurora Replication, Failover và khả năng mở rộng đọc | 19/06/2026 | 19/06/2026 | https://www.youtube.com/watch?v=qbrobQZrokY&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=218 |
| 6 | - Nghiên cứu Module 06-03 về Amazon Redshift và Amazon ElastiCache <br> - Phân biệt Transactional Database và Data Warehouse <br> - Tìm hiểu Redshift Cluster, Node, Columnar Storage và Massively Parallel Processing <br> - Phân tích quá trình nạp dữ liệu từ Amazon S3 vào Redshift | 20/06/2026 | 20/06/2026 | https://www.youtube.com/watch?v=UvdiRW34aNI&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=219 |
| 7 | - Tìm hiểu Amazon ElastiCache <br> - Phân biệt Valkey, Redis OSS và Memcached <br> - Phân tích Cache-Aside, Write-Through và Session Caching <br> - So sánh RDS, Aurora, Redshift và ElastiCache <br> - Rà soát và xóa các tài nguyên thực hành không còn sử dụng | 21/06/2026 | 21/06/2026 | https://www.youtube.com/watch?v=UvdiRW34aNI&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=219 |

---

## Kết quả đạt được tuần 9

### 1. Hoàn thành Module 06

Các nội dung chính đã được nghiên cứu:

| Module | Nội dung |
| --- | --- |
| Module 06-01 | Ôn tập các khái niệm cơ sở dữ liệu |
| Module 06-02 | Amazon RDS và Amazon Aurora |
| Module 06-03 | Amazon Redshift và Amazon ElastiCache |

Sau khi hoàn thành Module 06, đã hiểu rõ hơn cách lựa chọn dịch vụ cơ sở dữ liệu dựa trên cấu trúc dữ liệu, loại truy vấn, yêu cầu hiệu năng, khả năng mở rộng và mức độ sẵn sàng.

---

### 2. Tổng quan về cơ sở dữ liệu

Cơ sở dữ liệu được sử dụng để lưu trữ, tổ chức, truy xuất và quản lý dữ liệu.

Một hệ thống cơ sở dữ liệu thường gồm:

```text
Application
    ↓
Database Connection
    ↓
Database Management System
    ↓
Database
    ↓
Storage
```

Các chức năng chính của hệ quản trị cơ sở dữ liệu:

* Lưu trữ dữ liệu.
* Truy vấn dữ liệu.
* Cập nhật và xóa dữ liệu.
* Kiểm soát tính nhất quán.
* Quản lý nhiều kết nối.
* Kiểm soát quyền truy cập.
* Thực hiện sao lưu và khôi phục.
* Ghi nhận Transaction và Log.

---

### 3. Phân loại dữ liệu

#### Dữ liệu có cấu trúc

Dữ liệu được tổ chức theo Schema xác định.

Ví dụ:

* Bảng người dùng.
* Đơn hàng.
* Sản phẩm.
* Giao dịch tài chính.

Dữ liệu có cấu trúc thường phù hợp với cơ sở dữ liệu quan hệ.

#### Dữ liệu bán cấu trúc

Dữ liệu có cấu trúc linh hoạt hơn.

Ví dụ:

* JSON.
* XML.
* Event Log.
* API Response.

#### Dữ liệu phi cấu trúc

Dữ liệu không được tổ chức theo bảng truyền thống.

Ví dụ:

* Hình ảnh.
* Video.
* Tài liệu.
* Audio.
* Tệp nhị phân.

---

### 4. Cơ sở dữ liệu quan hệ

Cơ sở dữ liệu quan hệ tổ chức dữ liệu thành các bảng.

Ví dụ:

```text
Customers
├── customer_id
├── customer_name
└── email

Orders
├── order_id
├── customer_id
├── order_date
└── total_amount
```

Mối quan hệ giữa các bảng được thiết lập thông qua Key.

#### Primary Key

* Xác định duy nhất một bản ghi.
* Không được trùng lặp.
* Thường không được để trống.

#### Foreign Key

* Tham chiếu đến Primary Key của bảng khác.
* Giúp duy trì mối quan hệ giữa các bảng.
* Hỗ trợ bảo đảm tính toàn vẹn dữ liệu.

#### Index

* Tăng tốc quá trình tìm kiếm dữ liệu.
* Có thể làm tăng chi phí ghi dữ liệu và dung lượng lưu trữ.
* Cần được thiết kế theo Query Pattern thực tế.

---

### 5. Cơ sở dữ liệu phi quan hệ

Cơ sở dữ liệu phi quan hệ phù hợp với dữ liệu có Schema linh hoạt hoặc yêu cầu mở rộng lớn.

Các mô hình phổ biến:

| Mô hình | Ví dụ dữ liệu |
| --- | --- |
| Key–Value | Session, Shopping Cart và User Preference |
| Document | JSON Document và Content Catalog |
| Graph | Social Network và Recommendation |
| In-Memory | Cache, Leaderboard và Session |
| Time Series | Metric, IoT và Monitoring Data |

Khi lựa chọn Database cần dựa trên Access Pattern thay vì chỉ dựa trên cách dữ liệu được hiển thị.

---

### 6. Phân biệt SQL và NoSQL

| SQL Database | NoSQL Database |
| --- | --- |
| Sử dụng Schema tương đối cố định | Schema linh hoạt |
| Dữ liệu được tổ chức theo bảng | Có nhiều mô hình dữ liệu |
| Hỗ trợ JOIN | Thường tối ưu theo Access Pattern |
| Phù hợp với Transaction phức tạp | Phù hợp với khả năng mở rộng lớn |
| Thường sử dụng SQL | Sử dụng API hoặc Query Language riêng |
| Tập trung vào quan hệ dữ liệu | Tập trung vào tốc độ và khả năng mở rộng |

Không có loại Database phù hợp cho mọi trường hợp. Kiến trúc hiện đại có thể sử dụng nhiều loại Database cho những chức năng khác nhau.

---

### 7. Transaction và tính chất ACID

Transaction là một nhóm thao tác được xử lý như một đơn vị công việc.

ACID bao gồm:

#### Atomicity

Transaction phải hoàn thành toàn bộ hoặc không thực hiện thay đổi nào.

#### Consistency

Dữ liệu phải chuyển từ trạng thái hợp lệ này sang trạng thái hợp lệ khác.

#### Isolation

Các Transaction đồng thời không được gây ảnh hưởng sai lệch lẫn nhau.

#### Durability

Sau khi Transaction được xác nhận, dữ liệu phải được lưu bền vững.

Các hệ thống thanh toán, đặt hàng và quản lý tài chính thường cần đặc tính ACID mạnh.

---

### 8. OLTP và OLAP

#### Online Transaction Processing

OLTP phù hợp với:

* Giao dịch hằng ngày.
* Nhiều thao tác ghi nhỏ.
* Truy vấn theo từng bản ghi.
* Yêu cầu độ trễ thấp.
* Dữ liệu hiện tại.

Ví dụ:

* Đặt hàng.
* Thanh toán.
* Đăng ký tài khoản.
* Quản lý kho.

#### Online Analytical Processing

OLAP phù hợp với:

* Phân tích dữ liệu.
* Truy vấn tổng hợp.
* Xử lý khối lượng dữ liệu lớn.
* Báo cáo và Business Intelligence.
* Dữ liệu lịch sử.

Ví dụ:

* Báo cáo doanh thu.
* Phân tích hành vi khách hàng.
* Dự báo xu hướng.
* Dashboard quản trị.

---

### 9. Purpose-Built Database

AWS cung cấp nhiều dịch vụ cơ sở dữ liệu cho các mục đích khác nhau.

Ví dụ:

| Nhu cầu | Dịch vụ phù hợp |
| --- | --- |
| Relational Database | Amazon RDS hoặc Amazon Aurora |
| Key–Value Database | Amazon DynamoDB |
| Data Warehouse | Amazon Redshift |
| In-Memory Cache | Amazon ElastiCache |
| Graph Database | Amazon Neptune |
| Time-Series Database | Amazon Timestream |
| Document Database | Amazon DocumentDB |

Nguyên tắc Purpose-Built Database giúp lựa chọn dịch vụ tối ưu cho từng Access Pattern thay vì đưa toàn bộ dữ liệu vào một hệ thống duy nhất.

---

### 10. Tổng quan Amazon RDS

Amazon RDS là dịch vụ cơ sở dữ liệu quan hệ được quản lý trên AWS.

AWS hỗ trợ thực hiện nhiều công việc quản trị:

* Cấp phát máy chủ Database.
* Cài đặt Database Engine.
* Quản lý Storage.
* Backup tự động.
* Monitoring.
* Thay thế phần cứng khi có sự cố.
* Cập nhật phiên bản theo cấu hình.
* Failover trong mô hình Multi-AZ.

Người dùng vẫn chịu trách nhiệm về:

* Thiết kế Schema.
* Tạo Table.
* Viết Query.
* Quản lý User trong Database.
* Thiết kế Index.
* Kiểm soát quyền truy cập.
* Tối ưu ứng dụng.

---

### 11. Các Database Engine của Amazon RDS

Amazon RDS hỗ trợ nhiều Database Engine phổ biến:

* MySQL.
* PostgreSQL.
* MariaDB.
* Oracle.
* Microsoft SQL Server.
* IBM Db2.
* Amazon Aurora MySQL-Compatible.
* Amazon Aurora PostgreSQL-Compatible.

Việc lựa chọn Engine cần dựa trên:

* Khả năng tương thích ứng dụng.
* Tính năng Database.
* Mô hình Licensing.
* Kinh nghiệm của đội ngũ.
* Yêu cầu hiệu năng.
* Khả năng mở rộng.
* Chi phí.

---

### 12. Kiến trúc Amazon RDS

Các thành phần chính:

```text
Application
    ↓
RDS Endpoint
    ↓
DB Instance
    ↓
Database Engine
    ↓
Database Storage
```

Trong môi trường VPC:

```text
Application EC2
      ↓
Security Group
      ↓
RDS Endpoint
      ↓
DB Subnet Group
      ↓
Amazon RDS Database
```

Các thành phần cấu hình:

* DB Instance Class.
* Database Engine.
* Allocated Storage.
* DB Subnet Group.
* Security Group.
* Parameter Group.
* Option Group.
* Backup Retention.
* Maintenance Window.
* Monitoring.

---

### 13. DB Subnet Group

DB Subnet Group là tập hợp các Subnet mà Amazon RDS có thể sử dụng.

Trong môi trường Production nên:

* Sử dụng Subnet thuộc nhiều Availability Zone.
* Đặt RDS trong Private Subnet.
* Không mở trực tiếp Database ra Internet.
* Chỉ cho phép Traffic từ ứng dụng hoặc Bastion Host cần thiết.
* Sử dụng Security Group Reference thay vì mở CIDR quá rộng.

Luồng truy cập đề xuất:

```text
Internet
   ↓
Load Balancer
   ↓
Application Server
   ↓
Private RDS Database
```

---

### 14. Multi-AZ Deployment

Multi-AZ được sử dụng để tăng tính sẵn sàng.

Mô hình cơ bản:

```text
Availability Zone A
Primary DB Instance
          ↓
Synchronous Replication
          ↓
Availability Zone B
Standby DB Instance
```

Khi Primary gặp sự cố:

```text
Primary Failure
      ↓
Amazon RDS detects failure
      ↓
Standby becomes Primary
      ↓
Database Endpoint is redirected
```

Đặc điểm:

* Tập trung vào High Availability.
* Standby không được sử dụng trực tiếp để xử lý Read Traffic trong mô hình Multi-AZ DB Instance truyền thống.
* Có thể tự động Failover.
* Ứng dụng tiếp tục sử dụng cùng một Endpoint.
* Không thay thế hoàn toàn Backup hoặc Disaster Recovery.

---

### 15. Read Replica

Read Replica được sử dụng để mở rộng khả năng đọc.

Mô hình:

```text
Primary Database
       ↓
Asynchronous Replication
       ↓
Read Replica 1
Read Replica 2
```

Trường hợp sử dụng:

* Báo cáo.
* Dashboard.
* Truy vấn đọc lớn.
* Tách Read Workload khỏi Primary.
* Hỗ trợ một số kịch bản Disaster Recovery.

Điểm cần lưu ý:

* Replication thường không đồng bộ.
* Có thể xảy ra Replication Lag.
* Ứng dụng phải kết nối đến Endpoint của Read Replica.
* Read Replica có thể được Promote thành Database độc lập trong một số trường hợp.

---

### 16. Phân biệt Multi-AZ và Read Replica

| Multi-AZ | Read Replica |
| --- | --- |
| Tăng High Availability | Tăng Read Scalability |
| Sử dụng Standby | Sử dụng Replica có thể đọc |
| Replication đồng bộ trong mô hình cơ bản | Replication thường không đồng bộ |
| Hỗ trợ Automatic Failover | Không tự động thay thế Primary theo cùng cơ chế |
| Ứng dụng dùng Endpoint chính | Ứng dụng cần kết nối Replica Endpoint |
| Không chủ yếu dùng cho Read Scaling | Được thiết kế cho Read Scaling |

Có thể sử dụng cả Multi-AZ và Read Replica trong cùng một kiến trúc để đáp ứng yêu cầu Availability và Scalability.

---

### 17. Backup và Snapshot của Amazon RDS

#### Automated Backup

* Được thực hiện tự động.
* Có Backup Retention Period.
* Hỗ trợ Point-in-Time Recovery.
* Bao gồm Snapshot và Transaction Log cần thiết.
* Được quản lý theo Backup Window.

#### Manual Snapshot

* Được tạo thủ công.
* Tồn tại cho đến khi người dùng xóa.
* Có thể dùng để tạo Database mới.
* Phù hợp với Backup trước thay đổi quan trọng.

Quy trình khôi phục:

```text
RDS Backup hoặc Snapshot
          ↓
Restore
          ↓
New DB Instance
          ↓
New Endpoint
          ↓
Validate Data
          ↓
Update Application Connection
```

Restore không ghi trực tiếp đè lên DB Instance hiện tại mà thường tạo một DB Instance mới.

---

### 18. Point-in-Time Recovery

Point-in-Time Recovery cho phép khôi phục Database về một thời điểm trong khoảng lưu giữ Backup.

Ví dụ:

```text
10:00 – Database hoạt động bình thường
10:15 – Dữ liệu bị xóa nhầm
10:20 – Phát hiện sự cố
```

Có thể khôi phục Database về thời điểm trước 10:15 nếu Backup và Transaction Log đáp ứng yêu cầu.

Sau khi Restore cần:

* Kiểm tra dữ liệu.
* Kiểm tra User và Permission.
* Kiểm tra Parameter.
* Kiểm tra Security Group.
* Cập nhật Endpoint của ứng dụng.
* Xác nhận tính toàn vẹn dữ liệu.

---

### 19. Amazon Aurora

Amazon Aurora là cơ sở dữ liệu quan hệ tương thích với MySQL và PostgreSQL.

Kiến trúc Aurora tách lớp Compute và Storage:

```text
Aurora DB Cluster
├── Writer Instance
├── Reader Instance 1
├── Reader Instance 2
└── Distributed Cluster Storage
```

Đặc điểm:

* Storage được quản lý ở cấp Cluster.
* Có một Writer Instance xử lý ghi.
* Có thể có nhiều Reader Instance.
* Hỗ trợ Failover giữa các Instance.
* Có thể mở rộng Read Workload.
* Tích hợp với Backup, Monitoring và AWS KMS.

---

### 20. Aurora Endpoint

#### Cluster Endpoint

* Thường kết nối đến Writer Instance.
* Được ứng dụng sử dụng cho thao tác ghi.
* Tự động chuyển đến Writer mới sau Failover.

#### Reader Endpoint

* Phân phối kết nối đọc giữa các Reader Instance.
* Được sử dụng để mở rộng Read Workload.
* Không phải Load Balancer ở cấp câu lệnh SQL.

#### Instance Endpoint

* Trỏ đến một DB Instance cụ thể.
* Thường dùng cho quản trị hoặc kiểm tra.
* Không tự động phân phối kết nối sang Instance khác.

Luồng ứng dụng:

```text
Write Request
     ↓
Cluster Endpoint
     ↓
Writer Instance

Read Request
     ↓
Reader Endpoint
     ↓
Reader Instances
```

---

### 21. Amazon Redshift

Amazon Redshift là dịch vụ Data Warehouse được quản lý trên AWS.

Redshift phù hợp với:

* Business Intelligence.
* Báo cáo.
* Phân tích dữ liệu lịch sử.
* Truy vấn tổng hợp.
* Phân tích dữ liệu với dung lượng lớn.
* Xây dựng Dashboard.
* Phân tích dữ liệu từ nhiều nguồn.

Redshift không được thiết kế để thay thế trực tiếp cơ sở dữ liệu OLTP cho từng giao dịch nhỏ của ứng dụng.

---

### 22. Kiến trúc Amazon Redshift

Mô hình Redshift Cluster:

```text
Client Application
        ↓
Leader Node
        ↓
Compute Nodes
        ↓
Node Slices
        ↓
Columnar Data Storage
```

#### Leader Node

* Nhận kết nối từ Client.
* Phân tích Query.
* Tạo Execution Plan.
* Phân phối công việc đến Compute Node.
* Tổng hợp kết quả.

#### Compute Node

* Lưu và xử lý dữ liệu.
* Thực hiện phần lớn công việc tính toán.
* Có thể được chia thành các Slice.

---

### 23. Columnar Storage

Trong Row-Based Storage, dữ liệu của một hàng được lưu gần nhau:

```text
Customer 1: ID, Name, City, Revenue
Customer 2: ID, Name, City, Revenue
```

Trong Columnar Storage, dữ liệu của một cột được lưu gần nhau:

```text
ID:      1, 2, 3, 4
Name:    A, B, C, D
City:    HN, HCM, DN, HP
Revenue: 100, 200, 300, 400
```

Columnar Storage phù hợp với phân tích vì:

* Chỉ đọc các cột cần thiết.
* Hỗ trợ nén dữ liệu hiệu quả.
* Tăng hiệu năng truy vấn tổng hợp.
* Giảm lượng dữ liệu cần quét.

---

### 24. Massively Parallel Processing

Amazon Redshift chia công việc truy vấn cho nhiều Compute Resource xử lý song song.

Luồng xử lý:

```text
SQL Query
    ↓
Leader Node creates execution plan
    ↓
Query is divided into smaller tasks
    ↓
Compute Nodes process tasks in parallel
    ↓
Results are combined
    ↓
Return result to client
```

Hiệu năng phụ thuộc vào:

* Cách phân phối dữ liệu.
* Sort Key.
* Distribution Style.
* Kích thước Cluster hoặc Workgroup.
* Chất lượng câu lệnh SQL.
* Dung lượng dữ liệu cần Scan.
* Workload Management.

---

### 25. Nạp dữ liệu vào Amazon Redshift

Một luồng phổ biến:

```text
Operational Systems
        ↓
Extract Data
        ↓
Amazon S3
        ↓
COPY Command
        ↓
Amazon Redshift
        ↓
Business Intelligence Tool
```

Khi nạp dữ liệu từ S3 cần kiểm tra:

* IAM Role của Redshift.
* Quyền đọc S3.
* Bucket và Object Key.
* Region.
* File Format.
* Data Type.
* Delimiter.
* Compression.
* Error Log.

---

### 26. Amazon ElastiCache

Amazon ElastiCache cung cấp môi trường In-Memory Data Store hoặc Cache được quản lý.

Luồng không sử dụng Cache:

```text
Application
     ↓
Database
     ↓
Return Data
```

Luồng sử dụng Cache:

```text
Application
     ↓
Check ElastiCache
  ┌───────┴────────┐
Cache Hit       Cache Miss
   ↓                ↓
Return Data       Query Database
                    ↓
                Update Cache
                    ↓
                Return Data
```

Lợi ích:

* Giảm độ trễ.
* Giảm số Query đến Database.
* Tăng khả năng xử lý Request.
* Cải thiện trải nghiệm người dùng.
* Giảm tải cho hệ thống Backend.

---

### 27. Valkey, Redis OSS và Memcached

| Valkey hoặc Redis OSS | Memcached |
| --- | --- |
| Hỗ trợ nhiều cấu trúc dữ liệu | Mô hình Key–Value đơn giản |
| Hỗ trợ Replication | Không hỗ trợ Replication theo cùng cơ chế |
| Có thể hỗ trợ Backup | Thường không tập trung vào Backup |
| Hỗ trợ Pub/Sub | Không có đầy đủ tính năng tương tự |
| Phù hợp với Session và Leaderboard | Phù hợp với Cache đơn giản |
| Có Primary và Replica | Có thể phân phối dữ liệu qua nhiều Node |
| Có thể hỗ trợ Automatic Failover | Thiết kế đơn giản hơn |

Việc lựa chọn phụ thuộc vào:

* Loại dữ liệu.
* Yêu cầu Persistence.
* High Availability.
* Cấu trúc dữ liệu.
* Khả năng mở rộng.
* Độ phức tạp vận hành.

---

### 28. Các chiến lược Caching

#### Cache-Aside

```text
Application kiểm tra Cache
        ↓
Cache Miss
        ↓
Đọc Database
        ↓
Ghi dữ liệu vào Cache
        ↓
Trả kết quả
```

Ưu điểm:

* Chỉ Cache dữ liệu được truy cập.
* Dễ áp dụng.
* Ứng dụng kiểm soát quá trình Cache.

Nhược điểm:

* Request đầu tiên vẫn phải đọc Database.
* Có thể xuất hiện dữ liệu cũ.

#### Write-Through

```text
Application ghi dữ liệu
        ↓
Cache được cập nhật
        ↓
Database được cập nhật
```

Ưu điểm:

* Cache thường có dữ liệu mới.
* Giảm Cache Miss sau khi ghi.

Nhược điểm:

* Tăng độ trễ khi ghi.
* Có thể Cache cả dữ liệu ít được đọc.

#### Time to Live

TTL xác định thời gian một Cache Entry được giữ lại.

Cần cân bằng giữa:

* Độ mới của dữ liệu.
* Tỷ lệ Cache Hit.
* Tải lên Database.
* Dung lượng bộ nhớ.

---

### 29. Bảo mật cơ sở dữ liệu

Các lớp bảo mật cần kiểm tra:

```text
IAM Permission
      ↓
VPC và Subnet
      ↓
Route Table
      ↓
Security Group
      ↓
Database Authentication
      ↓
Encryption
      ↓
Database User Permission
```

Các nguyên tắc:

* Đặt Database trong Private Subnet.
* Không mở cổng Database cho `0.0.0.0/0`.
* Chỉ cho phép Traffic từ Security Group của ứng dụng.
* Mã hóa dữ liệu khi lưu trữ.
* Sử dụng TLS khi truyền dữ liệu.
* Bảo vệ Secret và Password.
* Phân quyền Database theo Least Privilege.
* Theo dõi Log và Audit.
* Sao lưu định kỳ.
* Thường xuyên kiểm tra khả năng Restore.

---

### 30. Monitoring cơ sở dữ liệu

Các chỉ số cần theo dõi:

#### Amazon RDS và Aurora

* CPUUtilization.
* DatabaseConnections.
* FreeStorageSpace.
* FreeableMemory.
* ReadIOPS.
* WriteIOPS.
* ReadLatency.
* WriteLatency.
* ReplicaLag.
* Deadlock.
* Query Throughput.

#### Amazon Redshift

* CPUUtilization.
* DatabaseConnections.
* QueryDuration.
* ReadIOPS.
* WriteIOPS.
* PercentageDiskSpaceUsed.
* QueryQueueLength.

#### Amazon ElastiCache

* CPUUtilization.
* EngineCPUUtilization.
* CurrConnections.
* CacheHits.
* CacheMisses.
* Evictions.
* FreeableMemory.
* ReplicationLag.

Monitoring giúp phát hiện vấn đề trước khi hệ thống bị ảnh hưởng nghiêm trọng.

---

## Các lỗi thực tế đã xử lý

### 1. Không kết nối được Amazon RDS

Các nội dung được kiểm tra:

* DB Instance ở trạng thái `Available`.
* Endpoint và Port.
* VPC.
* DB Subnet Group.
* Route Table.
* Security Group.
* Network ACL.
* Public Accessibility.
* Username và Password.
* Database Name.
* DNS Resolution.
* Database Service.

Lệnh kiểm tra kết nối có thể sử dụng:

```bash
nc -zv <rds-endpoint> 3306
```

Hoặc:

```bash
mysql -h <rds-endpoint> -u <username> -p
```

---

### 2. RDS Connection Timeout

Nguyên nhân thường liên quan đến Network:

* Security Group chưa cho phép cổng Database.
* Source IP hoặc Security Group không chính xác.
* RDS nằm trong Private Subnet.
* Máy Client không có đường Route đến RDS.
* Network ACL chặn Traffic.
* Sai Endpoint hoặc Port.
* DNS không phân giải được.

Phân biệt:

* `Connection timeout` thường liên quan đến Network.
* `Access denied` thường liên quan đến Username, Password hoặc Database Permission.

---

### 3. Không đăng nhập được Database

Các nguyên nhân được kiểm tra:

* Sai Master Username.
* Sai Password.
* Kết nối nhầm Database.
* User chưa được cấp quyền.
* Host không được phép kết nối.
* Password chứa ký tự được Shell xử lý đặc biệt.
* Authentication Plugin không tương thích.

---

### 4. Nhầm lẫn Multi-AZ và Read Replica

Cách xử lý:

* Xác định mục tiêu là High Availability hay Read Scaling.
* Không gửi Read Query đến Multi-AZ Standby trong mô hình truyền thống.
* Sử dụng Read Replica Endpoint cho Read Workload.
* Theo dõi Replication Lag khi sử dụng Read Replica.
* Không xem Read Replica là giải pháp thay thế hoàn toàn cho Backup.

---

### 5. Restore Snapshot nhưng ứng dụng không kết nối được

Nguyên nhân:

* Restore tạo DB Instance mới.
* Endpoint đã thay đổi.
* Security Group chưa được gán đúng.
* Parameter Group khác với Database cũ.
* DB Subnet Group không phù hợp.
* Username hoặc Permission khác.
* Ứng dụng vẫn sử dụng Endpoint cũ.

---

### 6. Aurora Reader Endpoint không xử lý được thao tác ghi

Nguyên nhân:

* Reader Endpoint được thiết kế cho Read Connection.
* Ứng dụng gửi câu lệnh ghi đến Reader.
* Connection Pool chưa tách Read và Write.

Cách xử lý:

* Sử dụng Cluster Endpoint cho thao tác ghi.
* Sử dụng Reader Endpoint cho thao tác đọc.
* Tách cấu hình Connection trong ứng dụng.

---

### 7. Amazon Redshift không nạp được dữ liệu từ S3

Các nội dung được kiểm tra:

* IAM Role đã được gắn vào Redshift.
* Role có quyền `s3:GetObject`.
* Bucket và Object Key.
* Region.
* Cú pháp lệnh `COPY`.
* File Format.
* Delimiter.
* Data Type.
* Encoding.
* Error Table và Load Error.

---

### 8. Query Amazon Redshift chạy chậm

Các nguyên nhân được phân tích:

* Quét quá nhiều dữ liệu.
* Không sử dụng Filter phù hợp.
* Distribution Style chưa tối ưu.
* Sort Key không phù hợp.
* Data Skew.
* Query Queue.
* Workload Management.
* Cluster hoặc Serverless Capacity chưa đủ.
* Query thực hiện JOIN trên lượng dữ liệu lớn.

---

### 9. Không kết nối được Amazon ElastiCache

Các nguyên nhân được kiểm tra:

* ElastiCache chỉ có Private Endpoint.
* Client không nằm trong VPC hoặc không có kết nối đến VPC.
* Security Group chưa cho phép Port.
* Sai Endpoint.
* Sai Port.
* TLS Configuration.
* Subnet Group.
* Route Table.
* Network ACL.
* Cluster đang được tạo hoặc bảo trì.

---

### 10. Tỷ lệ Cache Hit thấp

Nguyên nhân có thể:

* TTL quá ngắn.
* Cache Key không nhất quán.
* Dữ liệu ít được truy cập lại.
* Cache bị Eviction.
* Dung lượng Memory không đủ.
* Ứng dụng chưa sử dụng Cache đúng vị trí.
* Cache bị xóa thường xuyên.

Cách cải thiện:

* Chuẩn hóa Cache Key.
* Điều chỉnh TTL.
* Theo dõi Cache Hit và Cache Miss.
* Tăng Capacity khi cần thiết.
* Chỉ Cache dữ liệu phù hợp.
* Kiểm tra chiến lược Invalidation.

---

## Quy trình troubleshooting Database đã hình thành

Khi ứng dụng không truy cập được Database, thực hiện kiểm tra theo thứ tự:

1. Xác định loại Database và Endpoint.
2. Kiểm tra trạng thái tài nguyên.
3. Kiểm tra Endpoint và Port.
4. Kiểm tra VPC, Subnet và Route Table.
5. Kiểm tra Security Group và Network ACL.
6. Kiểm tra DNS Resolution.
7. Kiểm tra Username, Password và Authentication.
8. Kiểm tra quyền của Database User.
9. Kiểm tra Connection Limit.
10. Kiểm tra Database Log và CloudWatch Metric.
11. Kiểm tra Query và Application Log.
12. Kiểm tra Backup hoặc Replica nếu lỗi liên quan đến dữ liệu.

Quy trình này giúp phân biệt lỗi Network, Authentication, Authorization, Capacity và Query Performance.

---

## Kỹ năng đạt được

* Phân biệt cơ sở dữ liệu quan hệ và phi quan hệ.
* Hiểu Primary Key, Foreign Key và Index.
* Phân biệt OLTP và OLAP.
* Hiểu nguyên tắc Purpose-Built Database.
* Nắm được kiến trúc Amazon RDS.
* Cấu hình DB Subnet Group và Security Group.
* Phân biệt Multi-AZ và Read Replica.
* Hiểu Automated Backup, Snapshot và Point-in-Time Recovery.
* Hiểu kiến trúc Amazon Aurora.
* Phân biệt Cluster, Reader và Instance Endpoint.
* Hiểu kiến trúc Amazon Redshift.
* Nắm được Columnar Storage và Massively Parallel Processing.
* Hiểu vai trò của Amazon ElastiCache.
* Phân biệt Valkey, Redis OSS và Memcached.
* Phân tích các chiến lược Caching.
* Kiểm tra lỗi kết nối và hiệu năng Database.

---

## Tự đánh giá

* Đã hoàn thành toàn bộ nội dung Module 06.
* Hiểu được các khái niệm nền tảng của hệ quản trị cơ sở dữ liệu.
* Có thể phân biệt Transactional Database, Analytical Database và Cache.
* Hiểu vai trò của Amazon RDS trong việc giảm công việc quản trị cơ sở dữ liệu.
* Có thể phân biệt Multi-AZ Deployment và Read Replica.
* Hiểu cơ chế sao lưu và khôi phục Amazon RDS.
* Nắm được kiến trúc Cluster của Amazon Aurora.
* Hiểu trường hợp sử dụng của Amazon Redshift.
* Hiểu cách ElastiCache giúp giảm tải cho Database.
* Cải thiện kỹ năng kiểm tra lỗi dựa trên Network, Authentication, Permission và Performance.

Nội dung cần tiếp tục cải thiện:

* Thực hành thêm các câu lệnh SQL.
* Tìm hiểu sâu hơn về Database Normalization.
* Thực hành Failover với Amazon RDS Multi-AZ.
* Theo dõi Replication Lag của Read Replica.
* Thực hành Aurora Reader Auto Scaling.
* Tìm hiểu Amazon RDS Proxy.
* Thực hành Amazon Redshift Serverless.
* Tối ưu Distribution Key và Sort Key.
* Thực hành ElastiCache với một ứng dụng thực tế.
* Tìm hiểu sâu hơn về DynamoDB và các NoSQL Database khác.
* Tối ưu chi phí Database và Storage.

---

## Kế hoạch tiếp theo

* Tham gia thảo luận nhóm để lựa chọn đề tài dự án AWS.
* Phân tích yêu cầu nghiệp vụ và vấn đề cần giải quyết.
* Xác định đối tượng người dùng của hệ thống.
* Xây dựng danh sách Functional Requirements và Non-Functional Requirements.
* Nghiên cứu các dịch vụ AWS có thể áp dụng vào dự án.
* Thiết kế sơ đồ kiến trúc AWS ban đầu.
* Phân chia nhiệm vụ giữa các thành viên.
* Xác định các thành phần cần triển khai:

  * Frontend.
  * Backend API.
  * Database.
  * File Storage.
  * AI Service.
  * Monitoring.
  * Security.
  * Notification.
  * Report Generation.

* Chuẩn bị chuyển sang giai đoạn thiết kế và triển khai dự án Capstone.

---

