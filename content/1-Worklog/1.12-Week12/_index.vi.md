---
title: "Worklog Tuần 12"
date: 2026-07-10
weight: 2
chapter: false
pre: " <b> 1.12. </b> "
---

## Mục tiêu Tuần 12

* Hoàn thiện toàn bộ project **AI AWS Architecture Reviewer**.
* Triển khai các hạng mục còn lại trong kế hoạch của Tuần 11.
* Hoàn thiện workflow xử lý và đánh giá sơ đồ kiến trúc bằng AI.
* Kiểm thử toàn bộ hệ thống từ frontend đến backend.
* Kiểm tra, sửa lỗi và tối ưu các chức năng của ứng dụng.
* Hoàn thiện tài liệu mô tả kiến trúc, hướng dẫn triển khai và hướng dẫn sử dụng.
* Tổng hợp và theo dõi tiến độ thực tập trong toàn bộ 12 tuần.
* Hoàn thành các phiếu nhận xét, đánh giá và xác nhận thực tập.
* Chuẩn bị hồ sơ để xin chữ ký, đóng dấu xác nhận của đơn vị thực tập.
* Hoàn tất quá trình thực tập và bàn giao sản phẩm.

---

## Các công việc cần thực hiện trong tuần này

| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --- | --- | --- | --- |
| 1 | Xem lại các hạng mục còn lại của Tuần 11 và lập kế hoạch hoàn thiện project | 07/06/2026 | 07/06/2026 | |
| 2 | Hoàn thiện EventBridge, Step Functions và Lambda Diagram Extractor | 07/07/2026 | 07/07/2026 | https://docs.aws.amazon.com/eventbridge/ |
| 3 | Kết nối Lambda Diagram Extractor với Amazon Bedrock và lưu kết quả vào DynamoDB | 07/08/2026 | 07/08/2026 | https://docs.aws.amazon.com/bedrock/ |
| 4 | Hoàn thiện trang Review Progress, Report Detail và kiểm thử toàn bộ hệ thống | 07/09/2026 | 07/09/2026 | |
| 5 | Hoàn thiện tài liệu project, phiếu đánh giá, bảng theo dõi tiến độ và hồ sơ kết thúc thực tập | 07/10/2026 | 07/10/2026 | |

---

## Kết quả đạt được trong Tuần 12

### 1. Hoàn thiện AI Processing Workflow

* Đã triển khai Amazon EventBridge để phát hiện sự kiện khi có sơ đồ kiến trúc mới được upload vào Amazon S3 Input Bucket.
* Đã cấu hình EventBridge Rule cho sự kiện `Object Created`.
* Đã kết nối EventBridge với AWS Step Functions.
* Đã xây dựng Step Functions State Machine để điều phối toàn bộ quá trình đánh giá kiến trúc.
* Đã cấu hình các bước xử lý, cập nhật trạng thái, retry và xử lý lỗi trong workflow.
* Đã triển khai Lambda Diagram Extractor để đọc và xử lý sơ đồ kiến trúc từ Amazon S3.
* Đã cấu hình IAM Role và các quyền cần thiết cho Lambda, Step Functions, S3, DynamoDB và Amazon Bedrock.

Workflow xử lý đã hoàn thiện:

```text
Upload Diagram
→ S3 Input Bucket
→ EventBridge
→ Step Functions
→ Lambda Diagram Extractor
→ Amazon Bedrock
→ DynamoDB Review Result
```

---

### 2. Tích hợp Amazon Bedrock

* Đã bật quyền truy cập model trong Amazon Bedrock.
* Đã kết nối Lambda Diagram Extractor với Amazon Bedrock.
* Đã xây dựng prompt để phân tích sơ đồ kiến trúc AWS.
* Đã áp dụng các tiêu chí của AWS Well-Architected Framework vào quá trình đánh giá.
* Đã xử lý kết quả trả về từ Amazon Bedrock theo định dạng có cấu trúc.
* Đã lưu kết quả đánh giá AI vào Amazon DynamoDB.
* Đã cập nhật trạng thái review tự động theo từng giai đoạn xử lý.

Các tiêu chí đánh giá gồm:

```text
Security
Reliability
Performance Efficiency
Cost Optimization
Operational Excellence
Sustainability
```

Kết quả đánh giá gồm:

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

### 3. Hoàn thiện chức năng theo dõi tiến độ Review

* Đã hoàn thiện trang Review Progress.
* Đã kết nối frontend với API lấy trạng thái review.
* Đã hiển thị trạng thái xử lý theo thời gian thực.
* Đã cập nhật giao diện tương ứng với từng trạng thái.

