
---
title: "Worklog tuần 10"
date: 2026-06-28
weight: 1
chapter: false
pre: " <b> 1.10. </b> "

---

## Mục tiêu tuần 10

* Bắt đầu giai đoạn xây dựng dự án Capstone sau khi hoàn thành các Module kiến thức nền tảng về AWS.
* Thảo luận và thống nhất đề tài **AI AWS Architecture Reviewer**.
* Xác định vấn đề thực tế mà dự án cần giải quyết.
* Xác định đối tượng người dùng và các trường hợp sử dụng chính.
* Phân tích Functional Requirements và Non-Functional Requirements.
* Xây dựng sơ đồ kiến trúc tổng thể cho hệ thống.
* Thiết kế luồng xử lý từ khi người dùng gửi sơ đồ kiến trúc đến khi nhận báo cáo đánh giá.
* Lựa chọn các dịch vụ AWS phù hợp với từng thành phần trong hệ thống.
* Áp dụng kiến trúc Serverless để tăng khả năng mở rộng và giảm công việc vận hành.
* Xác định cách Amazon Bedrock đánh giá kiến trúc dựa trên AWS Well-Architected Framework.
* Thiết kế cơ chế lưu trữ ảnh kiến trúc, kết quả đánh giá, báo cáo PDF và lịch sử Review.
* Xây dựng các nguyên tắc bảo mật, giám sát và tối ưu chi phí cho hệ thống.
* Phân chia phạm vi công việc ban đầu giữa các thành viên trong nhóm.

---

## Các công việc thực hiện trong tuần

| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --- | --- | --- | --- |
| 1 | - Thảo luận nhóm về các đề tài có thể triển khai trên AWS <br> - Phân tích những khó khăn khi sinh viên và Cloud Engineer đánh giá sơ đồ kiến trúc <br> - Đề xuất ý tưởng AI AWS Architecture Reviewer <br> - Thống nhất mục tiêu và phạm vi ban đầu của dự án | 22/06/2026 | 22/06/2026 | |
| 2 | - Xác định đối tượng người dùng của hệ thống <br> - Xây dựng các Use Case chính <br> - Xác định ba phương thức cung cấp dữ liệu đầu vào: ảnh sơ đồ, file Draw.io và mô tả kiến trúc <br> - Phân tích kết quả đầu ra mà người dùng cần nhận được | 23/06/2026 | 23/06/2026 | |
| 3 | - Xây dựng danh sách Functional Requirements <br> - Xác định các chức năng nhận diện dịch vụ AWS, phân tích kết nối, đánh giá kiến trúc và tính chi phí <br> - Xác định yêu cầu tạo báo cáo PDF, lưu lịch sử Review và gửi thông báo qua email | 24/06/2026 | 24/06/2026 | |
| 4 | - Phân tích Non-Functional Requirements <br> - Lựa chọn kiến trúc Serverless <br> - Đề xuất các dịch vụ CloudFront, S3, API Gateway, Lambda, EventBridge, Step Functions, Bedrock, DynamoDB, SNS, CloudWatch và IAM <br> - Xác định yêu cầu về bảo mật, khả năng mở rộng và tối ưu chi phí | 25/06/2026 | 25/06/2026 | |
| 5 | - Thiết kế sơ đồ kiến trúc tổng thể <br> - Xây dựng luồng từ giao diện React đến API Gateway và Lambda Upload Service <br> - Thiết kế Input Bucket và Report Bucket trên Amazon S3 <br> - Xác định EventBridge và Step Functions làm lớp điều phối Workflow | 26/06/2026 | 26/06/2026 | |
| 6 | - Thiết kế Processing Layer <br> - Xác định chức năng của Diagram Extractor Lambda, Cost Tool Lambda và PDF Generator Lambda <br> - Thiết kế luồng tích hợp với Amazon Bedrock <br> - Xây dựng cơ chế Retry, Error Handling và lưu lịch sử vào DynamoDB | 27/06/2026 | 27/06/2026 | |
| 7 | - Hoàn thiện sơ đồ luồng hoạt động của hệ thống <br> - Kiểm tra lại trách nhiệm của từng dịch vụ AWS <br> - Bổ sung IAM Least Privilege, CloudWatch Monitoring, SSE-S3 Encryption và SNS Notification <br> - Trình bày ý tưởng dự án với cộng đồng và tổng hợp góp ý | 28/06/2026 | 28/06/2026 | |

