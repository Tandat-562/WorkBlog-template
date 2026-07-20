
---
title: "Worklog tuần 8"
date: 2026-06-14
weight: 1
chapter: false
pre: " <b> 1.8. </b> "

---

## Mục tiêu tuần 8

* Hoàn thành Module 05 về bảo mật, quản lý định danh và kiểm soát truy cập trên AWS.
* Hiểu mô hình AWS Shared Responsibility Model và trách nhiệm của AWS so với khách hàng.
* Nghiên cứu kiến trúc AWS Identity and Access Management.
* Phân biệt IAM User, IAM Group, IAM Role, IAM Policy và Permission Boundary.
* Tìm hiểu quy trình xác thực và phân quyền người dùng ứng dụng bằng Amazon Cognito.
* Nghiên cứu mô hình quản trị nhiều tài khoản bằng AWS Organizations.
* Tìm hiểu cơ chế đăng nhập tập trung bằng AWS IAM Identity Center.
* Hiểu cách AWS Key Management Service quản lý khóa và bảo vệ dữ liệu.
* Tìm hiểu AWS Security Hub và quy trình tập trung các phát hiện bảo mật.
* Thực hành kiểm soát truy cập bằng IAM Conditions, Resource Tags và Temporary Credentials.
* Áp dụng nguyên tắc Least Privilege vào quá trình cấp quyền.
* Nâng cao khả năng kiểm tra và xử lý lỗi liên quan đến IAM, Role, Policy, mã hóa và quản trị bảo mật.

---

## Các công việc thực hiện trong tuần

| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --- | --- | --- | --- |
| 1 | - Nghiên cứu Module 05-01 về AWS Shared Responsibility Model <br> - Phân biệt trách nhiệm bảo mật của AWS và khách hàng <br> - Tìm hiểu trách nhiệm thay đổi theo từng loại dịch vụ <br> - Ôn tập bảo mật Root User và MFA | 08/06/2026 | 08/06/2026 | https://www.youtube.com/watch?v=tsobAlSg19g&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=150 |
| 2 | - Nghiên cứu Module 05-02 về AWS Identity and Access Management <br> - Tìm hiểu IAM User, Group, Role và Policy <br> - Phân tích quy trình Authentication và Authorization <br> - Thực hành quản lý IAM User, Group và Role | 09/06/2026 | 09/06/2026 | https://www.youtube.com/watch?v=N_vlJGAqZxo&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=151, https://000002.awsstudygroup.com/vi/ |
| 3 | - Nghiên cứu Module 05-03 về Amazon Cognito <br> - Phân biệt User Pool và Identity Pool <br> - Tìm hiểu quy trình đăng ký, đăng nhập và cấp Token cho người dùng ứng dụng <br> - Ôn tập IAM Role cho ứng dụng truy cập AWS | 10/06/2026 | 10/06/2026 | https://www.youtube.com/watch?v=pZ2fgEFK3Vs&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=152, https://000048.awsstudygroup.com/vi/ |
| 4 | - Nghiên cứu Module 05-04 về AWS Organizations <br> - Tìm hiểu Management Account, Member Account và Organizational Unit <br> - Phân tích Service Control Policy <br> - Thực hành Assume Role, Trust Policy và IAM Conditions | 11/06/2026 | 11/06/2026 | https://www.youtube.com/watch?v=5oQY8Rogz9Y&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=153, https://000044.awsstudygroup.com/vi/ |
| 5 | - Nghiên cứu Module 05-05 về AWS IAM Identity Center <br> - Kích hoạt IAM Identity Center <br> - Tạo Users, Groups và Permission Sets <br> - Gán quyền truy cập AWS Account <br> - Cấu hình đăng nhập AWS CLI bằng SSO | 12/06/2026 | 12/06/2026 | https://www.youtube.com/watch?v=NW1xrMkNMjU&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=154, https://000012.awsstudygroup.com/vi/ |
| 6 | - Nghiên cứu Module 05-06 về AWS Key Management Service <br> - Tìm hiểu KMS Key, Key Policy và Data Key <br> - Phân biệt mã hóa đối xứng và bất đối xứng <br> - Thực hành IAM Policy Conditions và kiểm soát EC2 bằng Resource Tags | 13/06/2026 | 13/06/2026 | https://www.youtube.com/watch?v=GMihNQojhZc&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=155, https://000028.awsstudygroup.com/vi/ |
| 7 | - Nghiên cứu các phần cuối của Module 05 <br> - Tìm hiểu AWS Security Hub và quy trình quản lý Security Findings <br> - Tổng hợp kiến thức về Identity, Encryption, Governance và Security Monitoring <br> - Rà soát các lỗi IAM, Permission Set, KMS và Security Hub | 14/06/2026 | 14/06/2026 | https://www.youtube.com/watch?v=clj2E0rNBEs&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=156, https://www.youtube.com/watch?v=0SdpD2GPYz4&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=157 |

