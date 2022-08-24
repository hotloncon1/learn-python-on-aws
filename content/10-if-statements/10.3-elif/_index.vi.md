+++
title = "Elif"
date = 2020
weight = 3
chapter = false
pre = "<b>10.3. </b>"
+++
#### Elif

Câu lệnh **and** là một toán tử logic kết hợp việc kiểm tra cả ngôn ngữ nguồn và ngôn ngữ đích. Câu lệnh **elif** cho phép chúng ta đưa ra nhiều phép kiểm tra logic khác nhau.

1. Tạo file **lab_7_elif.py**
* Trong Cloud9 IDE, click **+** 
* Click **New File**
![Elif](/images/10-if-statements/10.3-elif/elif-001.png?featherlight=false&width=90pc)
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

SourceLanguageCode = json_input['Input'][0]['SourceLanguageCode']
TargetLanguageCode = json_input['Input'][0]['TargetLanguageCode']

# Uses an if-elif-else statements to check that the SourceLanguageCode is in the languages list.
if SourceLanguageCode == TargetLanguageCode:
    print("The SourceLanguageCode is the same as the TargetLanguageCode - nothing to do")
elif SourceLanguageCode not in languages and TargetLanguageCode not in languages:
    print("Neither the SourceLanguageCode and TargetLanguageCode are valid - stopping")
elif SourceLanguageCode not in languages:
    print("The SourceLanguageCode is not valid - stopping")
elif TargetLanguageCode not in languages:
    print("The TargetLanguageCode is not valid - stopping")
elif SourceLanguageCode in languages and TargetLanguageCode in languages:
    print("The SourceLanaguageCode and TargetLanguageCode are valid - proceeding")
else:
    print("There is an issue")
```
![Elif](/images/10-if-statements/10.3-elif/elif-002.png?featherlight=false&width=90pc)
3. Nhấn tổ hợp phím **Ctrl + s** 
* Tại mục **Filename**, nhập ```lab_7_elif.py```
* Click **Save**
![Elif](/images/10-if-statements/10.3-elif/elif-003.png?featherlight=false&width=90pc)
4. Để chạy chương trình, nhập câu lệnh dưới đây vào terminal:
```
python lab_7_elif.py
```
* Nhấn **Enter**. Chúng ta cùng xem kết quả
![Elif](/images/10-if-statements/10.3-elif/elif-004.png?featherlight=false&width=90pc)
5. Chúng ta sẽ kiểm tra bằng cách thay đổi các giá trị của **SourceLanguageCode** và giá trị của **TargetLanguageCode**
* Thay đổi **SourceLanguageCode** và **TargetLanguageCode** thành giá trị giống nhau. Thay đổi file **lab_7_elif.py** giống như nội dung dưới đây:
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
        "TargetLanguageCode":"en"
        }
    ]
}
"""

json_input = json.loads(json_string)

SourceLanguageCode = json_input['Input'][0]['SourceLanguageCode']
TargetLanguageCode = json_input['Input'][0]['TargetLanguageCode']

# Uses an if-elif-else statements to check that the SourceLanguageCode is in the languages list.
if SourceLanguageCode == TargetLanguageCode:
    print("The SourceLanguageCode is the same as the TargetLanguageCode - nothing to do")
elif SourceLanguageCode not in languages and TargetLanguageCode not in languages:
    print("Neither the SourceLanguageCode and TargetLanguageCode are valid - stopping")
elif SourceLanguageCode not in languages:
    print("The SourceLanguageCode is not valid - stopping")
elif TargetLanguageCode not in languages:
    print("The TargetLanguageCode is not valid - stopping")
elif SourceLanguageCode in languages and TargetLanguageCode in languages:
    print("The SourceLanaguageCode and TargetLanguageCode are valid - proceeding")
else:
    print("There is an issue")
```
* Lưu lại
* Để chạy chương trình, nhập câu lệnh dưới đây vào terminal:
```
python lab_7_elif.py
```
* Nhấn **Enter**. Chúng ta cùng xem kết quả
![Elif](/images/10-if-statements/10.3-elif/elif-005.png?featherlight=false&width=90pc)

Làm tương tự như khi chúng ta kiểm tra khi hai giá trị **SourceLanguageCode** và **TargetLanguageCode** bằng nhau, chúng ta kiểm tra trường hợp sau và xem kết quả:
* Thay đổi **SourceLanguageCode** và **TargetLanguageCode** thành các giá trị khác nhau nhưng không hợp lệ.
* Thay đổi **SourceLanguageCode** thành một giá trị không được hỗ trợ và **TargetLanguageCode** thành một giá trị được hỗ trợ.
* Thay đổi **SourceLanguageCode** thành một giá trị được hỗ trợ và **TargetLanguageCode** thành một giá trị không được hỗ trợ.
* Thay đổi cả hai biến **SourceLanguageCode** và **TargetLanguageCode** thành các giá trị được hỗ trợ nhưng khác nhau.