---

## Kết quả đạt được tuần 10

### 1. Thống nhất đề tài dự án

Nhóm đã thống nhất lựa chọn đề tài:

## AI AWS Architecture Reviewer

AI AWS Architecture Reviewer là hệ thống sử dụng trí tuệ nhân tạo để tự động phân tích và đánh giá sơ đồ kiến trúc AWS.

Người dùng có thể cung cấp thông tin kiến trúc theo ba hình thức:

* Tải lên ảnh sơ đồ kiến trúc AWS.
* Tải lên file Draw.io.
* Nhập trực tiếp mô tả kiến trúc bằng văn bản.

Hệ thống sẽ thực hiện:

* Nhận diện các dịch vụ AWS xuất hiện trong kiến trúc.
* Xác định mối quan hệ và luồng kết nối giữa các dịch vụ.
* Chuyển dữ liệu kiến trúc sang định dạng có cấu trúc.
* Đánh giá thiết kế theo AWS Well-Architected Framework.
* Phát hiện các điểm mạnh và điểm yếu.
* Phát hiện các lỗi thiết kế hoặc rủi ro tiềm ẩn.
* Đề xuất phương án cải tiến.
* Ước tính chi phí của các dịch vụ.
* Tạo báo cáo đánh giá dưới dạng PDF.
* Lưu lịch sử Review.
* Gửi email thông báo khi quá trình đánh giá hoàn thành.

---

### 2. Xác định vấn đề cần giải quyết

Việc đánh giá một kiến trúc AWS thường yêu cầu người thực hiện có kiến thức về nhiều nhóm dịch vụ như:

* Compute.
* Storage.
* Networking.
* Database.
* Security.
* Monitoring.
* High Availability.
* Cost Optimization.
* Disaster Recovery.

Đối với sinh viên hoặc người mới học Cloud Computing, quá trình này có thể gặp nhiều khó khăn:

* Không nhận diện đầy đủ các dịch vụ trong sơ đồ.
* Không hiểu rõ mối quan hệ giữa các thành phần.
* Không phát hiện được Single Point of Failure.
* Không xác định được lỗi Security Group hoặc IAM.
* Không biết kiến trúc có khả năng mở rộng hay không.
* Không biết cách áp dụng AWS Well-Architected Framework.
* Khó ước tính chi phí dịch vụ.
* Mất nhiều thời gian để đánh giá thủ công.

Dự án được xây dựng nhằm tự động hóa một phần quá trình này và cung cấp kết quả đánh giá dễ hiểu hơn.

---

### 3. Xác định đối tượng người dùng

Các nhóm người dùng chính:

#### Sinh viên học Cloud Computing

* Tải lên bài thiết kế kiến trúc.
* Nhận phản hồi về lỗi thiết kế.
* Hiểu rõ hơn cách sử dụng các dịch vụ AWS.
* Học cách áp dụng AWS Well-Architected Framework.
* So sánh thiết kế trước và sau khi cải tiến.

#### Cloud Engineer

* Kiểm tra nhanh một sơ đồ kiến trúc.
* Phát hiện các thành phần còn thiếu.
* Nhận đề xuất tối ưu chi phí và hiệu năng.
* Tạo báo cáo đánh giá ban đầu.
* Lưu lại lịch sử các lần Review.

#### Nhóm phát triển dự án

* Đánh giá kiến trúc trước khi triển khai.
* So sánh nhiều phương án thiết kế.
* Chia sẻ báo cáo Review cho thành viên khác.
* Theo dõi các đề xuất cần thực hiện.

---

### 4. Các chức năng chính của hệ thống

#### Quản lý dữ liệu đầu vào

Hệ thống hỗ trợ:

* Upload ảnh PNG hoặc JPG.
* Upload file Draw.io.
* Nhập mô tả kiến trúc bằng văn bản.
* Kiểm tra loại tệp.
* Kiểm tra kích thước tệp.
* Lưu dữ liệu đầu vào trên Amazon S3.
* Tạo Review ID cho mỗi yêu cầu.

