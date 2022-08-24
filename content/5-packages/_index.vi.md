+++
title = "Python Packages"
date = 2020
weight = 5
chapter = false
pre = "<b>5. </b>"
+++
#### Python Packages
**Python package** là mã bao gồm các thành phần riêng lẻ được gọi là mô-đun mà chúng ta có thể sử dụng trong mã của mình. Các gói giúp chúng ta không phải viết mọi thứ của chương trình từ đầu bằng cách cho phép chúng ta sử dụng mã của những người khác. Bằng cách nhập các gói(package) vào chương trình của chúng ta, chúng ta có thể sử dụng các tính năng của gói đó. Python có các gói(package) phổ biến có sẵn, những gói(package) khác phải được cài đặt vào môi trường ảo của chúng ta bằng trình quản lý gói(package) python [pip](https://pypi.org/project/pip/).

Để làm việc với AWS, bạn sẽ cần cài đặt gói(package) [Boto3](https://pypi.org/project/pip/)

1. Trong terminal nhập:
```
pip install boto3
```
![Python Packages](/images/5-packages/packages-001.png?featherlight=false&width=90pc)

{{% notice note %}} 
Nếu bạn nhận được thông báo lỗi. Kiểm tra xem bạn đã thoát khỏi môi trường **Interactive Mode** nếu chưa hãy sử dụng **crtl + d** hoặc nhập ```exit()``` và nhấn **Enter** để thoát khỏi môi trường **Interactive Mode**.
{{% /notice %}}

2. Chúng ta có thể xem những gói(package) nào chúng ta đã cài đặt nhập nội dung dưới đây vào terminal:
```
pip freeze
```
* Cùng xem kết quả.
![Python Packages](/images/5-packages/packages-002.png?featherlight=false&width=90pc)