+++
title = "Vòng lặp đơn giản"
date = 2020
weight = 1
chapter = false
pre = "<b>9.1. </b>"
+++
#### Vòng lặp đơn giản

Chúng ta sẽ tạo một ví dụ đơn giản trong **Python Interactive Mode** để hiển thị cách hoạt động của vòng lặp qua danh sách.

1. Tạo một danh sách và gán nó cho một biến:
* Nhập hoặc sao chép nội dung dưới đây vào **Interactive Mode**
```
fruit = ['apples','oranges','bananas']
```
* Nhấn **Enter**
![Simple Loops](/images/9-loop/9.1-simple-loop/simple-loop-001.png?featherlight=false&width=90pc)
2. Tạo vòng lặp **for** và in ra từng phần từ trong danh sách
* Nhập hoặc sao chép nội dung dưới đây vào **Interactive Mode**
```
for item in fruit:
   print(f'The best fruit now is {item}')
```
* Nhấn hai lần **Enter**. Chúng ta cùng xem kết quả
![Simple Loops](/images/9-loop/9.1-simple-loop/simple-loop-002.png?featherlight=false&width=90pc)
3. Nếu chúng ta muốn sử dụng một vòng lặp như một bộ đếm, chúng ta có thể tạo một danh sách các số và gán nó cho một biến
* Nhập hoặc sao chép nội dung dưới đây vào **Interactive Mode**
```
numbers = [0,1,2,3,4,5,6,7,8,9,10]
```
* Nhấn **Enter**
![Simple Loops](/images/9-loop/9.1-simple-loop/simple-loop-003.png?featherlight=false&width=90pc)
4. Nhập hoặc sao chép nội dung dưới đây vào **Interactive Mode**
```
for number in numbers:
   print(f'The next number is {number}')
```
{{% notice info %}} 
Ví dụ này in tất cả các số từ 0 đến 10
{{% /notice %}}
* Nhấn hai lần **Enter**. Chúng ta cùng xem kết quả
![Simple Loops](/images/9-loop/9.1-simple-loop/simple-loop-004.png?featherlight=false&width=90pc)
5. Ví dụ trước in tất cả các số từ 0 đến 10, nhưng nếu chúng ta muốn đếm đến 1000. Sẽ rất tẻ nhạt nếu viết tất cả các số theo cách này. Thay vì nó ta sử dụng hàm **range()**.
* Nhập hoặc sao chép nội dung dưới đây vào **Interactive Mode**
```
for number in range(10):
   print(f'The next number is {number}')
```
* Nhấn hai lần **Enter**. Chúng ta cùng xem kết quả
![Simple Loops](/images/9-loop/9.1-simple-loop/simple-loop-005.png?featherlight=false&width=90pc)
6. Ví dụ trước, chúng ta có thể thấy rằng bắt đầu ở 0 là số đầu tiên, nếu chúng ta muốn bắt đầu đếm từ 1, chúng ta vẫn có thể sử dụng hàm **range()**.
* Nhập hoặc sao chép nội dung dưới đây vào **Interactive Mode**
```
for number in range(1,10):
   print(f'The next number is {number}')
```
* Nhấn hai lần **Enter**. Chúng ta cùng xem kết quả
![Simple Loops](/images/9-loop/9.1-simple-loop/simple-loop-006.png?featherlight=false&width=90pc)
7. Nếu chúng ta muốn tăng bộ đếm nhiều hơn giá trị mặc định là 1, ví dụ như chúng ta chỉ muốn các số lẻ hoặc số chẵn chẳng hạn. Để làm điều này, chúng ta thêm một tham số thứ ba vào hàm **range()**
* Nhập hoặc sao chép nội dung dưới đây vào **Interactive Mode**
```
for number in range(1,10,2):
   print(f'The next number is {number}')
```
{{% notice info %}} 
Hàm **range(start, stop, step)** bao gồm 3 tham số:\
**start** : Không bắt buộc. Một số nguyên chỉ định vị trí bắt đầu. Mặc định là 0.\
**stop** : Bắt buộc. Một số nguyên chỉ định vị trí dừng (không được bao gồm).\
**step** : Không bắt buộc. Một số nguyên xác định bước tăng. Mặc định là 1
{{% /notice %}}
* Nhấn hai lần **Enter**. Chúng ta cùng xem kết quả
![Simple Loops](/images/9-loop/9.1-simple-loop/simple-loop-007.png?featherlight=false&width=90pc)