#### Phân tích sơ đồ kiến trúc

Hệ thống thực hiện:

* Nhận diện tên dịch vụ AWS.
* Xác định Node trong sơ đồ.
* Xác định kết nối giữa các Node.
* Xác định hướng truyền dữ liệu.
* Chuẩn hóa dữ liệu thành JSON.
* Kiểm tra các thành phần không nhận diện được.

#### Đánh giá kiến trúc

Amazon Bedrock được sử dụng để đánh giá theo sáu trụ cột của AWS Well-Architected Framework:

* Operational Excellence.
* Security.
* Reliability.
* Performance Efficiency.
* Cost Optimization.
* Sustainability.

#### Tính toán chi phí

Hệ thống dự kiến:

* Xác định các dịch vụ có khả năng phát sinh chi phí.
* Nhận cấu hình ước tính của từng dịch vụ.
* Tính chi phí theo tháng.
* Cung cấp tổng chi phí dự kiến.
* Cảnh báo các dịch vụ có chi phí cao.
* Đề xuất phương án tối ưu chi phí.

#### Xuất kết quả

Kết quả bao gồm:

* Danh sách dịch vụ được nhận diện.
* Luồng kết nối giữa các dịch vụ.
* Điểm đánh giá theo từng trụ cột.
* Các điểm mạnh.
* Các điểm yếu.
* Các rủi ro.
* Đề xuất cải tiến.
* Chi phí ước tính.
* Báo cáo PDF.
* Trạng thái Review.

---

### 5. Functional Requirements

| Mã | Yêu cầu chức năng |
| --- | --- |
| FR-01 | Người dùng có thể truy cập Web Application |
| FR-02 | Người dùng có thể tải lên ảnh sơ đồ kiến trúc |
| FR-03 | Người dùng có thể tải lên file Draw.io |
| FR-04 | Người dùng có thể nhập mô tả kiến trúc |
| FR-05 | Hệ thống kiểm tra loại và kích thước tệp |
| FR-06 | Hệ thống lưu dữ liệu đầu vào trên Amazon S3 |
| FR-07 | Hệ thống tự động khởi chạy Review Workflow |
| FR-08 | Hệ thống nhận diện các dịch vụ AWS |
| FR-09 | Hệ thống xác định mối quan hệ giữa các dịch vụ |
| FR-10 | Hệ thống chuyển kiến trúc thành dữ liệu JSON |
| FR-11 | Hệ thống đánh giá theo AWS Well-Architected Framework |
| FR-12 | Hệ thống phát hiện lỗi và rủi ro thiết kế |
| FR-13 | Hệ thống đề xuất phương án cải tiến |
| FR-14 | Hệ thống ước tính chi phí kiến trúc |
| FR-15 | Hệ thống tạo báo cáo PDF |
| FR-16 | Hệ thống lưu lịch sử Review |
| FR-17 | Hệ thống gửi thông báo hoàn thành qua email |
| FR-18 | Người dùng có thể xem lại kết quả đã đánh giá |
| FR-19 | Người dùng có thể tải báo cáo PDF |
| FR-20 | Hệ thống ghi Log cho từng bước xử lý |

---

### 6. Non-Functional Requirements

#### Khả năng mở rộng

* Sử dụng Serverless Architecture.
* Lambda tự động mở rộng theo số lượng Request.
* S3 hỗ trợ lưu trữ số lượng lớn Object.
* DynamoDB hỗ trợ mở rộng theo lưu lượng truy cập.
* Step Functions quản lý nhiều Workflow độc lập.

#### Tính sẵn sàng

* Sử dụng các dịch vụ AWS được quản lý.
* Hạn chế phụ thuộc vào một EC2 Instance duy nhất.
* Thiết kế Retry và Error Handling cho Workflow.
* Lưu trạng thái xử lý để có thể kiểm tra khi xảy ra lỗi.

#### Bảo mật

* Áp dụng IAM Least Privilege.
* Mã hóa dữ liệu trên S3.
* Kiểm soát quyền truy cập API.
* Không công khai Input Bucket và Report Bucket.
* Kiểm tra định dạng tệp trước khi xử lý.
* Không ghi thông tin nhạy cảm vào Log.

