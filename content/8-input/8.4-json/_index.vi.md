+++
title = "JSON"
date = 2020
weight = 4
chapter = false
pre = "<b>4.4. </b>"
+++
#### JSON

[**JSON**](https://www.json.org/json-en.html) viết tắt cho Javascript Object Notation. Nó có cấu trúc rất giống với từ điển và danh sách python. Đây là một định dạng rất phổ biến cho các chương trình máy tính để trao đổi thông tin trong việc sử dụng API.

Chúng ta có thể chuyển đổi Python sang JSON theo bảng dưới đây:

| Python | JSON |
| ------ | ----------- |
| dict   | object |
| list,tuple   | array |
| str   | string |
| int, float   | number |
| True   | true |
| False   | false |
| None   | null |

Chúng ta cần sử dụng gói **json** để thực hiện chuyển đổi. Gói **json** là một gói python được cài đặt sẵn nên không cần cài đặt bằng **pip**.

#### json.loads() & json.dumps()

Trước khi sử dụng tệp bên ngoài, chúng ta nên dành thời gian tìm hiểu về **json.loads()** và **json.dumps()**. Chúng ta có thể nhầm lẫn giữa **json.loads()** và **json.load()** hoặc **json.dumps()** và **json.dump()**.

Chúng ta có thể phân biệt như sau:
* **json.load()** & **json.dump()** - Sử dụng để nhập và xuất JSON từ tệp và vào tệp.
* **json.loads()** & **json.dumps()** - Sử dụng để nhập và xuất JSON từ chuỗi và thành chuỗi.

1. Tạo file **lab_5_json_input.py**
* Click **+** 
* Click **New File** 
![JSON](/images/8-input/8.4-json/json-001.png?featherlight=false&width=90pc)
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
        "TargetLanguageCode":"fr",
        "Required": true
        }
    ]
}
"""

def main():
    json_input = json.loads(json_string)
    print(json_input)

if __name__=="__main__":
    main()
```
![JSON](/images/8-input/8.4-json/json-002.png?featherlight=false&width=90pc)
3. Nhấn tổ hợp phím **Ctrl + s**.
* Tại mục **Filename**, nhập ```lab_5_json_input.py```
* Click **Save**
![JSON](/images/8-input/8.4-json/json-003.png?featherlight=false&width=90pc)
4. Để chạy chương trình, nhập câu lệnh dưới đây vào terminal:
```
python lab_5_json_input.py
```
* Nhấn **Enter**. Chúng ta cùng xem kết quả.
![JSON](/images/8-input/8.4-json/json-004.png?featherlight=false&width=90pc)

{{% notice note %}} 
Các tham số giống như là đầu vào của chúng ta cho dịch vụ **Amazon Translate** và thêm vào đó một tham số khác là **"Required": true** nhưng chỉ để minh họa. 
{{% /notice %}}
5. Chúng ta có thể sử dụng **json.dumps()** với tham số **indent** để có được định dạng với thụt lề dễ đọc:
* Thay đổi file **lab_5_json_input.py** giống như nội dung dưới đây:
```
import json

# This uses a json string as an input 

json_string = """
{
    "Input":[
        {
        "Text":"I am learning to code in AWS",
        "SourceLanguageCode":"en",
        "TargetLanguageCode":"fr",
        "Required": true
        }
    ]
}
"""

def main():
    json_input = json.loads(json_string)
    indented_format = json.dumps(json_input, indent=2)
    print(indented_format)

if __name__=="__main__":
    main()
```
* Lưu lại
![JSON](/images/8-input/8.4-json/json-005.png?featherlight=false&width=90pc)
6. Để chạy chương trình, nhập câu lệnh dưới đây vào terminal:
```
python lab_5_json_input.py
```
* Nhấn **Enter**. Chúng ta cùng xem kết quả. Chúng ta đã thêm định dạng **indent = 2** để JSON dễ đọc hơn.
![JSON](/images/8-input/8.4-json/json-006.png?featherlight=false&width=90pc)

#### Điều hướng cấu trúc JSON

Học cách điều hướng cấu trúc JSON để sử dụng thông tin chúng ta cần có lẽ là một trong những bài học cơ bản nhất chúng ta sẽ học được khi sử dụng python với AWS.

7. Thay đổi file **lab_5_json_input.py** giống như nội dung dưới đây:
```
import json

# This uses a json string as an input 

json_string = """
{
    "Input":[
        {
        "Text":"I am learning to code in AWS",
        "SourceLanguageCode":"en",
        "TargetLanguageCode":"fr",
        "Required": true
        }
    ]
}
"""
# Modify below this line
def main():
    json_input = json.loads(json_string)
    text = json_input['Input'][0]['Text']
    source_language_code = json_input['Input'][0]['SourceLanguageCode']
    target_language_code = json_input['Input'][0]['TargetLanguageCode']
    print(text, source_language_code, target_language_code)

if __name__=="__main__":
    main()
```
{{% notice info %}} 
Chúng ta sẽ thấy cách điều hướng cấu trúc JSON:\
Đầu tiên, vì JSON nằm trong biến **json_input** chúng ta sử dụng biến này để bắt đầu.\
Tiếp theo, khóa từ điển đầu tiên là **"Input"** vì vậy cái này được đặt trong dấu **[]**: **['Input']**.\
Tiếp theo, trong cấu trúc của chúng ta là một danh sách. Một danh sách sử dụng một chỉ mục và chỉ mục bắt đầu từ 0 cho phần tử đầu tiên. Vì vậy, để có được phần tử đầu tiên, chúng ta sử dụng **[0]**.\
Tiếp theo, chúng ta muốn nhận các giá trị cho các khóa **"Text"**,**"SourceLanguageCode"** và **"TargetLanguageCode"** trong từ điển.
{{% /notice %}}
* Lưu lại
![JSON](/images/8-input/8.4-json/json-007.png?featherlight=false&width=90pc)
8. Để chạy chương trình, nhập câu lệnh dưới đây vào terminal:
```
python lab_5_json_input.py
```
* Nhấn **Enter**. Chúng ta cùng xem kết quả.
![JSON](/images/8-input/8.4-json/json-008.png?featherlight=false&width=90pc)

#### json.load() & json.dump()

9. Chúng ta tạo file **translate_input.json** với một số dữ liệu JSON mà chúng ta sẽ sử dụng cho dịch vụ Amazon Translate.
* Click **+** 
* Click **New File**
![JSON](/images/8-input/8.4-json/json-009.png?featherlight=false&width=90pc)
10. Trong phần code editor, thêm nội dung dưới đây:
```
{
    "Input":[
        {
        "Text":"I am learning to code in AWS",
        "SourceLanguageCode":"en",
        "TargetLanguageCode":"fr"
        }
    ]
}
```
![JSON](/images/8-input/8.4-json/json-010.png?featherlight=false&width=90pc)
11. Nhấn tổ hợp phím **Ctrl + s**.
* Tại mục **Filename**, nhập ```translate_input.json```
* Click **Save**
![JSON](/images/8-input/8.4-json/json-011.png?featherlight=false&width=90pc)
12. Mở file **lab_5_json_input.py**
* Thay đổi file **lab_5_json_input.py** giống như nội dung dưới đây:
```
# Standard Imports
import argparse
import json

# 3rd Party Imports
import boto3

# Arguments
parser = argparse.ArgumentParser(description="Provides translation  between one source language and another of the same set of languages.")
parser.add_argument(
    '--file',
    dest='filename',
    help="The path to the input file. The file should be valid json",
    required=True)

args = parser.parse_args()

# Functions
def open_input():
    with open(args.filename) as file_object:
        contents = json.load(file_object)
        return contents['Input'][0]

def translate_text(**kwargs): 
    client = boto3.client('translate')
    response = client.translate_text(**kwargs)
    print(response) 

# Main Function - use to call other functions
def main():
    kwargs = open_input()
    translate_text(**kwargs)

if __name__ == "__main__":
    main()
```
* Save
![JSON](/images/8-input/8.4-json/json-012.png?featherlight=false&width=90pc)
13. Để chạy chương trình, nhập câu lệnh dưới đây vào terminal:
```
python lab_5_json_input.py --file translate_input.json
```
* Nhấn **Enter**. Chúng ta cùng xem kết quả.
![JSON](/images/8-input/8.4-json/json-013.png?featherlight=false&width=90pc)

Chúng ta đã sử dụng **json.loads()** và **json.dumps()** để thao tác các chuỗi JSON.