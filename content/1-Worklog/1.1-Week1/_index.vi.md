---
title: "Worklog Tuần 1"
date: 2026-04-18
weight: 1
chapter: false
pre: " <b> 1.1. </b> "

---

## Mục tiêu tuần 1:

* Làm quen với môi trường học tập, cách trao đổi và phương pháp làm việc trong cộng đồng First Cloud AI Journey.
* Xây dựng nền tảng ban đầu về điện toán đám mây và hệ sinh thái dịch vụ của AWS.
* Biết cách thiết lập tài khoản an toàn, theo dõi mức sử dụng tài nguyên và hạn chế chi phí phát sinh ngoài dự kiến.

---

### Các nhiệm vụ trong tuần:

| Ngày | Công việc                                                                                                      | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo                          |
| --- | --------------------------------------------------------------------------------------------------------- | ---------- | --------------- | ------------------------------------------- |
| 1   | - Tham gia cộng đồng FCAJ <br> - Giới thiệu bản thân, trao đổi với các thành viên <br> - Tìm hiểu cách học và các mốc hoạt động của chương trình | 18/04/2026 | 18/04/2026      |                                             |
| 2   | - Học tổng quan về AWS <br>  + Cloud Computing <br>  + AWS Global Infrastructure <br>  + Các nhóm dịch vụ | 19/04/2026 | 19/04/2026      | https://www.youtube.com/watch?v=AQlsd0nWdZk |
| 3   | - Tiến hành đăng ký tài khoản AWS cá nhân <br> - Kiểm tra thông tin thanh toán bằng thẻ Visa <br> - Ghi nhận lỗi tài khoản bị suspend và mở support case | 20/04/2026 | 20/04/2026      |                                             |
| 4   | - Chuẩn bị và gửi các tài liệu xác minh tài khoản <br> - Phản hồi email từ AWS Support <br> - Cập nhật trạng thái xử lý Account Reinstatement | 21/04/2026 | 21/04/2026      |                                             |
| 5   | - Học IAM <br> - Tạo admin group & IAM user <br> - Bật MFA (Authy)                                        | 22/04/2026 | 22/04/2026      | https://www.youtube.com/watch?v=AQlsd0nWdZk |
| 6   | - Học Billing <br> - Tạo Budget (Cost / Usage / RI / Savings Plan) <br> - Thiết lập cảnh báo              | 23/04/2026 | 23/04/2026      | https://www.youtube.com/watch?v=AQlsd0nWdZk |
| 7   | - Thực hành EC2 (Task) <br>  + Launch instance <br>  + Quan sát lifecycle <br>  + Terminate instance      | 24/04/2026 | 24/04/2026      | https://www.youtube.com/watch?v=AQlsd0nWdZk |
| 8   | - Thực hành RDS (Task) <br>  + Tạo database <br>  + Hiểu backup & cost                                    | 25/04/2026 | 25/04/2026      | https://www.youtube.com/watch?v=AQlsd0nWdZk |
| 9   | - Hoàn thiện hai nhiệm vụ còn lại với Lambda và Bedrock <br> - Kiểm tra trạng thái hoàn thành của 5 AWS credit tasks <br> - Rà soát và xóa tài nguyên không còn sử dụng | 26/04/2026 | 26/04/2026      |                                             |

---

### Kết quả đạt được tuần 1:

* Hoàn thành các module lý thuyết:

  * Module 01-01 → Làm quen với mô hình điện toán đám mây
  * Module 01-02 → Nhận biết các lợi thế khi sử dụng AWS
  * Module 01-03 → Tìm hiểu lộ trình đưa hệ thống lên môi trường Cloud
  * Module 01-04 → Nắm được cấu trúc Region, Availability Zone và Edge Location
  * Module 01-05 → Làm quen với AWS Console và các công cụ quản trị
  * Module 01-06 → Tìm hiểu nguyên tắc kiểm soát chi phí và quy trình hỗ trợ
  * Module 01-07 → Tổng hợp kiến thức thông qua nghiên cứu và thực hành

---

* Hoàn thành các bài lab thực hành:

  * Lab01-01: Thực hiện quy trình tạo tài khoản AWS, ghi nhận sự cố thanh toán và liên hệ bộ phận hỗ trợ

  * Lab01-02: Tăng cường bảo mật tài khoản bằng Virtual MFA Device

  * Lab01-03: Tổ chức quyền truy cập thông qua admin group và IAM user

  * Lab01-04: Thực hiện các bước xác minh để khôi phục quyền sử dụng tài khoản

  * Lab07:

    * Khởi tạo ngân sách theo chi phí sử dụng
    * Theo dõi ngân sách dựa trên mức tiêu thụ tài nguyên
    * Tìm hiểu Reserved Instance Budget
    * Tìm hiểu Savings Plan Budget
    * Kiểm tra và xóa các cấu hình ngân sách thử nghiệm

  * Lab09:

    * So sánh các cấp độ hỗ trợ của AWS
    * Tìm hiểu trường hợp sử dụng của từng loại support request
    * Thực hành quản lý và theo dõi tiến trình xử lý case