#### Hiệu năng

* CloudFront phân phối giao diện Web.
* Lambda xử lý bất đồng bộ.
* EventBridge và Step Functions giảm phụ thuộc giữa các thành phần.
* DynamoDB cung cấp khả năng truy xuất lịch sử nhanh.

#### Chi phí

* Sử dụng mô hình Pay-as-you-go.
* Không duy trì máy chủ chạy liên tục.
* Sử dụng S3 Lifecycle cho dữ liệu cũ.
* Giới hạn thời gian chạy Lambda.
* Theo dõi chi phí Bedrock và CloudWatch Logs.

---

### 7. Kiến trúc tổng thể của hệ thống

Kiến trúc được chia thành các lớp:

```text
Presentation Layer
        ↓
API and Upload Layer
        ↓
Storage and Event Layer
        ↓
Processing and Orchestration Layer
        ↓
AI Analysis and Cost Calculation Layer
        ↓
Report and Notification Layer
        ↓
Monitoring and Security Layer
```

Các dịch vụ được lựa chọn:

| Thành phần | Dịch vụ AWS |
| --- | --- |
| Phân phối giao diện | Amazon CloudFront |
| Lưu React Frontend | Amazon S3 |
| Cung cấp REST API | Amazon API Gateway |
| Xử lý Upload | AWS Lambda |
| Lưu sơ đồ đầu vào | Amazon S3 |
| Phát sự kiện | Amazon EventBridge |
| Điều phối Workflow | AWS Step Functions |
| Trích xuất sơ đồ | AWS Lambda |
| Phân tích bằng AI | Amazon Bedrock |
| Tính chi phí | AWS Lambda |
| Tạo báo cáo PDF | AWS Lambda |
| Lưu báo cáo | Amazon S3 |
| Lưu lịch sử Review | Amazon DynamoDB |
| Gửi email | Amazon SNS |
| Ghi Log và Monitoring | Amazon CloudWatch |
| Kiểm soát truy cập | AWS IAM |

---

### 8. Luồng hoạt động tổng thể

```text
Người dùng
    ↓
Amazon CloudFront
    ↓
React Frontend trên Amazon S3
    ↓
Amazon API Gateway
    ↓
Lambda Upload Service
    ↓
Amazon S3 Input Bucket
    ↓
Amazon EventBridge
    ↓
AWS Step Functions
    ↓
Diagram Extractor Lambda
    ↓
Amazon Bedrock
    ↓
Cost Tool Lambda
    ↓
PDF Generator Lambda
    ↓
Amazon S3 Report Bucket
    ↓
Amazon DynamoDB
    ↓
Amazon SNS
    ↓
Email thông báo cho người dùng
```

---

### 9. Chi tiết luồng xử lý theo sơ đồ

#### Bước 1 – Truy cập Web Application

Người dùng truy cập ứng dụng thông qua Amazon CloudFront.

CloudFront giúp:

* Phân phối nội dung qua Edge Location.
* Giảm độ trễ.
* Hỗ trợ HTTPS.
* Cache các tệp React, JavaScript và CSS.

#### Bước 2 – Phân phối React Frontend

CloudFront lấy nội dung giao diện từ S3 Static Website hoặc S3 Origin.

Frontend cung cấp:

* Form Upload ảnh.
* Form Upload Draw.io.
* Trường nhập mô tả kiến trúc.
* Trang theo dõi trạng thái Review.
* Trang hiển thị kết quả.

#### Bước 3 – Gửi sơ đồ kiến trúc

Frontend gửi yêu cầu đến API Gateway.

Yêu cầu có thể chứa:

* Metadata của tệp.
* Loại dữ liệu đầu vào.
* Email người dùng.
* Mô tả bổ sung.
* Cấu hình dùng để ước tính chi phí.

#### Bước 4 – Kiểm tra yêu cầu Upload

API Gateway chuyển Request đến Lambda Upload Service.

Lambda kiểm tra:

* Định dạng tệp.
* Dung lượng.
* Metadata.
* Các trường bắt buộc.
* Quyền truy cập.

#### Bước 5 – Lưu sơ đồ đã Upload