---

## Kết quả đạt được tuần 8

### 1. Hoàn thành Module 05

Các nội dung chính đã được nghiên cứu:

| Module | Nội dung |
| --- | --- |
| Module 05-01 | AWS Shared Responsibility Model |
| Module 05-02 | AWS Identity and Access Management |
| Module 05-03 | Amazon Cognito |
| Module 05-04 | AWS Organizations |
| Module 05-05 | AWS IAM Identity Center |
| Module 05-06 | AWS Key Management Service |
| Module 05-07 | AWS Security Hub và quản lý Security Findings |
| Module 05-08 | Tổng hợp bảo mật, quản trị và giám sát trên AWS |

Sau khi hoàn thành Module 05, đã hiểu rõ hơn cách AWS quản lý định danh, phân quyền, mã hóa, quản trị nhiều tài khoản và theo dõi trạng thái bảo mật của hệ thống.

---

### 2. AWS Shared Responsibility Model

AWS Shared Responsibility Model phân chia trách nhiệm bảo mật thành hai nhóm:

```text
AWS
├── Bảo mật của Cloud
│   ├── Trung tâm dữ liệu
│   ├── Phần cứng
│   ├── Hạ tầng mạng
│   ├── Lớp ảo hóa
│   └── Cơ sở hạ tầng dịch vụ
│
└── Khách hàng
    └── Bảo mật trong Cloud
        ├── Dữ liệu
        ├── IAM
        ├── Hệ điều hành
        ├── Ứng dụng
        ├── Network Configuration
        └── Mã hóa và quản lý khóa
```

Hiểu được:

* AWS chịu trách nhiệm bảo vệ cơ sở hạ tầng vận hành các dịch vụ AWS.
* Khách hàng chịu trách nhiệm về dữ liệu, tài khoản, quyền truy cập và cấu hình của mình.
* Mức độ trách nhiệm của khách hàng thay đổi tùy loại dịch vụ.
* Với Amazon EC2, khách hàng quản lý hệ điều hành, ứng dụng và Security Group.
* Với dịch vụ được quản lý như Amazon S3 hoặc DynamoDB, AWS đảm nhận nhiều thành phần hạ tầng hơn.
* Dịch vụ được AWS quản lý không có nghĩa khách hàng không còn trách nhiệm bảo mật.

---

### 3. Bảo vệ AWS Root User

Root User có quyền truy cập cao nhất trong AWS Account.

Các nguyên tắc bảo mật:

* Không sử dụng Root User cho công việc hằng ngày.
* Bật MFA cho Root User.
* Không tạo Access Key cho Root User nếu không cần thiết.
* Sử dụng địa chỉ email được kiểm soát an toàn.
* Bảo vệ thông tin thanh toán và thông tin khôi phục tài khoản.
* Chỉ sử dụng Root User cho các tác vụ yêu cầu đặc biệt.
* Theo dõi hoạt động đăng nhập bất thường.

Các hoạt động hằng ngày nên được thực hiện bằng IAM User, IAM Role hoặc IAM Identity Center.

