+++
title = "Xác định kiểu của dữ liệu"
date = 2020
weight = 5
chapter = false
pre = "<b>4.5. </b>"
+++
#### Xác định kiểu của dữ liệu

Đôi khi mã của chúng ta sẽ xuất hiện lỗi **TypeError**. Những điều này có thể gây khó chịu khi sửa chữa. Bước đầu tiên thường là tìm kiểu của dữ liệu đó trong Python.

Trong Python, cách để tìm ra kiểu của dữ liệu đã lưu trữ trong một biến là sử dụng method **type()**.

1. Nhập hoặc sao chép nội dung dưới đây vào **Interactive Mode** 
```
my_variable = "A string"
print(type(my_variable))
```
* Nhấn **Enter**. Cùng xem kết quả.
![Determining Type](/images/4-data-types/4.5-determining-type/determining-type-001.png?featherlight=false&width=90pc)

{{% notice note %}} 
Khi bạn biết kiểu của dữ liệu, bạn có thể sửa lỗi **TypeError**.
{{% /notice %}}

2. Nhập hoặc sao chép nội dung dưới đây vào **Interactive Mode** 
```
my_number = 50
some_string = "The number is "
print(some_string + my_number)
```
* Nhấn **Enter**. Cùng xem kết quả. Chúng ta sẽ thấy lỗi **TypeError**
![Determining Type](/images/4-data-types/4.5-determining-type/determining-type-002.png?featherlight=false&width=90pc)
3. Chúng ta có thể sửa lỗi **TypeError** bằng cách chuyển **my_number** thành một chuỗi
* Nhập hoặc sao chép nội dung dưới đây vào **Interactive Mode** 
```
my_number = 50
some_string = "The number is "
print(some_string + str(my_number))
```
* Nhấn **Enter**. Cùng xem kết quả. Lỗi **TypeError** đã được sửa.
* ![Determining Type](/images/4-data-types/4.5-determining-type/determining-type-003.png?featherlight=false&width=90pc)