Dữ liệu được lưu vào Amazon S3 Input Bucket.

Cấu trúc Object Key dự kiến:

```text
input/
└── <review-id>/
    ├── original-diagram.png
    ├── architecture.drawio
    └── metadata.json
```

#### Bước 6 – Phát sự kiện Object Created

Khi Object được tạo, S3 phát sự kiện để EventBridge nhận và xử lý.

Event có thể bao gồm:

* Bucket Name.
* Object Key.
* Object Size.
* Event Time.
* Review ID.

#### Bước 7 – Khởi chạy Review Workflow

EventBridge khởi chạy AWS Step Functions.

Step Functions chịu trách nhiệm:

* Điều phối các Lambda.
* Quản lý trạng thái.
* Retry khi có lỗi tạm thời.
* Catch lỗi không thể xử lý.
* Theo dõi từng bước.
* Chuyển dữ liệu giữa các State.

#### Bước 8 – Trích xuất dịch vụ và kết nối

Diagram Extractor Lambda xử lý dữ liệu theo loại đầu vào.

Đối với ảnh:

* Chuẩn hóa ảnh.
* Gửi ảnh đến mô hình hỗ trợ phân tích hình ảnh.
* Nhận diện dịch vụ và các kết nối.

Đối với Draw.io:

* Đọc dữ liệu XML.
* Xác định các Node.
* Xác định các Edge.
* Trích xuất Label và Metadata.

Đối với mô tả văn bản:

* Chuẩn hóa nội dung.
* Xác định tên dịch vụ.
* Xác định luồng xử lý.

#### Bước 9 – Chuyển kiến trúc thành JSON

Dữ liệu kiến trúc được chuẩn hóa:

```json
{
  "services": [
    {
      "id": "service-01",
      "name": "Amazon S3",
      "type": "Storage"
    },
    {
      "id": "service-02",
      "name": "AWS Lambda",
      "type": "Compute"
    }
  ],
  "connections": [
    {
      "source": "service-01",
      "target": "service-02",
      "relationship": "ObjectCreatedEvent"
    }
  ]
}
```

#### Bước 10 – Tính chi phí

Cost Tool Lambda nhận danh sách dịch vụ và cấu hình.

Kết quả ước tính có thể bao gồm:

```text
Amazon S3        : 3 USD/tháng
AWS Lambda       : 2 USD/tháng
API Gateway      : 4 USD/tháng
Amazon Bedrock   : 15 USD/tháng
CloudWatch       : 2 USD/tháng
--------------------------------
Tổng dự kiến     : 26 USD/tháng
```

Chi phí chỉ mang tính ước tính và phụ thuộc:

* Region.
* Số lượng Request.
* Dung lượng lưu trữ.
* Data Transfer.
* Thời gian chạy Lambda.
* Model Amazon Bedrock.
* Lượng Token hoặc dữ liệu được xử lý.

#### Bước 11 – Phân tích kiến trúc

Amazon Bedrock nhận dữ liệu JSON và đánh giá kiến trúc.

Prompt dự kiến yêu cầu AI:

* Kiểm tra các dịch vụ được sử dụng.
* Phân tích luồng kết nối.
* Phát hiện Single Point of Failure.
* Kiểm tra khả năng mở rộng.
* Phân tích Security.
* Phân tích Reliability.
* Phân tích Performance.
* Phân tích Cost.
* Phân tích Sustainability.
* Đề xuất phương án cải tiến.

#### Bước 12 – Xuất kết quả

Kết quả đánh giá được chuẩn hóa thành dữ liệu có cấu trúc:

```json
{
  "overallScore": 78,
  "strengths": [],
  "risks": [],
  "recommendations": [],
  "pillarScores": {
    "security": 75,
    "reliability": 70,
    "performance": 80,
    "costOptimization": 76
  }
}
```

#### Bước 13 – Lưu lịch sử Review

DynamoDB lưu:

* Review ID.
* User ID hoặc Email.
* Input Type.
* Input S3 Key.
* Review Status.
* Result Summary.
* Overall Score.
* Created Time.
* Completed Time.
* Report S3 Key.
* Error Message nếu có.

#### Bước 14 – Lưu báo cáo PDF

