+++
title = "Kiểm tra giá trị trong danh sách"
date = 2020
weight = 2
chapter = false
pre = "<b>10.2. </b>"
+++
#### Kiểm tra giá trị trong danh sách

Amazon Translate chỉ hỗ trợ một danh sách các ngôn ngữ được xác định. Danh sách mã ngôn ngữ mà Amazon Translate  sẽ chấp nhận được cung cấp trong [tài liệu](https://docs.aws.amazon.com/translate/latest/dg/what-is.html). Chúng ta có thể sử dụng câu lệnh if để thực hiện một số xác thực đầu vào để kiểm tra xem mã ngôn ngữ có trong danh sách hay không.

1. Tạo file **lab_7_check_language.py**
* Trong Cloud9 IDE, click **+** 
* Click **New File**
![Checking Values in a List](/images/10-if-statements/10.2-checking-value-in-the-list/checking-value-in-the-list-001.png?featherlight=false&width=90pc)
2. Trong phần code editor, thêm nội dung dưới đây:
```
import json

# A defined list of languages supported by Amazon Translate
languages = ["af","sq","am","ar","az","bn","bs","bg","zh","zh-TW","hr","cs","da","fa-AF","nl","en","et","fi","fr","fr-CA","ka","de","el","ha","he","hi","hu","id","it","ja","ko","lv","ms","no","fa","ps","pl","pt","ro","ru","sr","sk","sl","so","es","sw","sv","tl","ta","th","tr","uk","ur","vi"]

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

# Extracts the SourceLanguageCode and TargetLanguageCode from the JSON
SourceLanguageCode = json_input['Input'][0]['SourceLanguageCode']
TargetLanguageCode = json_input['Input'][0]['TargetLanguageCode']

# Uses an if-else statement to check that the SourceLanguageCode is in the languages list.
if SourceLanguageCode in languages:
    print("The SourceLanguageCode is valid - proceeding")
else:
    print("The SourceLanguageCode is not valid - stopping")
```
![Checking Values in a List](/images/10-if-statements/10.2-checking-value-in-the-list/checking-value-in-the-list-002.png?featherlight=false&width=90pc)
3. Nhấn tổ hợp phím **Ctrl + s** 
* Tại mục **Filename**, nhập ```lab_7_check_language.py```
* Click **Save**
![Checking Values in a List](/images/10-if-statements/10.2-checking-value-in-the-list/checking-value-in-the-list-003.png?featherlight=false&width=90pc)
4. Để chạy chương trình, nhập câu lệnh dưới đây vào terminal:
```
python lab_7_check_language.py
```
* Nhấn **Enter**. Chúng ta cùng xem kết quả
![Checking Values in a List](/images/10-if-statements/10.2-checking-value-in-the-list/checking-value-in-the-list-004.png?featherlight=false&width=90pc)
{{% notice info %}} 
Chúng tôi đã sử dụng câu lệnh **if** kết hợp với **in** để kiểm tra xem mã ngôn ngữ có hợp lệ hay không.
{{% /notice %}}