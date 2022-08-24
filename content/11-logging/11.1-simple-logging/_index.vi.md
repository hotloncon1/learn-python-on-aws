+++
title = "Ghi log đơn giản"
date = 2020
weight = 1
chapter = false
pre = "<b>11.1. </b>"
+++
#### Ghi log đơn giản

Chúng ta sẽ thay thế các câu lệnh **print()** bằng **logging** để đưa đầu ra trong console. Sử dụng **logging** cho phép chúng tôi trả lại thông tin về cách chương trình đang hoạt động. Sử dụng các phương thức như **print()** cho phép chúng ta trả lại thông tin cho người dùng.

1. Tạo file **lab_8_simple_logging.py**
* Trong Cloud9 IDE, click **+** 
* Click **New File**
![Add input validation](/images/11-logging/11.1-simple-logging/simple-logging-001.png?featherlight=false&width=90pc)
2. Trong phần code editor, thêm nội dung dưới đây:
```
import json

# This uses a json string as an input
json_string = """
{
    "Input":[
        {
        "Text":"I am learning to code in AWS",
        "SourceLanguageCode":"en",
        "TargetLanguageCode":"fr"
        }
    ]
}
"""

json_input = json.loads(json_string)

# Defines two variables to store the language code from the input.
SourceLanguageCode = json_input['Input'][0]['SourceLanguageCode']
TargetLanguageCode = json_input['Input'][0]['TargetLanguageCode']

# The if statement checks to see if the language code is the same as the source code
if SourceLanguageCode == TargetLanguageCode:
    print("The SourceLanguageCode is the same as the TargetLanguageCode - stopping")
else:
    print("The Source Language and Target Language codes are different - proceeding")
```
![Add input validation](/images/11-logging/11.1-simple-logging/simple-logging-002.png?featherlight=false&width=90pc)
3. Nhấn tổ hợp phím **Ctrl + s** 
* Tại mục **Filename**, nhập ```lab_8_simple_logging.py```
* Click **Save**
![Add input validation](/images/11-logging/11.1-simple-logging/simple-logging-003.png?featherlight=false&width=90pc)
4. Chúng tôi vừa dùng **print()** để xuất các thông báo ra bảng điều khiển. Đó là nơi chúng ta cần thực hiện các thay đổi đối với mã để thêm chúng vào nhật ký thay vì xuất ra bảng điều khiển.
* Thay đổi file **lab_8_simple_logging.py** giống như nội dung dưới đây:
```
# Import logging
import logging
import json

# This uses a json string as an input
json_string = """
{
    "Input":[
        {
        "Text":"I am learning to code in AWS",
        "SourceLanguageCode":"en",
        "TargetLanguageCode":"fr"
        }
    ]
}
"""

json_input = json.loads(json_string)

# Defines two variables to store the language code from the input.
SourceLanguageCode = json_input['Input'][0]['SourceLanguageCode']
TargetLanguageCode = json_input['Input'][0]['TargetLanguageCode']

# The if statement checks to see if the language code is the same as the source code
if SourceLanguageCode == TargetLanguageCode:
    logging.warning("The SourceLanguageCode is the same as the TargetLanguageCode - stopping") # This will print to the console as the default level is warning
else:
    logging.info("The Source Language and Target Language codes are different - proceeding") # This will not print to the console because it is lower than warning
```
* Lưu lại
![Add input validation](/images/11-logging/11.1-simple-logging/simple-logging-004.png?featherlight=false&width=90pc)
5. Để chạy chương trình, nhập câu lệnh dưới đây vào terminal:
```
python lab_8_simple_logging.py --file translate_input.json
```
* Nhấn **Enter**. Chúng ta cùng xem kết quả
![Add input validation](/images/11-logging/11.1-simple-logging/simple-logging-005.png?featherlight=false&width=90pc)
{{% notice info %}} 
Điều này sẽ không trả lại gì cho bảng điều khiển. Điều này là do theo mặc định, ghi log được đặt thành **logging.warning**. Bởi vì mã là chính xác, nó không tạo ra một cảnh báo nào.
{{% /notice %}}
6. Thay đổi **lab_8_simple_logging.py** giống như nội dung dưới đây:
```
# Import logging
import logging
import json

# This uses a json string as an input
json_string = """
{
    "Input":[
        {
        "Text":"I am learning to code in AWS",
        "SourceLanguageCode":"en",
        "TargetLanguageCode":"en"
        }
    ]
}
"""

json_input = json.loads(json_string)

# Defines two variables to store the language code from the input.
SourceLanguageCode = json_input['Input'][0]['SourceLanguageCode']
TargetLanguageCode = json_input['Input'][0]['TargetLanguageCode']

# The if statement checks to see if the language code is the same as the source code
if SourceLanguageCode == TargetLanguageCode:
    logging.warning("The SourceLanguageCode is the same as the TargetLanguageCode - stopping") # This will print to the console as the default level is warning
else:
    logging.info("The Source Language and Target Language codes are different - proceeding") # This will not print to the console because it is lower than warning
```
* Lưu lại
* Để chạy chương trình, nhập câu lệnh dưới đây vào terminal:
```
python lab_8_simple_logging.py --file translate_input.json
```
* Nhấn **Enter**. Chúng ta cùng xem kết quả. We will see the **WARNING** log.
![Add input validation](/images/11-logging/11.1-simple-logging/simple-logging-006.png?featherlight=false&width=90pc)