---

### 4. Kiến trúc AWS IAM

AWS IAM được sử dụng để quản lý quyền truy cập vào dịch vụ và tài nguyên AWS.

Các thành phần chính:

```text
Identity
├── IAM User
├── IAM Group
└── IAM Role

Permission
├── Identity-Based Policy
├── Resource-Based Policy
├── Permission Boundary
├── Service Control Policy
└── Session Policy
```

#### IAM User

* Đại diện cho một người dùng hoặc trường hợp sử dụng cụ thể.
* Có thể đăng nhập AWS Console.
* Có thể sử dụng Access Key cho AWS CLI hoặc API.
* Mặc định không có quyền khi mới được tạo.

#### IAM Group

* Nhóm nhiều IAM User.
* Giúp quản lý quyền theo vai trò công việc.
* Policy gắn với Group được áp dụng cho các thành viên.

#### IAM Role

* Không có thông tin xác thực dài hạn.
* Được sử dụng thông qua Assume Role.
* AWS STS cấp Temporary Credentials.
* Có thể được sử dụng bởi User, AWS Service hoặc ứng dụng.

---

### 5. IAM Policy

IAM Policy là tài liệu JSON xác định quyền truy cập.

Cấu trúc cơ bản:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "ec2:DescribeInstances"
      ],
      "Resource": "*"
    }
  ]
}
```

Các thành phần:

* `Effect`: Allow hoặc Deny.
* `Action`: Hành động được phép hoặc bị từ chối.
* `Resource`: Tài nguyên áp dụng.
* `Condition`: Điều kiện bổ sung.
* `Principal`: Đối tượng được áp dụng trong Resource-Based Policy.

Nguyên tắc quan trọng:

* Mặc định mọi truy cập đều bị từ chối.
* Quyền chỉ được cấp khi có một `Allow` phù hợp.
* `Explicit Deny` luôn được ưu tiên hơn `Allow`.
* Không nên sử dụng quyền `Action: "*"` và `Resource: "*"` nếu không cần thiết.

---

### 6. Quy trình đánh giá quyền IAM

Quy trình tổng quát:

```text
User hoặc Application gửi Request
            ↓
AWS xác thực Identity
            ↓
Kiểm tra Identity-Based Policy
            ↓
Kiểm tra Resource-Based Policy
            ↓
Kiểm tra Permission Boundary
            ↓
Kiểm tra Service Control Policy
            ↓
Kiểm tra Session Policy
            ↓
Allow hoặc Deny
```

Effective Permission là kết quả của nhiều lớp Policy kết hợp với nhau.

Một Identity có Policy cho phép vẫn có thể không thực hiện được hành động nếu:

* Permission Boundary không cho phép.
* Service Control Policy không cho phép.
* Resource Policy có Explicit Deny.
* KMS Key Policy không cho phép.
* Trust Policy không cho phép Assume Role.
* Policy Condition không được thỏa mãn.

---

### 7. IAM Role và Temporary Credentials

Quy trình Assume Role:

```text
IAM User hoặc AWS Service
          ↓
Gọi AWS STS AssumeRole
          ↓
Kiểm tra Trust Policy
          ↓
Cấp Temporary Credentials
          ↓
Sử dụng quyền của IAM Role
          ↓
Credentials tự động hết hạn
```

Temporary Credentials thường bao gồm:

* Access Key ID.
* Secret Access Key.
* Session Token.
* Expiration Time.

Lợi ích:

* Không cần lưu thông tin xác thực dài hạn.
* Credentials tự động hết hạn.
* Giảm nguy cơ rò rỉ Access Key.
* Có thể giới hạn thời gian và điều kiện Session.
* Phù hợp cho EC2, Lambda và các ứng dụng chạy trên AWS.

---

### 8. IAM Trust Policy

Trust Policy xác định đối tượng được phép Assume Role.

Ví dụ:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": {
        "AWS": "arn:aws:iam::<account-id>:user/example-user"
      },
      "Action": "sts:AssumeRole"
    }
  ]
}
```

