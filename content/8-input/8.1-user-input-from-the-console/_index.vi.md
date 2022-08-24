+++
title = "Nhập dữ liệu từ console"
date = 2020
weight = 1
chapter = false
pre = "<b>4.1. </b>"
+++
#### Nhập dữ liệu từ console

Trong phần này, chúng ta tìm hiểu cách cung cấp thông tin đầu vào của người dùng khi chương trình được chạy và chuyển thông tin này cho hàm.

1. Tạo file **lab_5_console_input.py**
* Click **+** 
* Click **New File**
![User input from the console](/images/8-input/8.1-user-input-from-the-console/user-input-from-the-console-001.png?featherlight=false&width=90pc)
2. Trong phần code editor, thêm nội dung dưới đây:
```
import boto3

def translate_text(**kwargs): 
    client = boto3.client('translate')
    response = client.translate_text(**kwargs)
    print(response) 

### Change below this line only ###

kwargs={
    "Text":"I am learning to code in AWS",
    "SourceLanguageCode":"en",
    "TargetLanguageCode":"fr"
    }

def main():
    translate_text(**kwargs)

if __name__=="__main__":
    main()
```
![User input from the console](/images/8-input/8.1-user-input-from-the-console/user-input-from-the-console-002.png?featherlight=false&width=90pc)
3. Nhấn tổ hợp phím **Ctrl + s**.
* Tại mục **Filename**, nhập ```lab_5_console_input.py```
* Click **Save**
![User input from the console](/images/8-input/8.1-user-input-from-the-console/user-input-from-the-console-003.png?featherlight=false&width=90pc)
4. Để chuyển đầu vào cho hàm của chúng ta khi chúng ta chạy tệp có tên **lab_5_console_input.py**, chúng ta cần sử dụng hàm **input()**. Thao tác này sẽ nhắc người dùng bằng một thông báo và sau đó đợi họ cung cấp thông tin đầu vào.
* Thay đổi file **lab_5_console_input.py** giống như nội dung dưới đây:
```
import boto3

def translate_text(**kwargs): 
    client = boto3.client('translate')
    response = client.translate_text(**kwargs)
    print(response) 

### Change below this line only ###

text = input("Provide the text you want translating: ")
source_language_code = input("Provide the two letter source language code: ")
target_language_code = input("Provide the two letter target language code: ") 

def main():
    translate_text(
        Text=text,
        SourceLanguageCode=source_language_code,
        TargetLanguageCode=target_language_code
        )

if __name__=="__main__":
    main()
```
* Lưu lại
![User input from the console](/images/8-input/8.1-user-input-from-the-console/user-input-from-the-console-004.png?featherlight=false&width=90pc)
5. Để chạy chương trình, nhập câu lệnh dưới đây vào terminal:
```
python lab_5_console_input.py
```
* Nhấn **Enter**.
* Tại dòng **Provide the text you want translating:**, nhập ```I am learning to code in AWS``` và nhấn **Enter**
* Tại dòng **Provide the two letter source language code:**, nhập ```en``` và nhấn **Enter**
* Tại dòng **Provide the two letter target language code:**, nhập ```fr``` và nhấn **Enter**
{{% notice info %}} 
Chương trình sẽ đợi bạn cung cấp giá trị trước khi yêu cầu lời nhắc tiếp theo.
{{% /notice %}}