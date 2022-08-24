+++
title = "Câu lệnh If - Else"
date = 2020
weight = 1
chapter = false
pre = "<b>10.1. </b>"
+++

Chúng ta sẽ thêm một số kiểm tra điều kiện, sử dụng câu lệnh **if**. Chúng ta sẽ thực hiện kiểm tra đầu vào để đảm bảo rằng các thông số được cung cấp là giá trị hợp lệ mà Amazon Translate chấp nhận.

#### Sự tương đương

Đôi khi chúng ta muốn kiểm tra xem hai giá trị có bằng nhau hay không. Chúng tôi không thể sử dụng **=** vì điều này chỉ dành để khai báo một biến. Để kiểm tra xem hai giá trị có bằng nhau nhau hay không, chúng ta cần sử dụng **==**.

Trường hợp hai giá trị bằng nhau, điều này sẽ trả về **True** và nếu họ không bằng nhau, nó sẽ trả về **False**

1. Chúng ta sẽ sử dụng **==**:
* Nhập hoặc sao chép nội dung dưới đây vào **Interactive Mode** 
```
SourceLanguageCode = "en"
TargetLanguageCode = "fr"
SourceLanguageCode == TargetLanguageCode
```
* Nhấn **Enter**. **"en"** khác với **"fr"** vì vậy **SourceLanguageCode == TargetLanguageCode** sẽ trả về **False**
![The If - Else Statement](/images/10-if-statements/10.1-if-else-statement/if-else-statement-001.png?featherlight=false&width=90pc)
2. Nhập hoặc sao chép nội dung dưới đây vào **Interactive Mode** 
```
SourceLanguageCode = "fr"
TargetLanguageCode = "fr"
SourceLanguageCode == TargetLanguageCode
```
* Nhấn **Enter**. **"fr"** và **"fr"** bằng nhau vì vậy **SourceLanguageCode == TargetLanguageCode** sẽ trả về **True**
![The If - Else Statement](/images/10-if-statements/10.1-if-else-statement/if-else-statement-002.png?featherlight=false&width=90pc)
{{% notice note %}} 
Chúng ta có thể sử dụng **ctrl + d** hoặc **exit()** để thoát khỏi **Interactive Mode**.
{{% /notice %}}
3. Chúng ta sẽ sử dụng câu lệnh **if** để tránh xảy ra lỗi khi cố dịch từ **"en"** đến **"en"**.
* Trong Cloud9 IDE, click **+** 
* Click **New File**
![The If - Else Statement](/images/10-if-statements/10.1-if-else-statement/if-else-statement-003.png?featherlight=false&width=90pc)
4. Trong phần code editor, thêm nội dung dưới đây:
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

json_input = json.loads(json_string) # We use loads as we are loading from a string.

# Defines two variables to store the language code from the input.
SourceLanguageCode = json_input['Input'][0]['SourceLanguageCode']
TargetLanguageCode = json_input['Input'][0]['TargetLanguageCode']

# The if statement checks to see if the language code is the same as the source code
if SourceLanguageCode == TargetLanguageCode:
    print("The SourceLanguageCode is the same as the TargetLanguageCode - stopping")
else:
    print("The Source Language and Target Language codes are different - proceeding")
```
![The If - Else Statement](/images/10-if-statements/10.1-if-else-statement/if-else-statement-004.png?featherlight=false&width=90pc)
5. Nhấn tổ hợp phím **Ctrl + s** 
* Tại mục **Filename**, nhập ```lab_7_equivalence.py```
* Click **Save**
![The If - Else Statement](/images/10-if-statements/10.1-if-else-statement/if-else-statement-005.png?featherlight=false&width=90pc)
6. Chúng ta nhập ```exit()``` trong **Interactive Mode** để thoát khỏi **Interactive Mode**
* Press **Enter**
* Để chạy chương trình, nhập câu lệnh dưới đây vào terminal:
```
python lab_7_equivalence.py
```
* Nhấn **Enter**
![The If - Else Statement](/images/10-if-statements/10.1-if-else-statement/if-else-statement-006.png?featherlight=false&width=90pc)
7. Thay đổi file **lab_7_equivalence.py** giống như nội dung dưới đây:
```
import json

# This uses a json string as an input 
json_string = """
{
    "Input":[
        {
        "Text":"I am learning to code in AWS",
        "SourceLanguageCode":"fr",
        "TargetLanguageCode":"fr"
        }
    ]
}
"""

json_input = json.loads(json_string) # We use loads as we are loading from a string.

# Defines two variables to store the language code from the input.
SourceLanguageCode = json_input['Input'][0]['SourceLanguageCode']
TargetLanguageCode = json_input['Input'][0]['TargetLanguageCode']

# The if statement checks to see if the language code is the same as the source code
if SourceLanguageCode == TargetLanguageCode:
    print("The SourceLanguageCode is the same as the TargetLanguageCode - stopping")
else:
    print("The Source Language and Target Language codes are different - proceeding")
```
* Lưu lại.
![The If - Else Statement](/images/10-if-statements/10.1-if-else-statement/if-else-statement-007.png?featherlight=false&width=90pc)
8. Để chạy chương trình, nhập câu lệnh dưới đây vào terminal:
```
python lab_7_equivalence.py
```
* Nhấn **Enter**. Chúng ta sẽ thấy câu lệnh **if** để ngăn lỗi khi chúng ta cố dịch từ **"fr"** thành **"fr"**
![The If - Else Statement](/images/10-if-statements/10.1-if-else-statement/if-else-statement-008.png?featherlight=false&width=90pc)

#### Các toán tử

Khi sử dụng câu lệnh if, bạn sẽ thường sử dụng các toán tử khác nhau để xác định tính tương đương. Dưới đây là một số toán tử mà python hỗ trợ

| Python | Meaning           |
| ------ | ----------------- |
| ==     | bằng nhau         |
| !=     | không bằng nhau   |
| >      | lớn hơn           |
| <      | nhỏ hơn           |
| >=     | lớn hơn hoặc bằng |
| <=     | nhở hơn hoặc bằng |