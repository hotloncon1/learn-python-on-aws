+++
title = "Virtual Environments"
date = 2020
weight = 3
chapter = false
pre = "<b>2.3. </b>"
+++
#### Virtual Environments

**Virtual Environment** trong python là một vùng chứa chứa tất cả mã của chúng ta và các gói python khác. Nó cho phép chúng ta giữ cấu hình python của mình tách biệt với các phiên bản khác trên hệ thống của chúng ta. Chúng ta nên luôn sử dụng **Virtual Environment** khi phát triển mã python.

Chúng ta có thể chọn tên cho **Virtual Environment** như **my_environment** nhưng thông thường chúng ta sẽ thấy **Virtual Environment** được đặt là **venv**.

1. Để tạo **Virtual Environment** chúng ta sử  dụng câu lệnh dưới đây:
```
python -m venv my_venv
```
![Virtual Environments](/images/2-prepare/2.3-virtual-environment/virtual-environment-001.png?featherlight=false&width=90pc)
{{% notice note %}} 
Khi **Virtual Environment** được tạo, chúng ta cần phải kích hoạt nó. Sau khi được kích hoạt, code của bạn sẽ chạy bên trong **Virtual Environment**, bao gồm bất kỳ gói python nào chúng ta cài đặt.
{{% /notice %}}

2. Để kích hoạt **Virtual Environment** chúng ta sử dụng một trong những câu lệnh dưới đây tùy theo môi trường chúng ta sử dụng
* Với Linux/macOS, chạy câu lệnh dưới đây:
```
source my_venv/bin/activate
```
* Với Windows (Git-Bash), chạy câu lệnh dưới đây:
```
source my_venv/Scripts/activate
```
* Với Windows (PowerShell), chạy câu lệnh dưới đây:
```
.\my_venv\Scripts\Activate.ps1
```
![Virtual Environments](/images/2-prepare/2.3-virtual-environment/virtual-environment-002.png?featherlight=false&width=90pc)

Để biết bạn đang ở bên trong **Virtual Environment**, chúng ta sẽ thấy **(my_venv)** trước mỗi dòng trong phần **Terminal**.

Để thoát khỏi **Virtual Environment**, chúng ta nhập ```deactivate``` và nhấn **Enter**.