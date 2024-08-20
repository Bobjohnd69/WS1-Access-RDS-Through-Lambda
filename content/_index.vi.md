+++
title = "Truy cập tài nguyên AWS qua Lambda"
date = 2024
weight = 1
chapter = false
+++

# Truy cập tài nguyên AWS qua Lambda

#### Tổng quan

Ở bài thực hành này, chúng ta sẽ tìm hiểu cách truy vấn vào tài nguyên cơ sở dữ liệu RDS sử dụng **Lambda** qua **RDS Proxy**. Sử dụng **Simple Queue Service** (*Dịch vụ hàng đợi đơn giản*) để gọi hàm Lambda ấy.


#### Lambda
**Lambda**: Là dịch vụ tính toán phi máy chủ. Bạn chỉ cần nạp code vào **Lambda** và **Lambda** sẽ tự động giải quyết việc quản lý tài nguyên tính toán, dự trữ dung lượng,... Và bạn chỉ cần phải trả phí cho thời gian dịch vụ **Lambda** xử lý tính toán, bạn sẽ không phải chi trả khi **Lambda** không được gọi.

#### RDS Proxy
**RDS Proxy**: Đứng trung gian giữa cơ sở dữ liệu RDS và Lambda. **RDS Proxy** có nhiệm vụ kiểm soát và quản lý các truy vấn vào cơ sở dữ liệu.

#### Simple Queue Service
**Simple Queue Service** (*Dịch vụ hàng đợi đơn giản*): Là dịch vụ giúp ta truyền, chứa và nhận các tin nhắn cho các bộ phận khác trong hệ thống. Chúng ta sẽ sử dụng **SQS** để gọi hàm Lambda.

  ![Diagram](../../images/0/0.1.png)

#### Nội dung:
1. [Khởi tạo RDS](1-rds)
2. [Khởi tạo Lambda](2-lambda)
3. [Khởi tạo SQS](3-sqs)
4. [Kiểm tra kết quả](4-testing)
5. [Dọn dẹp tài nguyên](5-clean-up)