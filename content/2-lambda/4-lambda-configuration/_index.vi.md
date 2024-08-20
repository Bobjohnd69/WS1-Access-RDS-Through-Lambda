+++
title = "Chính sửa cấu hình hàm Lambda"
date = 2024
weight = 4
chapter = false
pre = "<b>4. </b>"
+++

#### Chỉnh sửa cấu hình của hàm lambda
Bây giờ chúng ta sẽ quay lại hàm Lambda của chúng ta và bắt đầu chỉnh sửa cấu hình của Lambda để có thể chạy được chức năng của bài lab này.

1.Sau khi quay lại hàm **Lambda**, kéo xuống **Runtime settings** và nhấn vào **Edit**.

  ![Lambda Configuration](../../images/2/2.4.1.png)
  - Chỉnh **Runtime** thành `Python 3.12`
  - Trong **Handler** nhập `lambda-function.lambda_handler` để khi được gọi thì **Lambda** sẽ chạy tập tin *lambda-function* với hàm *lambda_handler*.
  - Nhấn vào Save

  ![Lambda Configuration](../../images/2/2.4.2.png)

2.Vào **Configuration**, nhấn vào mục **Enviroment variables** và chọn **Edit**

  ![Lambda Configuration](../../images/2/2.4.3.png)
  Sau đó nhấn vào **Add enviroment variable** để thêm bốn biến môi trường với các giá trị sau:
  - `DB_NAME`: Tên cơ sở dữ liệu bạn đưa.
  - `PASSWORD`: Mật khẩu của cơ sở dữ liệu
  - `RDS_PROXY_HOST`: Dán vào **Proxies endpoint** mà bạn đã lưu trữ ở phần trước của bài thực hành.
  - `USER_NAME`: ghi vào **master username** của cơ sở dữ liệu.

{{% notice warning %}}
Key của bốn khóa này phải chính xác với bên code do chúng case-sensitive (phân biệt sự khác nhau giữa viết thường với viết hoa). Nếu không thì sẽ không hoạt động.
{{% /notice%}}
  Rồi cuối cùng nhấn vào **Save**

  ![Lambda Configuration](../../images/2/2.4.4.png)

3.Cũng ở trong **Configuration**, chọn mục Permission. Ở phần **Execution role**, nhấn vào **Edit**

  ![Lambda Configuration](../../images/2/2.4.5.png)

Ở phần Existing role chọn role mà chúng ta đã tạo ở phần trước, để các giá trị còn lại y nguyên rồi ấn **Save**

  ![Lambda Configuration](../../images/2/2.4.6.png)