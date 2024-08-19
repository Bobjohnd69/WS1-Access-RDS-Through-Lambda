+++
title = "Create IAM Roles"
date = 2024
weight = 3
chapter = false
pre = "<b>3. </b>"
+++

#### Create IAM roles
Trước khi chỉnh sửa cấu hình của hàm Lambda, chúng ta sẽ tạo một vai trò IAM cấp quyền sử dụng dịch vụ **SQS** và quyền sử dụng tài nguyên trong một VPC.

1.Vào thanh tìm kiếm nhập vào dịch vụ **IAM**.

![IAM roles creation](/images/2/2.3.1.png)

2.Trong **IAM**:
  - Nhấn vào mục **Roles**
  - Nhấn vào **Create role**

![IAM roles creation](/images/2/2.3.2.png)

3.Trong **Select trusted entity**:
  - Chọn **AWS Service** nếu chưa chọn
  - Trong **Use Case**, chọn dịch vụ **Lambda**
  - Sau đó ấn vào **Next**

  ![IAM roles creation](/images/2/2.3.3.png)

4.Ở trong **Add permissions**, chúng ta sẽ cấp vào vai trò của chúng ta hai quyền:
  - `AWSLambdaSQSQueueExecutionRole`: Để cấp quyền sử dụng dịch vụ **SQS**.
  - `AWSLambdaVPCAccessExecutionRole`: Để cấp quyền lambda sử dụng tài nguyên trong VPC.

  ![IAM roles creation](/images/2/2.3.4.png)

  ![IAM roles creation](/images/2/2.3.5.png)

5.Ở phần **Role details**:
  - Cung cấp một cái tên cho **Role name**. `sqs-lambda-rds-role`.
  - Kéo xuống và xem lại các quyền mình đã cấp rồi ấn vào **Create role**

  ![IAM roles creation](/images/2/2.3.6.png)
  
  ![IAM roles creation](/images/2/2.3.7.png)