Để Assume Role thành công cần kiểm tra:

* User có quyền `sts:AssumeRole`.
* Trust Policy của Role cho phép User hoặc Account tương ứng.
* Policy Condition được đáp ứng.
* Service Control Policy không chặn hành động.
* Permission Boundary không giới hạn quyền cần thiết.

---

### 9. IAM Policy Conditions

IAM Conditions cho phép kiểm soát quyền chi tiết hơn.

Điều kiện có thể dựa trên:

* Địa chỉ IP.
* Thời gian.
* Region.
* Resource Tag.
* Request Tag.
* Principal Tag.
* MFA.
* VPC Endpoint.
* AWS Account.
* Organization ID.

Ví dụ giới hạn theo Region:

```json
"Condition": {
  "StringEquals": {
    "aws:RequestedRegion": "ap-southeast-1"
  }
}
```

Ví dụ yêu cầu MFA:

```json
"Condition": {
  "Bool": {
    "aws:MultiFactorAuthPresent": "true"
  }
}
```

---

### 10. Kiểm soát truy cập bằng Resource Tags

Đã thực hành cấp quyền quản lý EC2 dựa trên Tag.

Ví dụ:

```text
Team = Alpha
Environment = Development
Owner = FCJ-Team
```

Luồng kiểm soát:

```text
User gửi yêu cầu quản lý EC2
          ↓
IAM kiểm tra Resource Tag
          ↓
Tag phù hợp với Policy Condition?
          ↓
Có → Cho phép
Không → Từ chối
```

Các Policy đã tìm hiểu và kiểm thử:

* `ec2-list-read`
* `ec2-create-tags`
* `ec2-create-tags-existing`
* `ec2-run-instances`
* `ec2-manage-instances`

Kết quả:

* Giới hạn người dùng chỉ quản lý EC2 có Tag phù hợp.
* Bắt buộc gán Tag khi tạo Instance.
* Giới hạn thao tác theo Region.
* Ngăn người dùng quản lý tài nguyên thuộc nhóm khác.
* Áp dụng Attribute-Based Access Control.

---

### 11. IAM Permission Boundary

Permission Boundary xác định mức quyền tối đa mà IAM User hoặc IAM Role có thể nhận.

Effective Permission được hiểu như sau:

```text
IAM Identity Policy
          ∩
Permission Boundary
          =
Effective Permission
```

Ví dụ:

* Identity Policy cho phép quản lý toàn bộ EC2.
* Permission Boundary chỉ cho phép thao tác trong `ap-southeast-1`.
* User chỉ có thể quản lý EC2 tại `ap-southeast-1`.

Permission Boundary không tự cấp quyền. Nó chỉ giới hạn quyền được cấp bởi Identity-Based Policy.

Trường hợp sử dụng:

* Cho phép Developer tự tạo Role nhưng không vượt quá giới hạn.
* Ngăn Privilege Escalation.
* Giới hạn quyền quản trị theo Region hoặc Service.
* Phân quyền trong môi trường nhiều nhóm phát triển.

---

### 12. Amazon Cognito

Amazon Cognito cung cấp tính năng quản lý danh tính cho người dùng ứng dụng.

Hai thành phần chính:

#### Cognito User Pool

* Quản lý đăng ký và đăng nhập.
* Lưu thông tin người dùng.
* Hỗ trợ xác minh email hoặc số điện thoại.
* Hỗ trợ MFA.
* Phát hành JWT Token.
* Có thể tích hợp với Social Identity Provider và SAML.

#### Cognito Identity Pool

* Cấp Temporary AWS Credentials.
* Ánh xạ người dùng sang IAM Role.
* Cho phép ứng dụng truy cập tài nguyên AWS.
* Hỗ trợ người dùng đã xác thực và chưa xác thực.

Luồng hoạt động:

