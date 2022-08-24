+++
title = "Tham số và đối số"
date = 2020
weight = 7
chapter = false
pre = "<b>7. </b>"
+++
Tham số là biến được định nghĩa khi khai báo hàm. Khi một hàm được gọi, các đối số là dữ liệu bạn truyền vào các tham số của hàm.

#### Positional Arguments

**Positional argument** là đối số được truyền vào phụ thuộc vào thứ tự trong dấu **()**

1. Tạo file **lab_4_positional_arguments.py**
* Click **+** 
* Click **New File**
![Arguments and Parameters](/images/7-arguments-and-parameters/arguments-and-parameters-001.png?featherlight=false&width=90pc)
2. Trong phần code editor, thêm nội dung dưới đây:
```
import boto3

def translate_text():
    client = boto3.client('translate')
    response = client.translate_text(
        Text='I am learning to code in AWS', 
        SourceLanguageCode='en', 
        TargetLanguageCode='fr' 
    )
    print(response) 

def main():
    translate_text()

if __name__=="__main__":
    main()
```
![Arguments and Parameters](/images/7-arguments-and-parameters/arguments-and-parameters-002.png?featherlight=false&width=90pc)
3. Nhấn tổ hợp phím **Ctrl + s**.
* Tại mục **Filename**, nhập ```lab_4_positional_arguments.py```
* Click **Save**
![Arguments and Parameters](/images/7-arguments-and-parameters/arguments-and-parameters-003.png?featherlight=false&width=90pc)
4. Sửa đổi hàm để chúng ta có một số **positional argument** vị trí và lưu lại:
```
import boto3

def translate_text(text, source_language_code, target_language_code): # we define the positional arguments in the ()
    client = boto3.client('translate')
    response = client.translate_text(
        Text=text, # we remove the hard coded value
        SourceLanguageCode=source_language_code, # we used the positional argument instead
        TargetLanguageCode=target_language_code
    )
    print(response) 

def main():
    translate_text('I am learning to code in AWS','en','fr') # we provide the value for the arguments when we call the function in the correct positional order.

if __name__=="__main__":
    main()
```
{{% notice info %}} 
Giá trị **'I am learning to code in AWS'**, **'en'** và **'fr'** là những **positional argument** được truyền vào các tham số(parameters): **text**, **source_language_code** và **target_language_code**.
{{% /notice %}}
* Để chạy chương trình, nhập câu lệnh dưới đây vào terminal
```
python lab_4_positional_arguments.py
```
* Nhấn **Enter**. Chúng ta cùng xem kết quả.
![Arguments and Parameters](/images/7-arguments-and-parameters/arguments-and-parameters-004.png?featherlight=false&width=90pc)

#### Keyword Arguments

Một **keyword argument** là một cặp **name-value** được truyền cho hàm. Dưới đây là một số ưu điểm:

* Nếu các giá trị được truyền với các đối số vị trí sai, chúng ta sẽ gặp lỗi hoặc chương trình của chúng ta sẽ chạy không đúng. Các đối số từ khóa có thể được chuyển theo bất kỳ thứ tự nào.
* Khi sử dụng **\*\*** chúng ta có thể chuyển một số đối số từ khóa tùy ý.
* Chúng ta có thể giảm số dòng trong mã của mình.

