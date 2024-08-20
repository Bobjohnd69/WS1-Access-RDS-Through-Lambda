+++
title = "Chạy thử ứng dụng"
date = 2024
weight = 4
chapter = false
pre = "<b>4. </b>"
+++

#### Chạy thử ứng dụng

Chúng ta sẽ gửi một tin nhắn từ **SQS**, rồi sau đó sử dụng dịch vụ **CloudWatch** để kiểm tra tin nhắn có được gửi qua hay không.

1.Vào **SQS** và nhấn **Send and recieve messages**

  ![Test Application](../../images/4/4.1.png)

2.Trong **Send message**, chèn JSON này vào ô **Message body** vầ nhấn vào **Send message**

```
{
     "UserID": 1002,
     "Name": "Nguyen Tran",
     "Phone": "098732120",
     "Birthday": "2004-03-03"
}
```

  ![Test Application](../../images/4/4.2.png)

3.Để kiểm tra xem tin nhắn có được gửi qua thành công hay không. Nhập vào thanh tìm kiếm dịch vụ **CloudWatch**

  ![Test Application](../../images/4/4.3.png)

4.Trong **CloudWatch**, vào mục **Log groups** và chọn log group của chức năng **Lambda** của mình.

  ![Test Application](../../images/4/4.4.png)

5.Trong **Log Streams** chọn log mới nhất được tạo.
  
  ![Test Application](../../images/4/4.5.png)
  
  Nếu thành công thì bạn sẽ thấy thông tin người dùng sẽ hiện ở trên log.

  ![Test Application](../../images/4/4.6.png)