```text
Người dùng đăng nhập
        ↓
Cognito User Pool
        ↓
Nhận JWT Token
        ↓
Cognito Identity Pool
        ↓
Assume IAM Role
        ↓
Nhận Temporary AWS Credentials
        ↓
Truy cập dịch vụ AWS
```

---

### 13. AWS Organizations

AWS Organizations hỗ trợ quản lý nhiều AWS Account tập trung.

Cấu trúc:

```text
Organization Root
├── Management Account
├── Security OU
│   ├── Log Archive Account
│   └── Security Tooling Account
├── Production OU
│   └── Production Account
└── Development OU
    ├── Development Account
    └── Testing Account
```

Các thành phần:

* Management Account.
* Member Account.
* Organization Root.
* Organizational Unit.
* Service Control Policy.
* Consolidated Billing.

Lợi ích:

* Tách biệt workload theo Account.
* Quản lý tập trung.
* Áp dụng Policy theo OU.
* Tổng hợp Billing.
* Hạn chế phạm vi ảnh hưởng khi có sự cố.
* Hỗ trợ xây dựng Landing Zone.

---

### 14. Service Control Policy

Service Control Policy xác định mức quyền tối đa của Account hoặc OU trong AWS Organizations.

SCP:

* Không trực tiếp cấp quyền.
* Chỉ giới hạn quyền có thể được sử dụng.
* Có thể áp dụng cho Account hoặc OU.
* Không thay thế IAM Policy.
* Có thể ngăn sử dụng một số dịch vụ hoặc Region.

Ví dụ:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Deny",
      "Action": "*",
      "Resource": "*",
      "Condition": {
        "StringNotEquals": {
          "aws:RequestedRegion": [
            "ap-southeast-1"
          ]
        }
      }
    }
  ]
}
```

Policy trên có thể được sử dụng để hạn chế hoạt động ngoài Region được cho phép.

---

### 15. AWS IAM Identity Center

IAM Identity Center hỗ trợ quản lý đăng nhập tập trung cho nhiều AWS Account và ứng dụng.

Kiến trúc:

```text
Identity Source
      ↓
IAM Identity Center
      ↓
Users và Groups
      ↓
Permission Sets
      ↓
AWS Account Assignments
      ↓
AWS Access Portal hoặc AWS CLI
```

Đã thực hành:

* Kích hoạt AWS Organizations.
* Kích hoạt IAM Identity Center.
* Tạo User.
* Tạo Group.
* Tạo Permission Set.
* Gán User và Group vào AWS Account.
* Kiểm tra quyền Administrator và Read-Only.
* Cấu hình AWS CLI sử dụng SSO.

Các đối tượng đã tạo:

* Administrators Group.
* ReadOnly Group.
* Admin User.
* ReadOnly User.

---

### 16. Permission Set

Permission Set là mẫu quyền được IAM Identity Center sử dụng để cấp quyền vào AWS Account.

Permission Set có thể chứa:

* AWS Managed Policy.
* Customer Managed Policy.
* Inline Policy.
* Permission Boundary.
* Session Duration.
* Relay State.

Khi gán Permission Set vào Account, IAM Identity Center tạo IAM Role tương ứng trong Account đích.

Lợi ích:

* Quản lý quyền tập trung.
* Không cần tạo IAM User riêng trong từng Account.
* Dễ thu hồi quyền.
* Hỗ trợ nhiều Account.
* Credentials có thời hạn.
* Giảm việc sử dụng Access Key dài hạn.

---

### 17. AWS CLI với IAM Identity Center

Quy trình cấu hình:

```bash
aws configure sso
```

Sau đó người dùng cung cấp:

* SSO Start URL.
* SSO Region.
* AWS Account.
* Permission Set hoặc Role.
* CLI Profile Name.

Đăng nhập:

```bash
aws sso login --profile <profile-name>
```

Kiểm tra Identity:

```bash
aws sts get-caller-identity --profile <profile-name>
```

Lợi ích:

* Không cần lưu Access Key dài hạn.
* Sử dụng Session Credential.
* Đăng nhập qua trình duyệt.
* Quyền được quản lý tập trung.
* Có thể sử dụng nhiều Account và Role.

---

### 18. AWS Key Management Service

AWS KMS là dịch vụ quản lý khóa mã hóa.

Các thành phần:

```text
KMS Key
├── Key Material
├── Key Policy
├── Alias
├── Key ID
└── Key Metadata
```

AWS KMS được tích hợp với nhiều dịch vụ:

* Amazon S3.
* Amazon EBS.
* Amazon RDS.
* Amazon DynamoDB.
* AWS Lambda.
* AWS Secrets Manager.
* Amazon CloudWatch Logs.
* Amazon SNS.
* Amazon SQS.

---

### 19. Các loại KMS Key

#### AWS Owned Key

* Do AWS sở hữu và quản lý.
* Được sử dụng cho nhiều AWS Account.
* Khách hàng không trực tiếp quản lý.

#### AWS Managed Key

* Được tạo trong Account khi sử dụng dịch vụ AWS.
* Do AWS quản lý.
* Có Alias dạng `aws/<service>`.

#### Customer Managed Key

* Do khách hàng tạo và quản lý.
* Có thể chỉnh sửa Key Policy.
* Có thể bật hoặc tắt Key.
* Có thể thiết lập Rotation.
* Có thể sử dụng Alias.
* Hỗ trợ kiểm soát quyền chi tiết.

---

### 20. Envelope Encryption

Envelope Encryption sử dụng Data Key để mã hóa dữ liệu.

Quy trình:

```text
Ứng dụng yêu cầu GenerateDataKey
          ↓
