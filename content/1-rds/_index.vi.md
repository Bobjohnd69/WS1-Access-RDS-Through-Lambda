+++
title = "Khởi tạo cơ sở dữ liệu RDS"
date = 2024
weight = 1
chapter = false
pre = "<b>1. </b>"
+++

### Tạo cơ sở dữ liệu RDS

1. Ấn vào thanh tìm kiếm và chọn dịch vụ **RDS**

![Create Database](../images/1/1.0.png)

2.Trong RDS. Chọn Database rồi sau đó ấn vào "Create Database"

![Create Database](../images/1/1.1.png)

3. Trong Engine options, chọn MySQL

![Create Database](../images/1/1.2.png)

4. Giữ nguyên những thứ khác, ở phần Templates, chọn mức Free tier.

![Create Database](../images/1/1.7.png)


{{% notice note %}}
Khi tạo một cơ sỏ dữ liệu production. thì bạn nên lựa chọn "Production" và lực chọn "Multi-AZ DB instance" để bảo vệ dữ liệu của bạn phòng khi cơ sở dữ liệu chinh bị mất.
{{% /notice %}}

5.Ở phần Settings, chúng ta sẽ làm những việc như sau:
  - DB instance identifier: Cho cơ sở dữ liệu của bạn một cái tên. `db-for-lambda`
  - Master username: ghi nhớ username này cho phần sau của bài lab.
  - Credentials management: Chọn Self managed. Sau đó nhập mật khẩu cho cơ sở dữ liệu của bạn.

  ![Create Database](../images/1/1.4.png)

6.Kéo xuống đến Additional configuration. Ở phần Initial database name. Cho cơ sở dữ liệu mình một cái tên, ghi nhớ cái tên này cho phần tiếp theo của bài lab. `myDB`

  ![Create Database](../images/1/1.5.png)

7. Cuối cùng, ấn vào Create Database. Rồi đợi cho đến khi trạng thái của cơ sở dữ liệu của mình là "Available".

  ![Create Database](../images/1/1.6.png)
  ![Create Database](../images/1/1.8.png)