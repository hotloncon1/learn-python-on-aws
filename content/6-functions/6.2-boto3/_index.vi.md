+++
title = "Boto3"
date = 2020
weight = 2
chapter = false
pre = "<b>6.2. </b>"
+++
#### Boto3

Chúng ta sẽ sử dụng Amazon Translate để dịch một vài văn bản từ tiếng Anh sang tiếng Pháp.

Đầu tiên chúng ta hãy tìm hiểu [Boto3 documentation for Amazon Translate](https://boto3.amazonaws.com/v1/documentation/api/latest/reference/services/translate.html)

Trong phần [client](https://boto3.amazonaws.com/v1/documentation/api/latest/reference/services/translate.html#id11), nó cho chúng ta biết cách sử dụng dịch vụ dịch trong chương trình của chúng ta.

Trong tài liệu Boto3 cho AWS Translate, chúng ta có thể thấy rằng nó hỗ trợ các cách khác nhau. Chúng ta có thể khám phá nếu chúng ta muốn. Chúng ta sẽ sử dụng method [translate_text()](https://boto3.amazonaws.com/v1/documentation/api/latest/reference/services/translate.html#id11) trong chương trình của chúng ta.

Cú pháp của **request** như sau:
```
response = client.translate_text(
    Text='string',
    TerminologyNames=[
        'string',
    ],
    SourceLanguageCode='string',
    TargetLanguageCode='string'
)
```

Đọc tài liệu bạn sẽ thấy rằng hàm **translate_text()** có ba tham số bắt buộc và một tham số không bắt buộc.
* **Text** - bắt buộc
* **TerminologyNames** - không bắt buộc
* **SourceLanguageCode** - bắt buộc
* **TargetLanguageCode** - bắt buộc

Tất cả những thứ này đều là kiểu **String**, ngoại trừ **TerminologyNames**, là **list** chứa các giá trị kiểu **String**. Nhưng chúng ta có thể bỏ qua **TerminologyName** vì nó là không bắt buộc và chúng ta chưa cần sử dụng nó.

Giá trị **SourceLanguageCode** và **TargetLanguageCode** được liệt kê trong [tài liệu](https://boto3.amazonaws.com/v1/documentation/api/latest/reference/services/translate.html#id11)

1. Chúng ta sẽ sử dụng **tiếng Ang** và **tiếng Pháp**, với mã là **en** và **fr**.
* Click **+** 
* Click **New File**
![Boto3](/images/6-functions/6.2-boto3/boto3-001.png?featherlight=false&width=90pc)
2. Trong phần code editor, thêm nội dung dưới đây:
```
import boto3

client = boto3.client('translate')

#### Add the new text below this line ####

def translate_text(): # declare the function using def, name, braces for parameters and a colon  
    response = client.translate_text(
        Text='I am learning to code in AWS', # Assigning the value of the string to the variable Text
        SourceLanguageCode='en', # We are using a two letter language code from the documentation (en = English)
        TargetLanguageCode='fr' # We use a second two letter language code from the documentation (fr = French)
    )
```
{{% notice info %}} 
Khi một cái gì đó mới được giới thiệu, mã được đánh dấu bằng các nhận xét. Trong python, bất kỳ thứ gì theo sau **'#'** sẽ là nhận xét và bị python bỏ qua.
{{% /notice %}}
![Boto3](/images/6-functions/6.2-boto3/boto3-002.png?featherlight=false&width=90pc)
3. Nhấn tổ hợp phím **Ctrl + s**.
* Tại mục **Filename**, nhập ```lab_2_intro_to_boto3.py```
* Click **Save**
![Boto3](/images/6-functions/6.2-boto3/boto3-003.png?featherlight=false&width=90pc)
4. Chúng ta đã tạo hàm và gán giá trị cho các biến của mình, chúng ta cần in ra để chúng ta có thể nhìn thấy nó. 
* Thay đổi file **lab_2_intro_to_boto3.py** giống như nội dung dưới đây:
```

import boto3

client = boto3.client('translate')

def translate_text(): 
    response = client.translate_text(
        Text='I am learning to code in AWS', 
        SourceLanguageCode='en', 
        TargetLanguageCode='fr' 
    )
#### Add the new text below this line ####
    print(response) # this code is inside the function and will print the contents of the variable 'response' 

translate_text() # This line will call our function. Without it, python will not do anything.
```
* Nhấn tổ hợp phím **Ctrl + s** để lưu lại.
![Boto3](/images/6-functions/6.2-boto3/boto3-004.png?featherlight=false&width=90pc)
5. Để chạy chương trình, nhập câu lệnh dưới đây vào terminal:
```
python lab_2_intro_to_boto3.py
```
* Nhấn **Enter**. Cùng xem kết quả.
![Boto3](/images/6-functions/6.2-boto3/boto3-005.png?featherlight=false&width=90pc)

Nếu bạn tham khảo tài liệu, nó sẽ hiển thị như sau:
```
Return type
    dict

Returns
    Response Syntax

    {
        'TranslatedText': 'string',
        'SourceLanguageCode': 'string',
        'TargetLanguageCode': 'string',
        'AppliedTerminologies': [
            {
                'Name': 'string',
                'Terms': [
                    {
                        'SourceText': 'string',
                        'TargetText': 'string'
                    },
                ]
            },
        ]
    }
```

Điều này cho chúng ta biết rằng AWS đang trả về dữ liệu dưới dạng từ điển với một cú pháp cụ thể.

So sánh những gì đã được trả về từ chương trình của chúng ta với cấu trúc trong tài liệu. Chúng ta sẽ thấy rằng nó tuân theo cấu trúc được nêu trong tài liệu cộng với một số dữ liệu từ dịch vụ AWS. Định dạng này không dễ đọc đối với chúng ta nhưng nó là định dạng được sử dụng để trao đổi thông tin giữa các chương trình và mô-đun. Trong phần sau, chúng ta sẽ tìm hiểu cách trích xuất dữ liệu từ cấu trúc này để trình bày nó ở định dạng dễ đọc hơn cho chúng ta.

Nếu chúng ta nhìn vào giá trị **TranslatedText**, chúng ta sẽ thấy **"J'apprends à coder dans AWS"**. Đó chính là văn bản tiếng Pháp trả về bởi **Amazon Translate**