AWS KMS tạo Plaintext Data Key
và Encrypted Data Key
          ↓
Plaintext Data Key mã hóa dữ liệu
          ↓
Xóa Plaintext Data Key khỏi bộ nhớ
          ↓
Lưu Encrypted Data Key cùng Ciphertext
```

Khi giải mã:

```text
Encrypted Data Key
        ↓
AWS KMS Decrypt
        ↓
Plaintext Data Key
        ↓
Giải mã dữ liệu
```

Lợi ích:

* Không cần gửi toàn bộ dữ liệu đến AWS KMS.
* Phù hợp với dữ liệu có kích thước lớn.
* Giảm số lượng thao tác trực tiếp với KMS Key.
* Giúp tách khóa mã hóa dữ liệu khỏi dữ liệu đã mã hóa.

---

### 21. KMS Key Policy

KMS Key Policy xác định đối tượng được phép sử dụng và quản lý KMS Key.

Quyền thường gặp:

* `kms:Encrypt`
* `kms:Decrypt`
* `kms:GenerateDataKey`
* `kms:DescribeKey`
* `kms:CreateGrant`
* `kms:EnableKey`
* `kms:DisableKey`

Để sử dụng KMS Key thành công có thể cần:

* IAM Policy cho phép.
* Key Policy cho phép.
* Service Control Policy không chặn.
* Permission Boundary không chặn.
* Region và Key ARN chính xác.

---

### 22. AWS Security Hub

AWS Security Hub cung cấp một vị trí tập trung để theo dõi trạng thái bảo mật.

Luồng hoạt động:

```text
AWS Security Services
├── Amazon GuardDuty
├── Amazon Inspector
├── Amazon Macie
├── IAM Access Analyzer
└── Các giải pháp đối tác
          ↓
     Security Findings
          ↓
    AWS Security Hub
          ↓
Phân loại và ưu tiên Findings
          ↓
Điều tra và khắc phục
```

Security Hub hỗ trợ:

* Tổng hợp Security Findings.
* Chuẩn hóa dữ liệu Findings.
* Đánh giá tài nguyên theo Security Standards.
* Phân loại Findings theo mức độ nghiêm trọng.
* Cung cấp thông tin tài nguyên bị ảnh hưởng.
* Tích hợp với EventBridge để tự động xử lý.
* Theo dõi trạng thái khắc phục.

---

### 23. Security Standards và Security Findings

Security Hub có thể đánh giá môi trường dựa trên các tiêu chuẩn và bộ kiểm soát bảo mật.

Mỗi Finding có thể chứa:

* Title.
* Description.
* Severity.
* Resource.
* Region.
* AWS Account.
* Compliance Status.
* Remediation Recommendation.
* Workflow Status.

Các trạng thái xử lý:

```text
NEW
  ↓
