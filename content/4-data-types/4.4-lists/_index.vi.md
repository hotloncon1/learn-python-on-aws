+++
title = "List"
date = 2020
weight = 4
chapter = false
pre = "<b>4.4. </b>"
+++
#### List

**List** là danh sách được sử dụng để lưu trữ các giá trị có thứ tự. Ví dụ như: **[0, 1, 2, 3, 4]** hoặc **["apples", "oranges", "bananas"]**

Một **list** có thể chứa các kiểu dữ liệu khác(Ví dụ như: **dictionary**,**string**,...). Ví dụ: **[{"fruit_type" : "apples"}, {"number" : 50}]**

#### Tạo list
1. **List** có thể được tạo bằng cách gán các giá trị chúng ta muốn lưu trữ trong danh sách cho một biến
* Nhập hoặc sao chép nội dung dưới đây vào **Interactive Mode** 
```
fruit = ["apples","oranges","bananas"]
print(fruit)
```
* Nhấn **Enter**. Cùng xem kết quả.
![Lists](/images/4-data-types/4.4-lists/lists-001.png?featherlight=false&width=90pc)
2. Chúng ta có thể tạo **list** rỗng bằng 2 cách sau
* Gán **[]** cho một biến. Nhập hoặc sao chép nội dung dưới đây vào **Interactive Mode** 
```
first_empty_list = []
print(first_empty_list)
```
* Nhấn **Enter**. Cùng xem kết quả.
* Sử dụng hàm khởi tạo **list()**. Nhập hoặc sao chép nội dung dưới đây vào **Interactive Mode** 
```
second_empty_list = list()
print(second_empty_list)
```
* Nhấn **Enter**. Cùng xem kết quả.
![Lists](/images/4-data-types/4.4-lists/lists-002.png?featherlight=false&width=90pc)


#### Đọc list

Các đối tượng được lưu trữ trong **list** được cung cấp số chỉ mục bắt đầu từ **0**. Để lấy ra một phần tử từ danh sách, chúng ta sử dụng số chỉ mục của giá trị được lưu trữ.

3. Nhập hoặc sao chép nội dung dưới đây vào **Interactive Mode** 
```
fruit = ["apples","oranges","bananas"]
print(fruit[1])
```
* Nhấn **Enter**. Cùng xem kết quả.
{{% notice note %}} 
Trong ví dụ trên, chúng ta đã lấy ra giá trị được lưu trữ trong chỉ mục **1** là **oranges** bởi vì trong **list** vị trí chỉ mục đầu tiên bắt đầu từ **0**.
{{% /notice %}}
![Lists](/images/4-data-types/4.4-lists/lists-003.png?featherlight=false&width=90pc)
4. Để lấy ra độ dài của **list** chúng ta sử dụng hàm **len()**
* Nhập hoặc sao chép nội dung dưới đây vào **Interactive Mode** 
```
len(fruit)
```
* Nhấn **Enter**. Cùng xem kết quả.
![Lists](/images/4-data-types/4.4-lists/lists-004.png?featherlight=false&width=90pc)
5. Chúng ta có thể lấy giá trị ngược từ cuối **list** lên bằng cách sử dụng giá trị chỉ mục âm. Ví dụ chúng ta có thể lấy giá trị cuối cúng bằng cách sử dụng chỉ mục có giá trị là **-1**.
* Nhập hoặc sao chép nội dung dưới đây vào **Interactive Mode** 
```
print(fruit[-1])
print(fruit[-2])
```
* Nhấn **Enter**. Cùng xem kết quả.
![Lists](/images/4-data-types/4.4-lists/lists-005.png?featherlight=false&width=90pc)

#### Cập nhật list

**Lists** có thể thay đổi sau khi chúng ta tạo. Chúng ta có thể thêm, cập nhật, xóa và sắp xếp lại thứ tự các phần tử trong **list**.

6. Chúng ta có thể sử dụng hàm **append()** để thêm phần tử vào cuối của **list**.
* Nhập hoặc sao chép nội dung dưới đây vào **Interactive Mode** 
```
fruit.append("kiwi")
print(fruit)
```
* Nhấn **Enter**. Cùng xem kết quả. Chúng ta đã thêm một phần tử vào cuối của danh sách **fruit**
![Lists](/images/4-data-types/4.4-lists/lists-006.png?featherlight=false&width=90pc)
7. Nếu chúng ta muốn thêm một phần tử tại một điểm cụ thể trong **list**, chúng ta có thể sử dụng method **insert()**.
* Nhập hoặc sao chép nội dung dưới đây vào **Interactive Mode** 
```
fruit.insert(2, "passion fruit")
print(fruit)
```
* Nhấn **Enter**. Cùng xem kết quả.
![Lists](/images/4-data-types/4.4-lists/lists-007.png?featherlight=false&width=90pc)