PDF Generator Lambda tạo báo cáo và lưu vào S3 Report Bucket.

Cấu trúc dự kiến:

```text
reports/
└── <review-id>/
    └── architecture-review-report.pdf
```

Report Bucket sử dụng SSE-S3 Encryption để bảo vệ dữ liệu khi lưu trữ.

#### Bước 15 – Gửi thông báo

Amazon SNS gửi email thông báo khi Review hoàn thành.

Nội dung thông báo gồm:

* Review ID.
* Trạng thái.
* Điểm tổng quan.
* Thời gian hoàn thành.
* Liên kết trở lại Web Application.

---

### 10. Thiết kế Processing Layer

Processing Layer gồm:

```text
Amazon EventBridge
        ↓
AWS Step Functions
        ↓
Diagram Extractor Lambda
        ↓
Amazon Bedrock
        ↓
Cost Tool Lambda
        ↓
PDF Generator Lambda
```

Vai trò của Step Functions:

* Quản lý Workflow.
* Tránh xây dựng toàn bộ logic trong một Lambda duy nhất.
* Hỗ trợ Retry.
* Hỗ trợ Catch.
* Lưu trạng thái từng bước.
* Cung cấp Execution History.
* Giúp xác định bước bị lỗi.

Ví dụ trạng thái:

```text
RECEIVED
    ↓
EXTRACTING
    ↓
ANALYZING
    ↓
CALCULATING_COST
    ↓
GENERATING_REPORT
    ↓
COMPLETED
```

Trạng thái lỗi:

```text
FAILED_EXTRACTION
FAILED_ANALYSIS
FAILED_COST_CALCULATION
FAILED_REPORT_GENERATION
```

---

### 11. Thiết kế Amazon DynamoDB

DynamoDB được lựa chọn để lưu lịch sử Review vì:

* Không cần quản lý máy chủ Database.
* Có khả năng mở rộng.
* Phù hợp với dữ liệu dạng JSON.
* Hỗ trợ truy xuất theo Review ID.
* Phù hợp với kiến trúc Serverless.
* Có thể tích hợp với Lambda.

Thiết kế ban đầu:

```text
Partition Key: reviewId
```

Các thuộc tính:

```text
reviewId
userId
email
inputType
inputObjectKey
status
overallScore
resultSummary
reportObjectKey
createdAt
updatedAt
completedAt
errorMessage
```

Có thể bổ sung Global Secondary Index:

```text
GSI:
Partition Key: userId
Sort Key: createdAt
```

GSI giúp truy xuất lịch sử Review của từng người dùng theo thời gian.

---

### 12. Thiết kế bảo mật

#### IAM Least Privilege

Mỗi Lambda sử dụng một IAM Role riêng.

Ví dụ:

* Upload Lambda chỉ có quyền ghi vào Input Bucket.
* Diagram Extractor chỉ có quyền đọc Input Bucket.
* Cost Tool chỉ được truy cập dữ liệu cần thiết.
* PDF Generator chỉ có quyền ghi Report Bucket.
* Notification Function chỉ được Publish SNS.
* Step Functions chỉ được Invoke các Lambda cần thiết.

#### Bảo vệ S3

* Bật Block Public Access.
* Mã hóa Object.
* Không cho người dùng truy cập trực tiếp Bucket.
* Sử dụng Pre-Signed URL khi cần Upload hoặc Download.
* Tách Input Bucket và Report Bucket.
* Xây dựng Lifecycle Rule cho dữ liệu cũ.

#### Bảo vệ API

Các phương án được xem xét:

* API Key.
* Amazon Cognito.
* IAM Authorization.
* Rate Limiting.
* Request Validation.
* AWS WAF trong giai đoạn mở rộng.

#### Bảo vệ dữ liệu

* Không lưu thông tin nhạy cảm trong Log.
* Hạn chế thời gian tồn tại của Pre-Signed URL.
* Kiểm tra định dạng tệp.
* Giới hạn kích thước Upload.
* Từ chối loại tệp không được hỗ trợ.

---

### 13. Monitoring và Logging

Amazon CloudWatch được sử dụng để theo dõi:

