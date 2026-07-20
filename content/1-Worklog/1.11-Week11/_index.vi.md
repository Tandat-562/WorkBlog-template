---

title: "Worklog tuần 11"
date: 2026-07-05
weight: 1
chapter: false
pre: " <b> 1.11. </b> "

---

## Mục tiêu Tuần 11

* Tiếp tục triển khai project AI AWS Architecture Reviewer sau khi đã hoàn thành nền tảng frontend.
* Deploy ứng dụng React frontend lên AWS.
* Cấu hình Amazon S3 để lưu trữ ứng dụng React.
* Cấu hình Amazon CloudFront để phân phối frontend.
* Triển khai tích hợp API giữa frontend và backend.
* Cấu hình Amazon API Gateway.
* Triển khai AWS Lambda Upload Service.
* Lưu các sơ đồ kiến trúc được upload vào Amazon S3 Input Bucket.
* Lưu metadata của các lượt review vào Amazon DynamoDB.
* Triển khai các API liên quan đến review.
* Cấu hình CORS giữa frontend và backend.
* Kiểm thử luồng upload từ frontend đến các dịch vụ backend trên AWS.
* Nghiên cứu AI Processing Workflow sử dụng EventBridge, Step Functions, Lambda Diagram Extractor và Amazon Bedrock.
* Nghiên cứu AWS Well-Architected Framework để phục vụ đánh giá kiến trúc bằng AI.
* Chuẩn bị kế hoạch triển khai cho Tuần 12.

---

## Các công việc cần thực hiện trong tuần này

| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --- | --- | --- | --- |
| 1 | Xem lại tiến độ Tuần 10 và lập kế hoạch tích hợp backend AWS | 06/29/2026 | 06/29/2026 | |
| 2 | Deploy ứng dụng React lên Amazon S3 và Amazon CloudFront | 06/30/2026 | 06/30/2026 | https://docs.aws.amazon.com/AmazonS3/latest/userguide/WebsiteHosting.html |
| 3 | Cấu hình Amazon API Gateway và CORS | 07/01/2026 | 07/01/2026 | https://docs.aws.amazon.com/apigateway/latest/developerguide/http-api-cors.html |
| 4 | Triển khai Lambda Upload Service và kết nối với S3 Input Bucket | 07/02/2026 | 07/02/2026 | https://docs.aws.amazon.com/lambda/latest/dg/welcome.html |
| 5 | Tạo bảng DynamoDB và lưu metadata review | 07/03/2026 | 07/03/2026 | https://docs.aws.amazon.com/dynamodb/ |
| 6 | Triển khai các Review API và kiểm thử luồng upload end-to-end | 07/04/2026 | 07/04/2026 | |
| 7 | Nghiên cứu EventBridge, Step Functions, Lambda Diagram Extractor và Amazon Bedrock | 07/05/2026 | 07/05/2026 | https://docs.aws.amazon.com/bedrock/ |

---

## Kết quả đạt được trong Tuần 11

### 1. Deploy Frontend lên AWS

* Đã xem lại phần frontend đã hoàn thành trong Tuần 10.
* Đã build ứng dụng React để chuẩn bị deploy lên môi trường production.
* Đã deploy production build lên Amazon S3.
* Đã cấu hình Amazon CloudFront để phân phối ứng dụng frontend.
* Đã hiểu được quy trình deploy frontend khi có cập nhật mới:
  * Build ứng dụng React.
  * Upload các file build lên Amazon S3.
  * Tạo CloudFront invalidation.
* Đã xác nhận ứng dụng frontend có thể truy cập thông qua CloudFront.

S3 Bucket dùng để lưu frontend:

```text
ai-aws-reviewer-frontend-tiersteam
```

CloudFront Domain:

```text
https://d9353ayez9zar.cloudfront.net
```

CloudFront Distribution ID:

```text
E2JHD76RIC6AML
```

Các lệnh deploy đã sử dụng:

```bash
npm run build

aws s3 sync dist s3://ai-aws-reviewer-frontend-tiersteam --delete

aws cloudfront create-invalidation --distribution-id E2JHD76RIC6AML --paths "/*"
```

---

### 2. Cấu hình Amazon API Gateway

* Đã cấu hình Amazon API Gateway để frontend có thể giao tiếp với backend.
* Đã tạo các REST API route cho chức năng upload và review.
* Đã cấu hình CORS để frontend có thể gọi API.
* Đã kết nối ứng dụng frontend với API Gateway.

API Gateway Endpoint:

```text
https://031hqksomd.execute-api.ap-southeast-1.amazonaws.com
```

Các API Route đã triển khai:

```text
POST /upload
GET /reviews
GET /reviews/{reviewId}
GET /reviews/{reviewId}/status
```

