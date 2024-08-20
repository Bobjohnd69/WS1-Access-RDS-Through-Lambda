+++
title = "Create Lambda And RDS Proxy"
date = 2024
weight = 2
chapter = false
pre = "<b>2. </b>"
+++

#### Thêm code vào hàm Lambda

1.Trong máy tính của bạn, tạo một thư mục mang tên `lambda-package`.

![Add code into lambda function](../../images/2/2.2.1.png)

2.Bật **Visual Studio Code** (Hoặc IDE nào bạn quen dùng), vào phần **file** và chọn **Open Folder**

![Add code into lambda function](../images/2/2.2.2.png)

3.Chọn thư mục mình vừa mới tạo và ấn **Select Folder**

![Add code into lambda function](../../../images/2/2.2.3.png)

4.Sau đó, tạo một tập tin `lambda-function.py` và một thư mục `package`.

![Add code into lambda function](../../../../images/2/2.2.4.png)

5.Trong tập tin `lambda-function.py`, chèn vào bên trong đoạn code này:

```
import json
import logging
import os
import sys

import pymysql

# Các biến cần thiết để kết nối vào rds
user_name = os.environ['USER_NAME']
password = os.environ['PASSWORD']
rds_proxy_host = os.environ['RDS_PROXY_HOST']
db_name = os.environ['DB_NAME']

logger = logging.getLogger()
logger.setLevel(logging.INFO)

#Kết nối vào RDS. Ta để bên ngoài lambda_handler để kết nối vào cơ sở dữ liệu được giữ
#khi hàm này được gọi lại ở các lần tiếp theo
try:
        conn = pymysql.connect(host=rds_proxy_host, user=user_name, passwd=password, db=db_name, connect_timeout=5)
except pymysql.MySQLError as e:
    logger.error("ERROR: Unexpected error: Could not connect to MySQL instance.")
    logger.error(e)
    sys.exit(1)

logger.info("SUCCESS: Connection to RDS for MySQL instance succeeded")

def lambda_handler(event, context):

    #Lambda lấy các thuộc tính trong JSON của tin nhắn đầu tiên của SQS
    message = event['Records'][0]['body']
    data = json.loads(message)
    UserID = data['UserID']
    Name = data['Name']
    Phone = data['Phone']
    Birthday = data['Birthday']

    user_count = 0
    sql_string = "insert into User (UserID, Name, Phone, Birthday) values(%s, %s, %s, %s)"

    with conn.cursor() as cursor:
    #Tạo một bảng người dùng nếu như chưa có trong cơ sở dữ liệu.
        cursor.execute("""
                        create table if not exists User
                        ( UserID int NOT NULL, Name varchar(255) NOT NULL, Phone varchar(20), Birthday DATE, PRIMARY KEY (UserID))
                       """)

    #Một record mới sẽ được thêm vào bảng.
        cursor.execute(sql_string, (UserID, Name, Phone, Birthday))
        conn.commit()

    #Sau đó sẽ lần lượt log ra những người dùng có trong bảng người dùng.
        cursor.execute("select * from User")
        logger.info("The following users have been added to the database:")
        for row in cursor:
            user_count += 1
            logger.info(row) 
    conn.commit()

    return "Added %d users to RDS for MySQL table" %(user_count)
```
![Add code into lambda function](../../images/2/2.2.5.png)

{{% notice note %}}
Ở đoạn code trên, chúng ta sẽ lấy các credentials để truy cập vào RDS Proxy từ **Enviroment variables**(*Biến môi trường*) của Lambda. Để giữ an toàn hơn thì bạn có thể sử dụng dịch vụ **AWS Secrect Manager** để lưu trữ các credentials này.
{{% /notice%}}

6.Để tải thư viện pymysql, nhập vào terminal:
```
pip install --target package pymysql
```
Với *--target* được dùng để khi tải thì thư viện sẽ vào thư muc package mới tạo.

![Add code into lambda function](../../images/2/2.2.6.png)

![Add code into lambda function](../../images/2/2.2.7.png)

![Add code into lambda function](../../images/2/2.2.8.png)

7.Vào thư mục package, lấy thư viện vừa mới tải và để ra ngoài như vầy (xóa thư mục package).

![Add code into lambda function](../../images/2/2.2.11.png)

Rồi nén thư mục lambda-package thành một file .zip

![Add code into lambda function](../../images/2/2.2.12.png)

![Add code into lambda function](../../images/2/2.2.13.png)

![Add code into lambda function](../../images/2/2.2.14.png)

8.Quay lại **AWS managmment console** và chọn dịch vụ **Lambda** trong thanh tìm kiếm.

![Add code into lambda function](../../images/2/2.2.15.png)

Và chọn hàm Lambda được tạo ở phần trước.

![Add code into lambda function](../../images/2/2.2.16.png)

9.Trong **code source**:
  - Nhấn vào **.zip file**
  - Chọn tập tin ném .zip mới tạo ở bước trước
  - Ấn save

![Add code into lambda function](../../images/2/2.2.17.png)

![Add code into lambda function](../../images/2/2.2.18.png)

10.Sau khi xong, bố trí lại cấu trúc thư mục như vầy.

![Add code into lambda function](../../images/2/2.2.21.png)

