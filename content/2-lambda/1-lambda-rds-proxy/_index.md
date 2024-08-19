+++
title = "Create Lambda And RDS Proxy"
date = 2024
weight = 1
chapter = false
pre = "<b>1. </b>"
+++

#### Khởi tạo Lambda và RDS Proxy

1.Chọn cơ sở dữ liệu mình vừa tạo và ấn vào **Action**. Trong **Action** chọn **Set up Lambda connection**

![Create Lambda and RDS Proxy](../images/2/2.1.1.png)

2.Trong **Select Lambda function**, chọn **Create new function**. Sau đó cho hàm của mình một cái tên. `lambda-add-user-function`.

![Create Lambda and RDS Proxy](../images/2/2.1.2.png)

3.Kéo xuống đến **RDS Proxy**, chọn **Create new proxy**, ở ô **Username** và **Password** điền username và password của cơ sở dữ liệu bạn vừa tạo.

![Create Lambda and RDS Proxy](../images/2/2.1.3.png)

4.Kéo xuống và ấn **Set up**

![Create Lambda and RDS Proxy](../images/2/2.1.4.png)

{{% notice note %}}
Ở **Connection summary** bạn có thể thấy AWS sẽ tự động tạo sự nhóm bảo mật để liên kết từ Lambda đến RDS-Proxy, rồi từ RDS-Proxy sẽ truy cập vào RDS. Nếu như bạn sử dụng VPC tự tạo, hãy kiểm tra xem mình đã chọn đúng VPC, DB subnet group.
{{% /notice %}}

5.Vào phần **Proxies**, ấn vào proxies vừa được tạo.

![Create Lambda and RDS Proxy](../images/2/2.1.5.png)

6.Kéo xuống **Proxy endpoints** và ghi nhớ endpoint cho phần sau của bài lab

![Create Lambda and RDS Proxy](../images/2/2.1.6.png)