* Số lượng API Request.
* API Error Rate.
* Lambda Duration.
* Lambda Error.
* Lambda Throttle.
* Step Functions Execution Status.
* S3 Event Processing.
* Bedrock Request.
* DynamoDB Error.
* SNS Delivery Status.
* Tổng thời gian hoàn thành Review.

Log Group dự kiến:

```text
/aws/lambda/upload-service
/aws/lambda/diagram-extractor
/aws/lambda/cost-tool
/aws/lambda/pdf-generator
/aws/stepfunctions/review-workflow
```

Các Alarm dự kiến:

* Lambda Error lớn hơn ngưỡng.
* API Gateway trả nhiều lỗi `5xx`.
* Step Functions Execution Failed.
* DynamoDB Throttled Request.
* Review xử lý quá thời gian.
* Chi phí Bedrock tăng bất thường.

---

### 14. Thiết kế tối ưu chi phí

Các phương án được xác định:

* Sử dụng Serverless thay vì duy trì EC2 liên tục.
* Lambda chỉ phát sinh chi phí khi được gọi.
* DynamoDB sử dụng On-Demand Capacity trong giai đoạn đầu.
* S3 Lifecycle chuyển dữ liệu cũ sang Storage Class rẻ hơn.
* Xóa ảnh đầu vào sau thời gian lưu trữ quy định.
* Giới hạn kích thước tệp Upload.
* Giới hạn thời gian chạy Lambda.
* Chọn mô hình Bedrock phù hợp với yêu cầu.
* Không gửi toàn bộ ảnh nhiều lần giữa các bước.
* Cấu hình CloudWatch Log Retention.
* Sử dụng CloudFront Cache cho Frontend.

---

### 15. Kết quả kỳ vọng của dự án

Dự án hướng đến các kết quả:

* Giảm thời gian đánh giá kiến trúc AWS.
* Hỗ trợ sinh viên học Cloud Computing.
* Hỗ trợ Cloud Engineer kiểm tra thiết kế ban đầu.
* Tự động áp dụng AWS Well-Architected Framework.
* Phát hiện lỗi thiết kế phổ biến.
* Đề xuất tối ưu chi phí và hiệu năng.
* Cung cấp báo cáo có cấu trúc.
* Lưu lại lịch sử đánh giá.
* Hỗ trợ so sánh nhiều phiên bản kiến trúc.
* Tạo nền tảng có thể mở rộng trong tương lai.

---

### 16. Phạm vi MVP

Phiên bản MVP dự kiến bao gồm:

* Upload ảnh kiến trúc.
* Nhập mô tả kiến trúc.
* Lưu Input trên Amazon S3.
* Khởi chạy Workflow tự động.
* Trích xuất danh sách dịch vụ.
* Gọi Amazon Bedrock để đánh giá.
* Hiển thị điểm và đề xuất.
* Tạo báo cáo PDF.
* Lưu lịch sử trên DynamoDB.
* Gửi email thông báo.

Các chức năng có thể phát triển sau:

* Phân tích trực tiếp file Draw.io phức tạp.
* Kéo thả sơ đồ trên Web.
* So sánh hai phiên bản kiến trúc.
* Tích hợp AWS Pricing API nâng cao.
* Tự động tạo sơ đồ kiến trúc đã tối ưu.
* Tạo CloudFormation hoặc Terraform Template.
* Hỗ trợ nhiều Cloud Provider.
* Tích hợp đăng nhập bằng Amazon Cognito.
* Dashboard thống kê lịch sử Review.

---

### 17. Các rủi ro kỹ thuật đã xác định

#### AI nhận diện sai dịch vụ

Nguyên nhân:

* Ảnh có độ phân giải thấp.
* Icon không rõ.
* Sơ đồ có nhiều thành phần.
* Tên dịch vụ bị viết tắt.
* Đường kết nối chồng chéo.

Phương án:

* Yêu cầu ảnh có chất lượng tối thiểu.
* Cho phép người dùng sửa danh sách dịch vụ.
* Kết hợp OCR, XML Parser và AI.
* Yêu cầu Bedrock trả kết quả JSON có Schema.

#### Kết quả đánh giá không nhất quán

Phương án:

* Chuẩn hóa Prompt.
* Giảm Temperature.
* Sử dụng Output Schema.
* Lưu Prompt Version.
* Xây dựng bộ tiêu chí đánh giá cố định.
* Kiểm thử với nhiều kiến trúc mẫu.

#### Tính chi phí chưa chính xác

Nguyên nhân:

* Thiếu thông tin cấu hình.
* Giá thay đổi theo Region.
* Không biết lưu lượng thực tế.
* Một số dịch vụ có cách tính giá phức tạp.

Phương án:

* Hiển thị đây là chi phí ước tính.
* Yêu cầu người dùng nhập cấu hình bổ sung.
* Ghi rõ các giả định.
* Cho phép lựa chọn Region.
* Tách từng thành phần chi phí.

#### Workflow chạy quá thời gian

Phương án:

* Chia nhỏ Lambda.
* Sử dụng Step Functions.
* Xử lý bất đồng bộ.
* Thiết lập Timeout hợp lý.
* Lưu trạng thái trung gian.
* Retry những lỗi tạm thời.

---

## Kỹ năng đạt được

* Phân tích vấn đề và xác định đề tài dự án.
* Xác định đối tượng người dùng.
* Xây dựng Use Case.
* Xác định Functional Requirements.
* Xác định Non-Functional Requirements.
* Thiết kế kiến trúc Serverless.
* Xây dựng luồng xử lý Event-Driven.
* Lựa chọn dịch vụ AWS theo chức năng.
* Thiết kế Workflow bằng Step Functions.
* Thiết kế dữ liệu trên DynamoDB.
* Xây dựng nguyên tắc IAM Least Privilege.
* Thiết kế Monitoring với CloudWatch.
* Xác định các rủi ro kỹ thuật.
* Xây dựng phạm vi MVP.
* Trình bày ý tưởng kỹ thuật cho nhóm và cộng đồng.

---

## Tự đánh giá

* Nhóm đã thống nhất được một đề tài có tính thực tế và phù hợp với chương trình.
* Đề tài kết hợp được Cloud Computing, Serverless Architecture và Generative AI.
* Đã xác định được vấn đề, người dùng và các chức năng chính.
* Đã lựa chọn được các dịch vụ AWS phù hợp.
* Đã xây dựng được sơ đồ kiến trúc và luồng xử lý tổng thể.
* Hiểu rõ vai trò của EventBridge và Step Functions trong Workflow.
* Xác định được cách sử dụng Amazon Bedrock để đánh giá kiến trúc.
* Đã xây dựng định hướng lưu trữ báo cáo và lịch sử Review.
* Đã cân nhắc các yêu cầu bảo mật, giám sát và chi phí ngay từ giai đoạn thiết kế.
* Cải thiện khả năng trao đổi, phân tích và thiết kế hệ thống theo nhóm.

Nội dung cần tiếp tục cải thiện:

* Hoàn thiện Database Schema.
* Xác định chính xác mô hình Amazon Bedrock sử dụng.
* Xây dựng Prompt đánh giá chi tiết.
* Thiết kế API Contract.
* Chuẩn hóa định dạng JSON đầu vào và đầu ra.
* Xác định cách phân tích file Draw.io.
* Nghiên cứu phương pháp tính chi phí.
* Thiết kế giao diện người dùng.
* Xây dựng kế hoạch kiểm thử.
* Ước tính chi phí vận hành của chính dự án.

---

## Kế hoạch tiếp theo

* Tạo Repository chung cho nhóm.
* Xây dựng cấu trúc thư mục Frontend và Backend.
* Thiết kế giao diện Web bằng React.
* Triển khai S3 Bucket cho Frontend.
* Cấu hình Amazon CloudFront.
* Xây dựng API Gateway.
* Phát triển Lambda Upload Service.
* Thiết kế cơ chế Pre-Signed URL.
* Tạo Input Bucket và Report Bucket.
* Tạo DynamoDB Review Table.
* Xây dựng Step Functions State Machine.
* Phát triển Diagram Extractor.
* Thử nghiệm Amazon Bedrock.
* Xây dựng Prompt đánh giá kiến trúc.
* Phân chia nhiệm vụ cụ thể cho từng thành viên.
* Chuẩn bị triển khai phiên bản MVP đầu tiên.

---