NOTIFIED
  ↓
RESOLVED
```

Hoặc:

```text
SUPPRESSED
```

Không nên chỉ bật Security Hub mà không thiết lập quy trình kiểm tra và xử lý Findings.

---

## Các lỗi thực tế đã xử lý

### 1. IAM User vẫn bị Access Denied dù đã gắn Policy

Các nguyên nhân được kiểm tra:

* Policy chưa được gắn đúng User hoặc Group.
* Policy sử dụng sai Action.
* Resource ARN không phù hợp.
* Có Explicit Deny.
* Permission Boundary giới hạn quyền.
* SCP giới hạn quyền.
* Policy Condition không được đáp ứng.
* Session cũ chưa được cập nhật.

---

### 2. Không thể Assume Role

Các thành phần được kiểm tra:

* User có quyền `sts:AssumeRole`.
* Trust Policy của Role.
* Principal ARN.
* Role ARN.
* External ID nếu được yêu cầu.
* Điều kiện IP.
* Điều kiện thời gian.
* MFA Condition.
* Session Duration.

---

### 3. Resource Tag Policy không hoạt động

Các nguyên nhân được rà soát:

* Sai Tag Key.
* Giá trị Tag phân biệt chữ hoa và chữ thường.
* Sử dụng nhầm `aws:ResourceTag` và `aws:RequestTag`.
* Tag chưa tồn tại tại thời điểm đánh giá.
* Action không hỗ trợ loại Condition được sử dụng.
* Tài nguyên phụ như EBS Volume chưa được gán Tag.

---

### 4. Permission Set đã tạo nhưng User chưa truy cập được Account

Các nội dung được kiểm tra:

* User hoặc Group đã được gán đúng AWS Account.
* Permission Set đã được Provision.
* User đang sử dụng đúng Access Portal.
* Session cũ chưa hết hạn.
* Identity Source đã đồng bộ.
* Permission Set không bị giới hạn bởi SCP.

---

### 5. AWS CLI SSO không đăng nhập được

Các nguyên nhân được kiểm tra:

* Sai SSO Start URL.
* Sai SSO Region.
* Profile chưa được cấu hình.
* Token đã hết hạn.
* User chưa được Account Assignment.
* Trình duyệt không hoàn tất xác thực.

Cách xử lý:

```bash
aws sso logout
aws sso login --profile <profile-name>
```

---

### 6. KMS Access Denied

Các thành phần được kiểm tra:

* IAM Policy.
* KMS Key Policy.
* Key ARN.
* Region.
* Key State.
* Grant.
* SCP.
* Permission Boundary.
* Dịch vụ gọi KMS chưa có quyền.

---

### 7. Không nhìn thấy Finding trong Security Hub

Các nguyên nhân được rà soát:

* Security Hub chưa được bật tại đúng Region.
* Security Standard chưa được Enable.
* Dịch vụ bảo mật chưa được tích hợp.
* Finding đã bị Archive hoặc Suppress.
* Chưa có dữ liệu đánh giá.
* Quyền IAM không đủ để xem Finding.
* Bộ lọc trên giao diện đang loại bỏ Finding.

---

## Quy trình troubleshooting IAM đã hình thành

Khi gặp lỗi quyền truy cập, thực hiện theo thứ tự:

1. Xác định Principal đang thực hiện Request.
2. Xác định Action và Resource.
3. Kiểm tra Identity-Based Policy.
4. Kiểm tra Resource-Based Policy.
5. Kiểm tra Trust Policy nếu có Assume Role.
6. Kiểm tra Permission Boundary.
7. Kiểm tra Service Control Policy.
8. Kiểm tra Session Policy.
9. Kiểm tra Policy Conditions.
10. Kiểm tra KMS Key Policy nếu dữ liệu được mã hóa.
11. Sử dụng CloudTrail hoặc Policy Simulator để hỗ trợ phân tích.

Quy trình này giúp tránh việc cấp thêm quyền quá rộng chỉ để xử lý nhanh lỗi `AccessDenied`.

---

## Kỹ năng đạt được

* Hiểu AWS Shared Responsibility Model.
* Bảo vệ AWS Root User.
* Tạo và quản lý IAM User, Group và Role.
* Viết và phân tích IAM Policy.
* Hiểu cơ chế đánh giá quyền.
* Thực hiện Assume Role.
* Sử dụng Temporary Credentials.
* Cấu hình IAM Policy Conditions.
* Kiểm soát truy cập bằng Resource Tags.
* Áp dụng Permission Boundary.
* Hiểu User Pool và Identity Pool của Amazon Cognito.
* Tổ chức nhiều Account bằng AWS Organizations.
* Hiểu Service Control Policy.
* Cấu hình AWS IAM Identity Center.
* Đăng nhập AWS CLI bằng SSO.
* Hiểu cách AWS KMS quản lý khóa.
* Phân tích KMS Key Policy.
* Theo dõi Findings bằng AWS Security Hub.
* Xử lý lỗi liên quan đến IAM, KMS và Permission Sets.

---

## Tự đánh giá

* Đã hoàn thành toàn bộ nội dung Module 05.
* Hiểu rõ sự phân chia trách nhiệm bảo mật giữa AWS và khách hàng.
* Có thể phân biệt Authentication và Authorization.
* Hiểu vai trò của User, Group, Role và Policy trong AWS IAM.
* Có thể phân tích nhiều lớp ảnh hưởng đến Effective Permission.
* Hiểu cách ứng dụng sử dụng Amazon Cognito để xác thực người dùng.
* Nắm được cách AWS Organizations quản lý nhiều Account.
* Có khả năng cấu hình Users, Groups và Permission Sets trong IAM Identity Center.
* Hiểu cơ chế quản lý khóa và Envelope Encryption bằng AWS KMS.
* Hiểu vai trò của Security Hub trong việc tổng hợp và theo dõi Security Findings.
* Cải thiện khả năng troubleshooting các lỗi liên quan đến quyền truy cập.

Nội dung cần tiếp tục cải thiện:

* Thực hành thêm IAM Policy Simulator.
* Tìm hiểu sâu hơn về Attribute-Based Access Control.
* Thực hành Cognito với một ứng dụng thực tế.
* Tạo môi trường AWS Organizations gồm nhiều Member Account.
* Tìm hiểu AWS Control Tower.
* Thực hành KMS Grant và Key Rotation.
* Tích hợp Security Hub với EventBridge và SNS.
* Tìm hiểu Amazon GuardDuty, Inspector và Macie.
* Xây dựng quy trình tự động khắc phục Security Findings.

---

## Kế hoạch tiếp theo

* Chuẩn bị cho Module tiếp theo.
* Tham gia thảo luận nhóm về dự án AWS.
* Áp dụng kiến thức bảo mật vào kiến trúc dự án:

  * Tách quyền theo IAM Role.
  * Hạn chế sử dụng Access Key.
  * Áp dụng Least Privilege.
  * Bảo vệ dữ liệu bằng AWS KMS.
  * Theo dõi Security Findings.
  * Sử dụng Resource Tags để quản lý quyền.
  * Thiết kế quyền riêng cho từng thành phần.

* Tiếp tục nghiên cứu:

  * Amazon GuardDuty.
  * Amazon Inspector.
  * Amazon Macie.
  * AWS Config.
  * AWS CloudTrail.
  * Amazon CloudWatch.
  * AWS WAF.
  * AWS Shield.
  * AWS Secrets Manager.
  * AWS Systems Manager Parameter Store.

---