---

* Hoàn thành toàn bộ AWS credit tasks (5/5):

  * Launch an instance using EC2 → Completed
  * Create an Aurora or RDS database → Completed
  * Set up a cost budget using AWS Budgets → Completed
  * Create a web app using AWS Lambda → Completed
  * Use a foundation model in Amazon Bedrock playground → Completed

* Kết quả:

  * **Hoàn thành toàn bộ yêu cầu của chương trình AWS credit**
  * **Được cấp 100$ AWS credits để phục vụ quá trình học tập và thực hành**

---

#### 🔹 Thực hành RDS (Task Completed)

* Triển khai thành công một MySQL database trên Amazon RDS

* Quan sát được:

  * Sự khác biệt về cấu hình giữa t3.micro và t3.small
  * Các bước thay đổi trạng thái khi database được khởi tạo
  * Quá trình hệ thống thực hiện sao lưu trước khi chuyển sang trạng thái Available

* Rút ra được:

  * RDS có thể tiếp tục tính phí ngay cả khi không có người dùng truy cập
  * Việc giữ lại bản backup sau khi xóa database có thể làm phát sinh thêm chi phí
  * Cần kiểm tra kỹ tùy chọn retained automated backups trước khi xác nhận xóa

* Đã thực hiện:

  * Xóa RDS instance sau khi hoàn tất nhiệm vụ
  * Kiểm tra danh sách backup còn tồn tại
  * Xóa các retained automated backups không còn cần thiết

---

#### 🔹 Nhận thức về Billing & Cost

* Theo dõi biến động chi phí trong quá trình tạo và sử dụng tài nguyên AWS

* Nhận diện các dịch vụ có khả năng tạo chi phí:

  * EC2 instance đang chạy
  * RDS database và dung lượng lưu trữ
  * Snapshot hoặc backup chưa được xóa

* Thiết lập các mức cảnh báo để chủ động kiểm soát ngân sách

* Rút ra kinh nghiệm:

  * Không nên phụ thuộc hoàn toàn vào nhãn Free Tier
  * Cần kiểm tra điều kiện miễn phí của từng dịch vụ và từng loại tài nguyên
  * Nên mở Billing Dashboard thường xuyên để phát hiện chi phí bất thường

---

#### 🔹 Bảo mật & Phân quyền

* Thiết lập lớp xác thực thứ hai bằng ứng dụng Authy
* Hạn chế sử dụng Root account cho các thao tác hằng ngày
* Tạo IAM user để thực hiện các bài lab theo quyền được cấp
* Hiểu vai trò của user, group và policy trong quá trình quản lý truy cập

---

#### 🔹 Kinh nghiệm làm việc với AWS Support

* Chủ động tạo support case khi tài khoản gặp vấn đề
* Chuẩn bị thông tin và tài liệu xác minh theo yêu cầu
* Theo dõi nội dung phản hồi qua email và AWS Support Center
* Rút ra được:

  * Mỗi case cần được mô tả rõ vấn đề và cung cấp đầy đủ bằng chứng
  * Quá trình khôi phục tài khoản có thể yêu cầu nhiều bước xác minh
  * Cần lưu lại case ID để thuận tiện cho việc theo dõi và phản hồi

---

#### 🔹 Kỹ năng & Tư duy đạt được

* Phát triển kỹ năng giải quyết sự cố:

  * Kiểm tra nguyên nhân tài khoản bị hạn chế
  * Xử lý lỗi thiếu quyền truy cập tài nguyên
  * Xác định dịch vụ đang tạo ra chi phí
  * Theo dõi trạng thái hoạt động của tài nguyên AWS

* Hình thành thói quen khi thực hành Cloud:

  * Kiểm tra quyền trước khi thao tác
  * Theo dõi tài nguyên sau khi triển khai
  * Xóa instance, database và backup khi không còn sử dụng
  * Sử dụng Budget và Billing Alert để tránh vượt chi phí

* Nhận thức được:

  * Một hệ thống Cloud hiệu quả cần được cân bằng giữa kỹ thuật, bảo mật, chi phí và khả năng vận hành

---

