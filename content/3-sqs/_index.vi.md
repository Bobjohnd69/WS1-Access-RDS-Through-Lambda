+++
title = "Khởi tạo SQS"
date = 2024
weight = 3
chapter = false
pre = "<b>3. </b>"
+++

#### Tạo SQS

Chúng ta sẽ tạo một **SQS** đơn giản để có thể gọi hàm lambda và gửi thông tin người dùng.

1.Nhập vào thanh tìm kiếm dịch vụ **SQS**

  ![Create SQS](../images/3/3.1.png)

2.Ở trong **Amazon SQS** ấn vào **Create Queue**

  ![Create SQS](../images/3/3.2.png)

3.Trong **Create queue**, ở **Type** chọn **Standard Info** và điền tên cho **SQS**. `SQS-Lambda`.

  ![Create SQS](../images/3/3.3.png)

  Giữ nguyên các định dạng còn lại và ấn **Create Queue**

  ![Create SQS](../images/3/3.7.png)

4.Quay lại hàm Lambda, ấn vào **Add Trigger**

  ![Create SQS](../images/3/3.5.png)

  Trong **Trigger configuration**, ở ô **SQS queue** chọn **SQS** mình vừa mới tạo. Giữ nguyên những thứ còn lại và ấn **Add**

  ![Create SQS](../images/3/3.6.png)
