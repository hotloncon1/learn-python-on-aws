+++
title = "Log Level và Log File"
date = 2020
weight = 2
chapter = false
pre = "<b>11.2. </b>"
+++
#### Log Level và Log File

**Logging level** mặc định được đặt là **warning**. Điều này có thể được thay đổi vì vậy chúng ta có thể nắm bắt được nhiều hơn hoặc ít hơn thông tin trong các **Log File**.

Chúng ta sẽ thay đổi **Logging level** mặc định và lưu đầu ra của chúng ta thành tệp log cục bộ trên Cloud9 instance. Điều này được thực hiện bằng cách thêm dòng sau để cấu hình **Logging level**:
```
logging.basicConfig(filename='example.log',level=logging.DEBUG)
```

1. Tạo file **lab_8_log_level.py**
* Trong Cloud9 IDE, click **+** 
* Click **New File**
![Log Level and Log File](/images/11-logging/11.2-log-level-and-log-file/log-level-and-log-file-001.png?featherlight=false&width=90pc)
2. Trong phần code editor, thêm nội dung dưới đây:
```
# Import logging
import logging
import json

# Set the log level in the basic configuration.  This means we will capture all our log entries and not just those at Warning or above.
logging.basicConfig(filename='example.log',level=logging.DEBUG)

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
![Log Level and Log File](/images/11-logging/11.2-log-level-and-log-file/log-level-and-log-file-002.png?featherlight=false&width=90pc)
3. Nhấn tổ hợp phím **Ctrl + s** 
* Tại mục **Filename**, nhập ```lab_8_log_level.py```
* Click **Save**
![Log Level and Log File](/images/11-logging/11.2-log-level-and-log-file/log-level-and-log-file-003.png?featherlight=false&width=90pc)
4. Để chạy chương trình, nhập câu lệnh dưới đây vào terminal:
```
python lab_8_log_level.py
```
* Nhấn **Enter**. Chúng ta sẽ thấy file **example.log** đã được tạo
![Log Level and Log File](/images/11-logging/11.2-log-level-and-log-file/log-level-and-log-file-004.png?featherlight=false&width=90pc)
5. Mở file **example.log** để xem logs
![Log Level and Log File](/images/11-logging/11.2-log-level-and-log-file/log-level-and-log-file-005.png?featherlight=false&width=90pc)
6. Mở file **lab_8_log_level.py** 
* Thay đổi file **lab_8_log_level.py** giống như nội dung dưới đây:
```
# Import logging
import logging
import json

# Set the log level in the basic configuration.  This means we will capture all our log entries and not just those at Warning or above.
logging.basicConfig(filename='example.log',level=logging.DEBUG)

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
python lab_8_log_level.py
```
* Nhấn **Enter**.
![Log Level and Log File](/images/11-logging/11.2-log-level-and-log-file/log-level-and-log-file-006.png?featherlight=false&width=90pc)
7. Mở file **example.log** để xem tất cả các log
![Log Level and Log File](/images/11-logging/11.2-log-level-and-log-file/log-level-and-log-file-007.png?featherlight=false&width=90pc)