Cấu hình CORS:

Allowed Origins:

```text
http://localhost:5173
https://d9353ayez9zar.cloudfront.net
```

Allowed Methods:

```text
GET
POST
OPTIONS
```

Allowed Headers:

```text
content-type
authorization
```

---

### 3. AWS Lambda Upload Service

* Đã triển khai AWS Lambda Upload Service.
* Đã kết nối API Gateway với Lambda.
* Đã triển khai chức năng kiểm tra file upload.
* Đã tạo review ID duy nhất cho mỗi lượt upload.
* Đã upload các sơ đồ kiến trúc vào Amazon S3 Input Bucket.
* Đã lưu metadata review vào DynamoDB.
* Đã trả response upload về cho frontend.

Lambda Function:

```text
ai-aws-reviewer-upload-service
```

Environment Variables:

```text
INPUT_BUCKET = ai-aws-reviewer-input-bucket-tiersteam
TABLE_NAME = AIArchitectureReviews
MAX_FILE_SIZE_MB = 5
ALLOWED_ORIGINS = http://localhost:5173,https://d9353ayez9zar.cloudfront.net
```

Định dạng Review ID:

```text
REV-XXXXXXXX
```

Ví dụ:

```text
REV-C6A0D048
```

---

### 4. Amazon S3 Input Bucket

* Đã cấu hình Amazon S3 Input Bucket để lưu các sơ đồ kiến trúc được upload.
* Đã lưu file upload theo cấu trúc thư mục rõ ràng.
* Đã xác nhận upload thành công từ frontend thông qua Lambda.

Input Bucket:

```text
ai-aws-reviewer-input-bucket-tiersteam
```

Key Pattern:

```text
uploads/{reviewId}/{fileName}
```

Ví dụ:

```text
uploads/REV-C6A0D048/architecture-2.jpg
```

---

### 5. DynamoDB Review Metadata

* Đã tạo bảng DynamoDB để lưu metadata của các lượt review.
* Đã lưu metadata sau mỗi lần upload thành công.
* Đã chuẩn bị metadata để phục vụ cho bước xử lý AI ở giai đoạn tiếp theo.

Tên bảng:

```text
AIArchitectureReviews
```

Partition Key:

```text
reviewId
```

Các trường dữ liệu đã lưu:

```text
reviewId
fileName
fileType
fileSize
s3InputBucket
s3InputKey
status
architectureType
uploadDate
updatedAt
```

Trạng thái ban đầu:

```text
uploaded
```

---

### 6. Phát triển Review API

* Đã triển khai các API để lấy thông tin review.
* Đã hỗ trợ các trang frontend như Review History, Review Progress và Report Detail.
* Đã xác nhận có thể truy xuất các bản ghi review thành công.

Các API đã triển khai:

```text
GET /reviews
GET /reviews/{reviewId}
GET /reviews/{reviewId}/status
```

Vòng đời trạng thái review đã chuẩn bị:

```text
uploaded
→ processing
→ analyzed
```

Vòng đời khi xảy ra lỗi:

```text
uploaded
→ processing
→ failed
```

Vòng đời đầy đủ trong tương lai:

```text
uploaded
→ processing
→ analyzed
→ report_generated
→ completed
```

---

### 7. Tích hợp Frontend và Backend

* Đã kết nối React frontend với API Gateway.
* Đã upload sơ đồ kiến trúc thành công từ frontend.
* Đã kiểm thử toàn bộ luồng upload.
* Đã sửa các lỗi liên quan đến CORS.
* Đã xác nhận file upload được lưu vào Amazon S3.
* Đã xác nhận metadata được lưu vào DynamoDB.

Luồng đã hoàn thành:

```text
React Frontend
→ CloudFront
→ API Gateway
→ Lambda Upload Service
→ S3 Input Bucket
→ DynamoDB
```

---

### 8. Nghiên cứu AI Processing Workflow

* Đã nghiên cứu giai đoạn triển khai tiếp theo của project.
* Đã tìm hiểu cách xử lý tự động các diagram sau khi được upload.
* Đã thiết kế workflow xử lý AI trong tương lai.

Workflow dự kiến:

```text
S3 Input Bucket
→ EventBridge
→ Step Functions
→ Lambda Diagram Extractor
→ Amazon Bedrock
→ DynamoDB Review Result
```

Đã nghiên cứu trách nhiệm của từng dịch vụ AWS:

**Amazon EventBridge**

* Phát hiện sự kiện Object Created từ Amazon S3.
* Tự động kích hoạt review workflow.

**AWS Step Functions**

* Điều phối review workflow.
* Quản lý thứ tự thực thi các bước.
* Hỗ trợ retry và xử lý lỗi.

**AWS Lambda Diagram Extractor**

