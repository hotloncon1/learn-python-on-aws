+++
title = "Kiểu số"
date = 2020
weight = 2
chapter = false
pre = "<b>4.2. </b>"
+++
#### Dữ liệu kiểu số

**integer** là kiểu số nguyên, chẳng hạn như **50**. **integer** được viết tắt là **int**.

Số thực(float) là một kiểu dữ liệu số. Ví dụ: 99.9

#### Sử dụng biến kiểu số trong chuỗi

In the previous section on strings you learnt that you can use the **+** to add strings together to form sentences. You also learned that you can insert variables into a sentence using the **{}**.

What happens if we try to use a number with these two different methods?

Trong phần trước, chúng ta có thể sử dụng **+** để cộng các chuỗi lại với nhau. Chúng ta cũng có thể chèn giá trị của biến vào chuỗi sử dụng **{}**. Chúng ta cùng thử dùng để cộng một số với một chuỗi.

1. Nhập hoặc sao chép nội dung dưới đây vào **Interactive Mode** 
```
my_int = 50
sentence = "The total comes to: "
print(sentence + my_int)
```
* Nhấn **Enter**. Chúng ta sẽ thấy lỗi **TypeError**.
{{% notice info %}} 
Lỗi **TypeErrors** rất phổ biến khi chúng ta học python. Python cho chúng ta biết rằng chúng ta đang gặp lỗi về kiểu dữ liệu. Trong trường hợp này, chúng ta không thể cộng một chuỗi và một số với nhau.
{{% /notice %}}
![Virtual Environments](/images/4-data-types/4.2-numbers/numbers-001.png?featherlight=false&width=90pc)
2. Sửa lỗi bằng cách chuyển đổi kiểu dữ liệu **int** thành kiểu dữ liệu **str**.
* Nhập hoặc sao chép nội dung dưới đây vào **Interactive Mode** 
```
my_int = 50
sentence = "The total comes to: "
print(sentence + str(my_int))
```
* Nhấn **Enter**. Cùng xem kết quả.
![Virtual Environments](/images/4-data-types/4.2-numbers/numbers-002.png?featherlight=false&width=90pc)

Chúng ta đã sử dụng phương thức **str()** để chuyển đổi biến từ số nguyên thành chuỗi. Trong hầu hết các trường hợp, python sẽ xác định kiểu dữ liệu mà không cần phải khai báo. Tuy nhiên, có thể hữu ích khi cho python biết chính xác kiểu dữ liệu mà chúng ta muốn xử lý. Những ví dụ khác:
* **str()** trả về một chuỗi
* **int()** trả về một số nguyên
* **float()** trả về một số thực
* **bool()** trả về giá trị **True** hoặc **False**