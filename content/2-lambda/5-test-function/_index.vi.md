+++
title = "Chạy thử hàm Lambda"
date = 2024
weight = 5
chapter = false
pre = "<b>5. </b>"
+++

#### Chạy thử hàm Lambda
Chúng ta sẽ chạy thử để xem hàm có hoạt động như mong đợi hay không.

1.Vào Test, chọn **Create new event** và nhập vào tên của bài kiểm tra này.`testAddUser`

 ![Test Lambda Function](../images/2/2.5.1.png)

2.Ở **Event JSON**, chèn vào đoạn JSON mẫu này:
```
{
  "Records": [
    {
      "messageId": "059f36b4-87a3-44ab-83d2-661975830a7d",
      "receiptHandle": "AQEBwJnKyrHigUMZj6rYigCgxlaS3SLy0a...",
      "body": "{\n     \"UserID\": 1021,\n     \"Name\": \"Nguyen Van A\",\n     \"Phone\": \"0987443221\",\n     \"Birthday\": \"2000-01-01\"\n}",
      "attributes": {
        "ApproximateReceiveCount": "1",
        "SentTimestamp": "1545082649183",
        "SenderId": "AIDAIENQZJOLO23YVJ4VO",
        "ApproximateFirstReceiveTimestamp": "1545082649185"
      },
      "messageAttributes": {},
      "md5OfBody": "e4e68fb7bd0e697a0ae8f1bb342846b3",
      "eventSource": "aws:sqs",
      "eventSourceARN": "arn:aws:sqs:us-west-2:123456789012:my-queue",
      "awsRegion": "ap-southeast-1"
    }
  ]
}
```
 ![Test Lambda Function](../../../../images/2/2.5.2.png)

Điều chỉnh *body* và/hoặc *awsRegion* phù hợp với bài lab của mình.

3.Kéo lên và nhấn **Save** rồi nhấn **Test**

 ![Test Lambda Function](../../../images/2/2.5.3.png)

4.Nếu mọi thứ thành công thì sẽ hiện lên thông báo này:

 ![Test Lambda Function](../images/2/2.5.4.png)
