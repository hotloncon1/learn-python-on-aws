+++
title = "Dictionaries"
date = 2020
weight = 3
chapter = false
pre = "<b>4.3. </b>"
+++
#### Dictionaries

Kiểu dữ liệu **Dictionary** trong Python là một tập hợp các cặp **key-value**. Nó sử dụng **key** duy nhất để định danh và **value** để lưu trữ giá trị. **Key** phải là một kiểu dữ liệu không thay đổi (immutable) như chuỗi, số hoặc tuple. **Value** có thể là bất kỳ kiểu giá trị nào. **Dictionary** được khởi tạo với các dấu ngoặc nhọn **{}** và chúng có các khóa và giá trị **(key-value)**. Mỗi cặp **key-value** được xem như là một item.


Dictionaries rất phổ biến trong AWS, vì vậy chúng ta sẽ thấy chúng thường xuyên:
* Chúng được sử dụng để trao đổi thông tin giữa các dịch vụ và chức năng khác nhau
* Chúng được trả lại bởi API(Application Programming Interfaces)
* Chúng được sử dụng như giá trị **Tag**

#### Tạo dictionary

Dictionaries có thể được tạo bằng cách gán các **key-value** mà bạn muốn lưu trữ trong dictionary.

1. Nhập hoặc sao chép nội dung dưới đây vào **Interactive Mode** 
```
user = {"first_name":"Ada"}
print(user)
```
* Nhấn **Enter**. Cùng xem kết quả.
![Dictionaries](/images/4-data-types/4.3-dictionaries/dictionaries-001.png?featherlight=false&width=90pc)
2. Chúng ta có thể tạo **dictionary** rỗng bằng 2 cách.
* Gán **{}** vào một biến, nhập hoặc sao chép nội dung dưới đây vào **Interactive Mode** 
```
first_empty_dictionary = {}
print(first_empty_dictionary)
```
* Nhấn **Enter**.
* Sử dụng hàm tạo **dict()**, nhập hoặc sao chép nội dung dưới đây vào **Interactive Mode** 
```
second_empty_dictionary = dict()
print(second_empty_dictionary)
```
* Nhấn **Enter**. Cùng xem kết quả.
![Dictionaries](/images/4-data-types/4.3-dictionaries/dictionaries-002.png?featherlight=false&width=90pc)

#### Đọc dictionary

Để đọc **value** được liên kết với **key**, bạn cần cung cấp tên của **dictionary** và giá trị của **key** bên trong dấu ngoặc vuông.

3. Nhập hoặc sao chép nội dung dưới đây vào **Interactive Mode** 
```
user = {"first_name":"Ada"}
print(user["first_name"])
```
* Nhấn **Enter**. Cùng xem kết quả. Chúng ta đã đọc được giá trị được liên kết với **key** có giá trị **first_name** của **dictionary** có tên **user**
![Dictionaries](/images/4-data-types/4.3-dictionaries/dictionaries-003.png?featherlight=false&width=90pc)

#### Cập nhật **dictionary**

**Dictionaries** có thể thay đổi sau khi tạo. Chúng ta có thể thêm, cập nhật hoặc xóa các cặp **key-value** trong **dictionary**.

4. Để thêm cặp **key-value** vào **dictionary**, chúng ta thực hiện như ví dụ dưới đây
* Nhập hoặc sao chép nội dung dưới đây vào **Interactive Mode** 
```
user["family_name"] = "Byron"
print(user)
```
* Nhấn **Enter**. Chúng ta đã thêm một cặp **key-value** vào **dictionary** có tên **user**
![Dictionaries](/images/4-data-types/4.3-dictionaries/dictionaries-004.png?featherlight=false&width=90pc)
5. Để sửa đổi một giá trị theo cách tương tự để thêm nó.
* Nhập hoặc sao chép nội dung dưới đây vào **Interactive Mode** 
```
user["family_name"] = "Lovelace"
print(user)
```
* Nhấn **Enter**. Cùng xem kết quả. Chúng ta đã thay đổi giá trị được liên kết với **key** là **first_name** thành **"Lovelace"**
![Dictionaries](/images/4-data-types/4.3-dictionaries/dictionaries-005.png?featherlight=false&width=90pc)
6. Để xóa một cặp **key-value**, chúng ta sẽ sử dụng câu lệnh **del**
* Nhập hoặc sao chép nội dung dưới đây vào **Interactive Mode** 
```
del user["family_name"]
print(user)
```
* Nhấn **Enter**. Cùng xem kết quả. Chúng ta đã xóa cặp **key-value** có **key** là **first_name**
![Dictionaries](/images/4-data-types/4.3-dictionaries/dictionaries-006.png?featherlight=false&width=90pc)