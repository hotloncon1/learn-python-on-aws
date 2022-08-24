+++
title = "Chuỗi(String)"
date = 2020
weight = 1
chapter = false
pre = "<b>4.1. </b>"
+++
#### Chuỗi
Kiểu dữ liệu **chuỗi(string)** trong Python là một trong các kiểu phổ biến nhất trong Python. Chuỗi ký tự trong python được bao quanh bởi dấu nháy đơn hoặc dấu nháy kép. Dưới đây là một số ví dụ:

```
"The quick brown fox jumped over the lazy dog"
'The quick brown fox jumped over the lazy dog'
```

Nếu chúng ta muốn sử dụng dấu nháy đơn hoặc nháy kép trong chuỗi, chúng ta có thể sử dụng một trong những cách dưới đây:
```
'The error message was "Incorrect DataType"'
"The error message was \"Incorrect DataType\""
'The error message was \'Incorrect DataType\''
"The error message was 'Incorrect DataType'"
```

1. Trong terminal, nhập ```python``` và nhấp **Enter** để mở **Interactive Mode**
![Virtual Environments](/images/4-data-types/4.1-string/string-001.png?featherlight=false&width=90pc)
2. Chuỗi(String) giống với tất cả các kiểu dữ liệu khác, chúng ta có thể gán vào biến.
* Nhập hoặc sao chép nội dung dưới đây vào **Interactive Mode**  
```
first_name = "Monty"
last_name = "Python"
```
* Nhấn **Enter**
![Virtual Environments](/images/4-data-types/4.1-string/string-002.png?featherlight=false&width=90pc)

{{% notice info %}} 
Chúng ta đã tạo một biến Python gọi là **first_name** và gán cho nó giá trị **"Monty"**. Thêm vào đó, chúng ta đã tạo một biến khác gọi là **last_name** và gán cho nó giá trị **"Python"**.
{{% /notice %}}

3. Chúng ta có thể in giá trị của các biến bằng hàm **print**
* Nhập hoặc sao chép nội dung dưới đây vào **Interactive Mode**  
```
print(first_name)
print(last_name)
```
* Nhấn **Enter**. Cùng xem kết quả.
![Virtual Environments](/images/4-data-types/4.1-string/string-003.png?featherlight=false&width=90pc)
4. Chúng ta có thể cộng chuỗi với nhau.
* Nhập hoặc sao chép nội dung dưới đây vào **Interactive Mode**  
```
print(first_name + last_name)
```
* Nhấn **Enter**. Cùng xem kết quả.
![Virtual Environments](/images/4-data-types/4.1-string/string-004.png?featherlight=false&width=90pc)
5. Chúng có thể thấy rằng không có dấu cách trong chuỗi **MontyPython**. Để bao gồm một dấu cách, Chúng ta có thể thêm dấu cách dưới dạng một chuỗi riêng biệt.
* Nhập hoặc sao chép nội dung dưới đây vào **Interactive Mode**  
```
print(first_name + " " + last_name)
```
* Nhấn **Enter**. Cùng xem kết quả.
![Virtual Environments](/images/4-data-types/4.1-string/string-005.png?featherlight=false&width=90pc)

#### Sử dụng biến trong chuỗi

Khi muốn sử dụng giá trị của một biến ở giữa một chuỗi trong python, chúng ta có thể sử dụng một vài cách.

6. Dùng **.format()** để sử dụng giá trị của một biến ở giữa một chuỗi
{{% notice info %}} 
Dùng hàm **.format()**, chúng ta có thể sử dụng **{}** trong chuỗi của chúng ta để sử dụng giá trị của một biến ở giữa một chuỗi. Chúng ta sử dụng **.format()** phía sau chuỗi để đưa giá trị của biến vào giữa chuỗi. Với mỗi biến chúng ta sử dụng một dấu **{}** trong chuỗi. Nếu chúng ta có 2 biến chúng ta sẽ sử dụng 2 dấu **{}** trong chuỗi và phía sau chuỗi **.format(variable_1, variable_2)**, giá trị của các biến trong dấu **()** của hàm **.format()** lần lượt ứng với vị trí của dấu **{}** trong chuỗi.
{{% /notice %}}
* Nhập hoặc sao chép nội dung dưới đây vào **Interactive Mode**  
```
first_name = "John"
surname = "Doe"
print("My first name is {}. My family name is {}".format(first_name, surname))
```
* Nhấn **Enter**. Cùng xem kết quả.
![Virtual Environments](/images/4-data-types/4.1-string/string-006.png?featherlight=false&width=90pc)
7. Dùng **f strings** để sử dụng giá trị của một biến ở giữa một chuỗi

* Nhập hoặc sao chép nội dung dưới đây vào **Interactive Mode**  
```
print(f"My first name is {first_name}. My family name is {surname}")
```
* Nhấn **Enter**. Cùng xem kết quả.
![Virtual Environments](/images/4-data-types/4.1-string/string-007.png?featherlight=false&width=90pc)

Có nhiều hành động hơn mà chúng ta có thể thực hiện trên chuỗi, nhưng chúng ta có đủ thông tin để bắt đầu sử dụng python với AWS. Bạn có thể tiếp tục tìm hiểu thêm hoặc chuyển sang phần tiếp theo.