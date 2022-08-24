+++
title = "Hàm đơn giản"
date = 2020
weight = 1
chapter = false
pre = "<b>6.1. </b>"
+++
#### Hàm đơn giản

Trong python, chúng ta có thể khai báo một hàm bằng cú pháp: ```def function_name():```

Một hàm bắt đầu bằng **def**, có tên viết thường, với các từ được phân tách bằng dấu gạch dưới để chúng ta có thể dễ đọc hơn, trong dấu **()** chứa các tham số và cuối cùng là dấu **:**.

#### Tạo một hàm đơn giản
1. Trong phần đầu của Cloud9 IDE.
* Click **+** 
* Click **New File** để tạo file mới
![Simple Function](/images/6-functions/6.1-simple-function/simple-function-001.png?featherlight=false&width=90pc)
2. Trong phần code editor, thêm nội dung dưới đây: 
```
# A function that prints hello world
def hello_world():
    print('hello world')

# This line calls (runs) the function
hello_world()
```
![Simple Function](/images/6-functions/6.1-simple-function/simple-function-002.png?featherlight=false&width=90pc)
3. Nhấn tổ hợp phím **Ctrl + s**
* Tại mục **Filename**, nhập ```lab_1_hello_world.py```
{{% notice info %}} 
Đuôi **.py** cho thấy rằng đây là một tệp python.
{{% /notice %}}
* Click **Save**
![Simple Function](/images/6-functions/6.1-simple-function/simple-function-003.png?featherlight=false&width=90pc)
4. Để chạy chương trình, nhập câu lệnh dưới đây vào terminal:
```
python lab_1_hello_world.py
```
* Nhấn **Enter**
![Simple Function](/images/6-functions/6.1-simple-function/simple-function-004.png?featherlight=false&width=90pc)

#### Hàm trả lại giá trị

Để hàm trả lại giá trị chúng ta sử dụng **return**.

5. Thay đổi file **lab_1_hello_world.py** giống như nội dung dưới đây:
```
# A function that returns hello world
def hello_world():
    return 'hello world'

# Assign the hello_world() function to a variable.
greeting = hello_world()
print(greeting)
```
* Lưu lại. Chúng ta đã tạo ra một hàm trả lại giá trị.
![Simple Function](/images/6-functions/6.1-simple-function/simple-function-005.png?featherlight=false&width=90pc)