Vòng đời trạng thái review:

```text
uploaded
→ processing
→ analyzed
→ report_generated
→ completed
```

Trường hợp xảy ra lỗi:

```text
uploaded
→ processing
→ failed
```

* Đã bổ sung thông báo khi review hoàn thành hoặc xảy ra lỗi.
* Đã kiểm tra khả năng truy xuất trạng thái theo `reviewId`.

---

### 4. Hoàn thiện trang Report Detail

* Đã hoàn thiện trang hiển thị kết quả đánh giá kiến trúc.
* Đã hiển thị thông tin tổng quan của sơ đồ.
* Đã hiển thị các dịch vụ AWS được phát hiện.
* Đã hiển thị điểm đánh giá theo từng tiêu chí.
* Đã hiển thị mức độ rủi ro và các vấn đề cần ưu tiên xử lý.
* Đã hiển thị các đề xuất cải thiện do Amazon Bedrock tạo ra.
* Đã kết nối dữ liệu từ DynamoDB với giao diện Report Detail.
* Đã kiểm tra chức năng xem lại các báo cáo đã hoàn thành.

---

### 5. Hoàn thiện chức năng tạo và lưu báo cáo

* Đã chuẩn bị chức năng tạo báo cáo từ kết quả AI review.
* Đã triển khai Lambda PDF Generator để xử lý dữ liệu báo cáo.
* Đã cấu hình Amazon S3 Report Bucket để lưu báo cáo.
* Đã lưu đường dẫn báo cáo vào metadata của review.
* Đã chuẩn bị chức năng gửi thông báo khi báo cáo hoàn thành.
* Đã cấu hình Amazon SNS phục vụ việc gửi thông báo.

Luồng tạo báo cáo:

```text
DynamoDB Review Result
→ Lambda PDF Generator
→ S3 Report Bucket
→ SNS Email Notification
```

---

### 6. Kiểm thử toàn bộ hệ thống

* Đã kiểm thử luồng upload sơ đồ từ React frontend.
* Đã xác nhận file được lưu thành công trong Amazon S3 Input Bucket.
* Đã xác nhận metadata được lưu trong DynamoDB.
* Đã xác nhận EventBridge kích hoạt workflow tự động.
* Đã xác nhận Step Functions điều phối đúng các bước xử lý.
* Đã kiểm tra Lambda Diagram Extractor và kết nối Amazon Bedrock.
* Đã kiểm tra kết quả AI được lưu và hiển thị trên frontend.
* Đã kiểm tra trang Review History, Review Progress và Report Detail.
* Đã kiểm tra chức năng tạo báo cáo.
* Đã kiểm tra các trường hợp lỗi upload, lỗi xử lý và lỗi API.
* Đã sửa các lỗi liên quan đến CORS, IAM permissions, API response và trạng thái review.
* Đã kiểm thử end-to-end toàn bộ hệ thống.

Luồng hoàn chỉnh của project:

```text
User
→ CloudFront
→ S3 React App
→ API Gateway
→ Lambda Upload Service
→ S3 Input Bucket
→ EventBridge
→ Step Functions
→ Lambda Diagram Extractor
→ Amazon Bedrock
→ DynamoDB
→ Lambda PDF Generator
→ S3 Report Bucket
→ SNS Email Notification
```

---

### 7. Hoàn thiện và bàn giao Project

* Đã kiểm tra lại toàn bộ source code frontend và backend.
* Đã sắp xếp lại cấu trúc thư mục của project.
* Đã kiểm tra các biến môi trường và thông tin cấu hình.
* Đã bổ sung hướng dẫn cài đặt, build và deploy ứng dụng.
* Đã hoàn thiện tài liệu mô tả kiến trúc hệ thống.
* Đã cập nhật sơ đồ kiến trúc AWS cuối cùng.
* Đã ghi chú các chức năng đã hoàn thành và các hướng phát triển trong tương lai.
* Đã bàn giao source code, tài liệu và thông tin triển khai của project.
* Đã xác nhận project có thể hoạt động đúng theo các yêu cầu đã đề ra.

---

### 8. Tổng hợp và theo dõi tiến độ thực tập

* Đã xem lại toàn bộ nội dung công việc từ Tuần 1 đến Tuần 12.
* Đã tổng hợp các nhiệm vụ, kết quả và kiến thức đạt được trong từng tuần.
* Đã cập nhật bảng theo dõi tiến độ thực tập.
* Đã kiểm tra thời gian bắt đầu và hoàn thành của từng công việc.
* Đã đối chiếu nội dung worklog với kế hoạch thực tập.
* Đã bổ sung các công việc còn thiếu trong báo cáo tiến độ.
* Đã sắp xếp tài liệu theo đúng trình tự thời gian.
* Đã tổng hợp các kết quả nổi bật trong quá trình thực tập.