#### Tổ chức 1 danh sách

Các phần tử trong danh sách không được sắp xếp tự động nhưng chúng ta có thể sắp xếp chúng.

8. Nếu chúng ta muốn sắp xếp những phần tử trong **list** chúng ta có thể sử dụng hàm **sorted()**.
* Nhập hoặc sao chép nội dung dưới đây vào **Interactive Mode** 
```
print(sorted(fruit))
print(fruit)
```
* Nhấn **Enter**. Cùng xem kết quả.
![Lists](/images/4-data-types/4.4-lists/lists-008.png?featherlight=false&width=90pc)

{{% notice info %}} 
Trong ví dụ trên, bạn có thể thấy rằng hàm **sorted()** trả về một danh sách đã được sắp xếp, nhưng không thay đổi thứ tự ban đầu của danh sách.
{{% /notice %}}

9. Nếu chúng ta muốn sắp xếp một **list** vĩnh viễn, chúng ta có thể sử dụng method **sort()** 
* Nhập hoặc sao chép nội dung dưới đây vào **Interactive Mode** 
```
fruit.sort()
print(fruit)
```
* Nhấn **Enter**. Cùng xem kết quả.
![Lists](/images/4-data-types/4.4-lists/lists-009.png?featherlight=false&width=90pc)
10. Để đảo ngược thứ tự những phần tử trong **list**, chúng ta có thể sử dụng method **reverse()**. Sau khi sử dụng method **reverse()**, **list** sẽ được thay đổi vĩnh viễn.
* Nhập hoặc sao chép nội dung dưới đây vào **Interactive Mode** 
```
fruit.reverse()
print(fruit)
```
* Nhấn **Enter**. Cùng xem kết quả.
![Lists](/images/4-data-types/4.4-lists/lists-010.png?featherlight=false&width=90pc)

#### Xóa phần tử trong list

11. Chúng ta có thể xóa phần tử trong **list** sử dụng câu lệnh **del** nếu chúng ta biết vị trí chỉ mục của phần tử
* Nhập hoặc sao chép nội dung dưới đây vào **Interactive Mode** 
```
del fruit[1]
print(fruit)
```
* Nhấn **Enter**. Cùng xem kết quả.
![Lists](/images/4-data-types/4.4-lists/lists-011.png?featherlight=false&width=90pc)

12. Nếu chúng ta muốn sử dụng giá trị sau khi xóa nó khỏi danh sách, bạn sử dụng method **pop()**. Để sử dụng **pop()**, chúng ta cần lưu trữ giá trị chúng ta đã xóa khỏi **list** bên trong một biến khác.
* Nhập hoặc sao chép nội dung dưới đây vào **Interactive Mode** 
```
favorite_fruit = fruit.pop()
print(favorite_fruit)
```
* Nhấn **Enter**. Cùng xem kết quả.
![Lists](/images/4-data-types/4.4-lists/lists-012.png?featherlight=false&width=90pc)
13. **pop()** mặc định trả về phần tử cuối cùng của **list**. Chúng ta có thể trả về bất cứ phần tử nào bằng cách sử dụng vị trí chỉ mục của phần tử.
* Nhập hoặc sao chép nội dung dưới đây vào **Interactive Mode** 
```
fresh_fruit = fruit.pop(1)
print(fresh_fruit)
```
* Nhấn **Enter**. Cùng xem kết quả.
![Lists](/images/4-data-types/4.4-lists/lists-013.png?featherlight=false&width=90pc)
14. Nếu chúng ta không biết vị trí chỉ mục của phần tử chúng ta có thể sử dụng method **remove()** để chỉ định giá trị của phần tử chúng ta muốn xóa
* Nhập hoặc sao chép nội dung dưới đây vào **Interactive Mode** 
```
fruit.remove('bananas')
print(fruit)
```
* Nhấn **Enter**. Cùng xem kết quả.
![Lists](/images/4-data-types/4.4-lists/lists-014.png?featherlight=false&width=90pc)

{{% notice note %}}
Khi chúng ta sử dụng **del**, **pop()** or **remove()**, phần tử sẽ bị xóa vĩnh viễn khỏi **list** ban đầu. Nếu **list** được in ra, chúng ta sẽ thấy rằng các phần tử đó không còn được lưu trữ trong **list**.
{{% /notice %}}