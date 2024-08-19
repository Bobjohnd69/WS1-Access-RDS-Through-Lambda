+++
title = "Dọn dẹp tài nguyên"
date = 2024
weight = 5
chapter = false
pre = "<b>5. </b>"
+++

#### Dọn dẹp tài nguyên

1.Vào **SQS**
  - Chọn **SQS** của mình và ấn **Delete**
  - Điền *confirm* vào trong ô và ấn **Delete**

  ![Resource cleaning](../images/5/5.1.png)

  ![Resource cleaning](../images/5/5.2.png)

2.Vào **Lambda**
  - Chọn hàm **Lambda** của mình và ấn **Delete**
  - Điền *delete* vào trong ô và ấn **Delete**

  ![Resource cleaning](../images/5/5.3.png)

  ![Resource cleaning](../images/5/5.4.png)

3.Cũng ở trong **Lambda**, chọn mục **Event source mappings**
  - Chọn hàm **Event source mappings** của mình và ấn **Delete**
  - Điền *confirm* vào trong ô và ấn **Delete**

  ![Resource cleaning](../images/5/5.5.png)

  ![Resource cleaning](../images/5/5.6.png)

4.Vào **RDS**, ở mục **database**
  - Trong ô **Action**, chọn **Delete**
  - Bỏ lựa chọn **Retain automated backups*
  - Bỏ lựa chọn *Create final snapshot*
  - Chọn *I acknowledge that upon instance deletion, automated backup, including system snapshot and point-in-time recovery, will no longer be available.*
  - Điền *delete me* vào trong ô và ấn **Delete**

  ![Resource cleaning](../images/5/5.7.png)

  ![Resource cleaning](../images/5/5.8.png)


5.Cũng ở trong **RDS**, ở mục **Proxies**:
  - Trong ô **Action**, chọn **Delete**
  - Điền *delete me* và nhấn vào **Delete**

  ![Resource cleaning](../images/5/5.9.png)

  ![Resource cleaning](../images/5/5.10.png)

6.Điền vào trong thanh tìm kiếm và chọn chức năng **Security Group** của EC2. Vào mục **Security Groups**
  - Ở mỗi **Security Group** mà đã được tạo, xóa các inbound rules và outbound rules của mỗi **Security Group**
  - Sau đó chọn các **Security Group** ấy, ấn vào dropdown **Action** và chọn **Delete**
  - Điền *delete* vảo trong ô và nhấn **Delete**.

    ![Resource cleaning](../images/5/5.11.png)

  ![Resource cleaning](../images/5/5.12.png)

7.Vào **IAM**, ở mục **Roles**: 
  - **IAM role** mình đã tạo, rồi ấn **Delete**
  - Điền tên của role mình đã tạo vào ô và nhấn **Delete**

    ![Resource cleaning](../images/5/5.13.png)

  ![Resource cleaning](../images/5/5.14.png)

8.Cuối cùng, vào **CloudWatch**, ở mục **Log groups**
  - Chọn các **log group** đã được tạo trong bài thực hành, vào dropdown **Action** và ấn **Delete log group(s)**
  - Nhấn **Delete**

      ![Resource cleaning](../images/5/5.15.png)

  ![Resource cleaning](../images/5/5.16.png)