* Đọc sơ đồ kiến trúc từ Amazon S3.
* Trích xuất thông tin kiến trúc.
* Chuẩn bị prompt cho quá trình phân tích AI.
* Gọi Amazon Bedrock.
* Lưu kết quả AI review vào DynamoDB.

**Amazon Bedrock**

* Phân tích sơ đồ kiến trúc AWS.
* Đánh giá kiến trúc dựa trên AWS Well-Architected Framework.
* Tạo kết quả đánh giá AI có cấu trúc.

---

### 9. Nghiên cứu AWS Well-Architected Framework

* Đã nghiên cứu AWS Well-Architected Framework.
* Đã chuẩn bị các tiêu chí đánh giá sẽ được sử dụng bởi Amazon Bedrock.

AI review sẽ đánh giá theo các tiêu chí:

```text
Security
Reliability
Performance Efficiency
Cost Optimization
Operational Excellence
Sustainability
```

Kết quả AI review dự kiến gồm:

```text
Architecture Summary
Detected AWS Services
Detected Connections
Security Assessment
Reliability Assessment
Performance Efficiency Assessment
Cost Optimization Assessment
Operational Excellence Assessment
Sustainability Assessment
Overall Score
Risk Level
Recommendations
Priority Actions
```

---

### 10. Lập kế hoạch Review Architecture

* Đã xem lại kiến trúc AWS hiện tại của project.
* Đã xác nhận phần đã triển khai hoàn thành:

```text
User
→ CloudFront
→ S3 React App
→ API Gateway
→ Lambda Upload Service
→ S3 Input Bucket
→ DynamoDB Metadata
```

* Đã xác định phần còn lại cần triển khai:

```text
S3 Input Bucket
→ EventBridge
→ Step Functions
→ Lambda Diagram Extractor
→ Amazon Bedrock
→ DynamoDB Review Result
```

* Đã lập kế hoạch cho phần triển khai trong tương lai:

```text
Lambda PDF Generator
→ S3 Report Bucket
→ SNS Email Notification
```

---

## Tự đánh giá

* Cải thiện hiểu biết về cách deploy ứng dụng React lên AWS.
* Hiểu rõ hơn về cách sử dụng Amazon S3 và CloudFront cho frontend deployment.
* Hiểu rõ hơn về cấu hình API Gateway.
* Hiểu rõ hơn về cách triển khai AWS Lambda.
* Hiểu rõ hơn về thiết kế metadata trong Amazon DynamoDB.
* Hiểu rõ hơn về tích hợp frontend và backend.
* Cải thiện khả năng xử lý lỗi CORS.
* Hiểu rõ hơn về kiến trúc serverless event-driven.
* Hiểu rõ hơn về EventBridge và Step Functions trong điều phối workflow.
* Hiểu rõ hơn về cách Amazon Bedrock có thể phân tích kiến trúc.
* Hiểu rõ hơn về AWS Well-Architected Framework.

Có thể:

* Deploy ứng dụng React lên AWS.
* Cấu hình Amazon CloudFront.
* Cấu hình API Gateway.
* Triển khai Lambda Upload Service.
* Lưu các sơ đồ được upload vào Amazon S3.
* Lưu metadata vào DynamoDB.
* Phát triển API upload và review.
* Tích hợp frontend với các dịch vụ backend.
* Thiết kế AI processing workflow.
* Giải thích vai trò của EventBridge, Step Functions, Lambda Diagram Extractor và Amazon Bedrock.

---

## Các bước tiếp theo

* Triển khai Amazon EventBridge.
* Cấu hình EventBridge rule cho sự kiện Amazon S3 Object Created.
* Tạo AWS Step Functions Review Workflow.
* Triển khai Lambda Diagram Extractor.
* Cấu hình IAM permissions cho Lambda Diagram Extractor.
* Bật quyền truy cập model trong Amazon Bedrock.
* Kết nối Lambda Diagram Extractor với Amazon Bedrock.
* Thiết kế Bedrock prompt để phân tích theo AWS Well-Architected Framework.
* Lưu kết quả AI review vào DynamoDB.
* Cập nhật trạng thái review tự động.
* Kiểm thử AI workflow hoàn chỉnh:

```text
Upload Diagram
→ S3 Input Bucket
→ EventBridge
→ Step Functions
→ Lambda Diagram Extractor
→ Amazon Bedrock
→ DynamoDB
```

* Cập nhật trang Review Progress với trạng thái xử lý thực tế.
* Hiển thị kết quả AI-generated review trong trang Report Detail.
* Tiếp tục triển khai:

```text
Lambda PDF Generator
→ S3 Report Bucket
→ SNS Email Notification
```

* Tiếp tục kiểm thử end-to-end và xác thực toàn bộ kiến trúc serverless.
---