---

### 9. Hoàn thiện các phiếu đánh giá thực tập

* Đã điền đầy đủ thông tin vào phiếu đánh giá của đơn vị thực tập.
* Đã chuẩn bị phiếu nhận xét quá trình thực tập.
* Đã chuẩn bị phiếu theo dõi tiến độ thực tập.
* Đã kiểm tra thông tin cá nhân, thời gian và vị trí thực tập.
* Đã kiểm tra nội dung nhận xét, đánh giá và kết quả công việc.
* Đã hoàn thiện các phần cần xác nhận của người hướng dẫn.
* Đã chuẩn bị hồ sơ để xin chữ ký và đóng dấu của đơn vị thực tập.
* Đã rà soát hình thức trình bày trước khi in và nộp.

Các hồ sơ đã chuẩn bị gồm:

```text
Phiếu đánh giá của đơn vị thực tập
Phiếu nhận xét của người hướng dẫn
Phiếu theo dõi tiến độ thực tập
Nhật ký thực tập từ Tuần 1 đến Tuần 12
Báo cáo tổng kết thực tập
Thông tin bàn giao Project
```

---

### 10. Hoàn tất quá trình thực tập

* Đã hoàn thành các nhiệm vụ được giao trong thời gian thực tập.
* Đã hoàn thiện project AI AWS Architecture Reviewer.
* Đã bàn giao sản phẩm và tài liệu liên quan.
* Đã hoàn thành báo cáo và nhật ký thực tập.
* Đã chuẩn bị đầy đủ các phiếu đánh giá và xác nhận.
* Đã xin chữ ký và đóng dấu xác nhận của đơn vị thực tập.
* Đã kiểm tra lại toàn bộ hồ sơ trước khi nộp.
* Đã hoàn tất quá trình thực tập theo đúng kế hoạch.

---

## Tự đánh giá

* Hoàn thành các mục tiêu đã đề ra cho project.
* Cải thiện khả năng triển khai một ứng dụng full-stack trên AWS.
* Hiểu rõ hơn về kiến trúc serverless và event-driven.
* Hiểu rõ cách tích hợp Amazon S3, CloudFront, API Gateway, Lambda và DynamoDB.
* Hiểu rõ hơn về EventBridge và Step Functions trong việc điều phối workflow.
* Có khả năng tích hợp Amazon Bedrock vào ứng dụng thực tế.
* Cải thiện khả năng kiểm thử và xử lý lỗi end-to-end.
* Cải thiện kỹ năng quản lý tiến độ và tổng hợp báo cáo.
* Cải thiện kỹ năng viết tài liệu kỹ thuật.
* Có kinh nghiệm chuẩn bị hồ sơ, phiếu đánh giá và tài liệu kết thúc thực tập.
* Hoàn thành quá trình thực tập đúng tiến độ.

Có thể:

* Triển khai frontend React lên Amazon S3 và CloudFront.
* Phát triển backend serverless với API Gateway và AWS Lambda.
* Lưu trữ file và dữ liệu bằng Amazon S3 và DynamoDB.
* Xây dựng workflow tự động bằng EventBridge và Step Functions.
* Tích hợp Amazon Bedrock để phân tích sơ đồ kiến trúc.
* Theo dõi và cập nhật trạng thái xử lý của hệ thống.
* Kiểm thử toàn bộ luồng hoạt động của ứng dụng.
* Viết và hoàn thiện tài liệu bàn giao project.
* Tổng hợp tiến độ và kết quả thực tập.
* Chuẩn bị hồ sơ đánh giá và kết thúc thực tập.

---

## Kết luận

Trong Tuần 12, project **AI AWS Architecture Reviewer** đã được hoàn thiện và kiểm thử toàn bộ. Các chức năng chính từ upload sơ đồ, xử lý tự động, phân tích bằng Amazon Bedrock, lưu kết quả, theo dõi tiến độ đến hiển thị báo cáo đã được tích hợp thành một hệ thống hoàn chỉnh.

Bên cạnh việc hoàn thiện project, các tài liệu kỹ thuật, nhật ký thực tập, phiếu đánh giá và bảng theo dõi tiến độ cũng đã được tổng hợp đầy đủ. Hồ sơ đã được chuẩn bị để xin chữ ký, đóng dấu xác nhận của đơn vị thực tập và kết thúc quá trình thực tập theo đúng kế hoạch.