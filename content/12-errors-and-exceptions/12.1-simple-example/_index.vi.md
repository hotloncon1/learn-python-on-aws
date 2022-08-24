+++
title = "Ví dụ đơn giản"
date = 2020
weight = 1
chapter = false
pre = "<b>12.1. </b>"
+++
#### Ví dụ đơn giản

Trong python, chúng ta xử lý các ngoại lệ bằng cách sử dụng một khối **try-exception** bao bọc xung quanh mã của chúng ta. Python sử dụng câu lệnh **try** để thử chạy mã và sử dụng câu lệnh **except** nếu mã trả về một số loại lỗi.

[Tài liệu](https://docs.python.org/3/tutorial/errors.html) cung cấp chi tiết về cách thực hiện điều này. Chúng ta sẽ bắt đầu với một ví dụ.

1. Tạo file **lab_9_errors.py**
* Trong Cloud9 IDE, click **+** 
* Click **New File**
![A simple example](/images/12-errors-and-exceptions/12.1-simple-example/simple-example-001.png?featherlight=false&width=90pc)
2. Trong phần code editor, thêm nội dung dưới đây:
```
integer = 50
string = "The number is"

print(string + integer)
```
![A simple example](/images/12-errors-and-exceptions/12.1-simple-example/simple-example-002.png?featherlight=false&width=90pc)
3. Nhấn tổ hợp phím **Ctrl + s** 
* Tại mục **Filename**, nhập ```lab_9_errors.py```
* Click **Save**
![A simple example](/images/12-errors-and-exceptions/12.1-simple-example/simple-example-003.png?featherlight=false&width=90pc)
4. Để chạy chương trình, nhập câu lệnh dưới đây vào terminal:
```
python lab_9_errors.py
```
* Nhấn **Enter**. Chúng ta cùng xem kết quả
![A simple example](/images/12-errors-and-exceptions/12.1-simple-example/simple-example-004.png?featherlight=false&width=90pc)

{{% notice info %}} 
Chương trình trả về **TypeError** bởi vì chúng ta không thể cộng chuỗi và số nguyên mà không chuyển đổi số nguyên thành chuỗi bằng cách sử dụng **str()**
{{% /notice %}}

5. Chúng ta thêm khối **try-except**.
* Thay đổi file **lab_9_errors.py** giống như nội dung dưới đây:
```
import logging

integer = 50
string = "The number is"

try:
    print(string + integer)
except TypeError as err:
    logging.warning("Error - {}. You cannot add a string to an integer, without converting the integer to a string first".format(err))
```
* Lưu lại
* Để chạy chương trình, nhập câu lệnh dưới đây vào terminal:
```
python lab_9_errors.py
```
* Nhấn **Enter**. Chúng ta cùng xem kết quả
![A simple example](/images/12-errors-and-exceptions/12.1-simple-example/simple-example-005.png?featherlight=false&width=90pc)

#### Thêm câu lệnh Except

Câu lệnh **except** ở trên sẽ chỉ hoạt động cho lỗi **TypeError** vì chúng ta đã chỉ định điều này trong câu lệnh **except**.

Chúng ta có thể dùng nhiều câu lệnh **except** trong đó cung cấp thông tin chi tiết để xử lý các trường hợp có các loại lỗi khác nhau.

Đây là một ví dụ:
```
import logging

integer = 50
string = "The number is"

try:
    print(string + integer)
except TypeError as t_err:
    logging.warning("Error - {}. You cannot add a string to an integer, without converting the integer to a string first".format(t_err))
except ValueError as v_err:
    logging.warning("Error - {}. Your message".format(v_err))
```

#### Các ngoại lệ được tạo bởi AWS Boto3

Chúng tôi có thể thấy các ngoại lệ được tạo ra bởi các dịch vụ AWS mà chúng tôi đang gọi. Chúng được trả lại bởi **Boto3** bằng cách sử dụng **botocore**. Chúng ta cần thêm câu lệnh **import** và sau đó chúng ta sử dụng câu lệnh **try-exception**. Dưới đây là một ví dụ.
```
import logging
import boto3
from botocore.exceptions import ClientError

try:
    client = boto3.client('translate')
except ClientError as e:
    logging.warning("<your msg> {}".format(e))
```