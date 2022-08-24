+++
title = "CLI Arguments"
date = 2020
weight = 2
chapter = false
pre = "<b>4.2. </b>"
+++
#### CLI Arguments

Trong phần trước, chúng ta đã có thể nhắc người dùng nhập vào thông tin nhưng cách này sẽ rất tốn thời gian và không tiện lợi. Nên chúng ta cần một phương pháp truyền các tham số tốt hơn và chúng ta có thể sử dụng **Command Line Interface (CLI)**

1. Tạo file **lab_5_cli_arguments.py**
* Click **+** 
* Click **New File**
![CLI Arguments](/images/8-input/8.2-cli-arguments/cli-arguments-001.png?featherlight=false&width=90pc)
2. Trong phần code editor, thêm nội dung dưới đây:
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
![CLI Arguments](/images/8-input/8.2-cli-arguments/cli-arguments-002.png?featherlight=false&width=90pc)
3. Nhấn tổ hợp phím **Ctrl + s**.
* Tại mục **Filename**, nhập ```lab_5_cli_arguments.py```
* Click **Save**
![CLI Arguments](/images/8-input/8.2-cli-arguments/cli-arguments-003.png?featherlight=false&width=90pc)
4. Chúng ta sẽ sử dụng **argparse** để truyền các đối số từ **CLI**
* Thay đổi file **lab_5_cli_arguments.py** giống như nội dung dưới đây:
```
import argparse # argparse is a built in python package, we add it with an import statement
import boto3

# Define the parser variable to equal argparse.ArgumentParser()
parser = argparse.ArgumentParser(description="Provides translation between one source language and another of the same set of languages.")

# Add each of the arguments using the parser.add_argument() method
parser.add_argument(
    '--text',
    dest="Text",
    type=str,
    help="The text to translate. The text string can be a maximum of 5,000 bytes long. Depending on your character set, this may be fewer than 5,000 characters",
    required=True
    )

parser.add_argument(
    '--source-language-code', 
    dest="SourceLanguageCode", 
    type=str, 
    help="The language code for the language of the source text. The language must be a language supported by Amazon Translate.",
    required=True
    )

parser.add_argument(
    '--target-language-code',
    dest="TargetLanguageCode",
    type=str,
    help="The language code requested for the language of the target text. The language must be a language support by Amazon Translate.",
    required=True
    )

# This will inspect the command line, convert each argument to the appropriate type and then invoke the appropriate action.
args = parser.parse_args()

def translate_text(**kwargs): 
    client = boto3.client('translate')
    response = client.translate_text(**kwargs)
    print(response) 

def main():
    # vars() is an inbuilt function which returns a dictionary object
    translate_text(**vars(args))

if __name__=="__main__":
    main()
```
{{% notice info %}} 
Chúng ta đã sử dụng **parser.add_argument()** để thêm từng đối số.\
Ví dụ tên đối số: **\-\-text**.\
Giá trị **dest** được yêu cầu để làm cho nó trở thành đối số từ khóa giá trị được chấp nhận bởi tham số, nếu không nó sẽ sử dụng đối số mặc định **text="value"** nó phải là **Text="value"**\
**type** là kiểu dữ liệu **string**(str).\
**help** là nội dung trợ giúp.\
**args = parser.parse_args()** sẽ kiểm tra dòng lệnh, chuyển đổi từng đối số thành kiểu thích hợp.\
khi chúng ta gọi hàm **translate_text()** chúng ta cần sử dụng **\*\*vars(args)**. **\*\*vars** biến đối tượng của chúng tôi được tạo ra bởi **args = parser.parse_args()** vào một đối tượng từ điển mà chúng ta có thể chuyển dưới dạng cặp **key\\:value** đến hàm của chúng ta
{{% /notice %}}
* Lưu lại
![CLI Arguments](/images/8-input/8.2-cli-arguments/cli-arguments-004.png?featherlight=false&width=90pc)
5. Để chạy chương trình, nhập câu lệnh dưới đây vào terminal:
```
python lab_5_cli_arguments.py --text "we are learning python on AWS" --source-language-code en --target-language-code fr
```
* Nhấn **Enter**.
{{% notice info %}} 
Chúng tôi đã thêm các tham số trên **CLI**.\
Mỗi tham số liên quan đến mỗi khối **parser.add_argument**.
{{% /notice %}}
![CLI Arguments](/images/8-input/8.2-cli-arguments/cli-arguments-005.png?featherlight=false&width=90pc)