5. Tạo file **lab_4_keyword_arguments.py**
* Click **+** 
* Click **New File**
![Arguments and Parameters](/images/7-arguments-and-parameters/arguments-and-parameters-005.png?featherlight=false&width=90pc)
6. Trong phần code editor, thêm nội dung dưới đây:
```
import boto3

def translate_text(text, source_language_code, target_language_code): 
    client = boto3.client('translate')
    response = client.translate_text(
        Text=text, 
        SourceLanguageCode=source_language_code, 
        TargetLanguageCode=target_language_code
    )
    print(response) 

def main():
    translate_text('I am learning to code in AWS','en','fr')

if __name__=="__main__":
    main()
```
![Arguments and Parameters](/images/7-arguments-and-parameters/arguments-and-parameters-006.png?featherlight=false&width=90pc)
7. Nhấn tổ hợp phím **Ctrl + s**.
* Tại mục **Filename**, nhập ```lab_4_keyword_arguments.py```
* Click **Save**
![Arguments and Parameters](/images/7-arguments-and-parameters/arguments-and-parameters-007.png?featherlight=false&width=90pc)
8. Thay đổi file **lab_4_keyword_arguments.py** giống như nội dung dưới đây:
```
import boto3

def translate_text(**kwargs): 
    client = boto3.client('translate')
    response = client.translate_text(**kwargs)
    print(response) 

def main():
    translate_text(Text='I am learning to code in AWS',SourceLanguageCode='en',TargetLanguageCode='fr')

if __name__=="__main__":
    main()
```
{{% notice info %}} 
Chúng ta đã thay thế các đối số vị trí bằng các đối số từ khóa. Điều này được thực hiện bằng cách sử dụng **\*\*kwargs**.\
Chúng ta đã xóa tất cả các thông số như **Text=text** rút ngắn mã của chúng ta và thay thế nó bằng **response = client.translate_text(\*\*kwargs)**.\
Chúng ta đã xác định các **keyword argument** khi chúng ta truyền vào khi gọi hàm bằng cú pháp **Text='I am learning to code in AWS'**.
{{% /notice %}}
* Lưu lại
![Arguments and Parameters](/images/7-arguments-and-parameters/arguments-and-parameters-008.png?featherlight=false&width=90pc)
9. Để chạy chương trình, nhập câu lệnh dưới đây vào terminal
```
python lab_4_keyword_arguments.py
```
* Nhấn **Enter**. Chúng ta cùng xem kết quả.
![Arguments and Parameters](/images/7-arguments-and-parameters/arguments-and-parameters-009.png?featherlight=false&width=90pc)
10. Chúng ta sẽ thay đổi vị trí thứ tự của các **keyword argument** để xem có bất kỳ thay đổi nào không.
* Thay đổi file **lab_4_keyword_arguments.py** giống như nội dung dưới đây:
```
import boto3

def translate_text(**kwargs): 
    client = boto3.client('translate')
    response = client.translate_text(**kwargs)
    print(response) 

def main():
    translate_text(SourceLanguageCode='en',Text='I am learning to code in AWS',TargetLanguageCode='fr')

if __name__=="__main__":
    main()
```
* Lưu lại
![Arguments and Parameters](/images/7-arguments-and-parameters/arguments-and-parameters-010.png?featherlight=false&width=90pc)
11. Để chạy chương trình, nhập câu lệnh dưới đây vào terminal
```
python lab_4_keyword_arguments.py
```
* Nhấn **Enter**. Chúng ta cùng xem kết quả. Chúng ta sẽ thấy kết quả không có bất kỳ thay đổi nào. Chúng ta sẽ thấy các **keyword argument** không phụ thuộc vào thứ tự trong dấu **()**.
![Arguments and Parameters](/images/7-arguments-and-parameters/arguments-and-parameters-011.png?featherlight=false&width=90pc)
12. Chúng tôi sẽ sử dụng **dictionary** làm **keyword argument**
* Thay đổi file **lab_4_keyword_arguments.py** giống như nội dung dưới đây:
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
{{% notice info %}} 
Chúng ta đã xác định một biến có tên là **kwargs** là từ **dictionary** chứa các cặp **key\\:value**.\
Chúng ta đã thay thế các **keyword argument** khi chúng ta truyền **\*\*kwargs** vào khi gọi hàm. The **\*\*** nói rằng đó là một đối số mà chúng ta có thể truyền số **keyword argument** tùy ý, **kwargs** là tên mà chúng ta tự định nghĩa.
Chúng tôi đặt mỗi cặp **key\\:value** trên một dòng riêng biệt để dễ đọc.
{{% /notice %}}
* Lưu lại
![Arguments and Parameters](/images/7-arguments-and-parameters/arguments-and-parameters-012.png?featherlight=false&width=90pc)
13. Để chạy chương trình, nhập câu lệnh dưới đây vào terminal
```
python lab_4_keyword_arguments.py
```
* Nhấn **Enter**. Chúng ta cùng xem kết quả.
![Arguments and Parameters](/images/7-arguments-and-parameters/arguments-and-parameters-013.png?featherlight=false&width=90pc)