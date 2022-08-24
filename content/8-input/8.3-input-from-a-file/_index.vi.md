+++
title = "Truyền dữ liệu từ tệp tin"
date = 2020
weight = 3
chapter = false
pre = "<b>8.3. </b>"
+++
#### Truyền dữ liệu từ tệp tin

Hàm **open** là một hàm được xây dựng sẵn. [Tài liệu](https://docs.python.org/3/library/functions.html#open) cho thấy rằng có một chế độ tùy chọn có thể dùng để đọc dữ liệu chuyển vào hàm của chúng ta. Chúng ta có thể sử dụng **r** để mở tệp tin với chế độ chỉ đọc. Để viết chúng ta cần sử dụng **w**.

Để nhận đầu vào từ tệp bên ngoài, chúng tôi sử dụng:
```
with open(filename, 'r' ) as variable_name:
    <Do something with the variable here>
```

1. Tạo file **lab_5_input_text_file.py**
* Click **+** 
* Click **New File** 
![Dictionaries](/images/8-input/8.3-input-from-a-file/input-from-a-file-001.png?featherlight=false&width=90pc)
2. Trong phần code editor, thêm nội dung dưới đây:
```
def open_input(file):
    with open(file, 'r') as f:
        text = f.read() #We use read() to read the actual contents of the file
        print(text)

def main():
    open_input("text.txt")

if __name__=="__main__":
    main()
```
![Dictionaries](/images/8-input/8.3-input-from-a-file/input-from-a-file-002.png?featherlight=false&width=90pc)
3. Nhấn tổ hợp phím **Ctrl + s**.
* Tại mục **Filename**, nhập ```lab_5_input_text_file.py```
* Click **Save**
![Dictionaries](/images/8-input/8.3-input-from-a-file/input-from-a-file-003.png?featherlight=false&width=90pc)
4. Tạo file **text.txt**
* Click **+** 
* Click **New File** 
![Dictionaries](/images/8-input/8.3-input-from-a-file/input-from-a-file-004.png?featherlight=false&width=90pc)
5. Trong phần code editor, thêm nội dung dưới đây:
```
"The Quick Brown Fox"
```
![Dictionaries](/images/8-input/8.3-input-from-a-file/input-from-a-file-005.png?featherlight=false&width=90pc)
6. Nhấn tổ hợp phím **Ctrl + s**.
* Tại mục **Filename**, nhập ```text.txt```
* Click **Save**
![Dictionaries](/images/8-input/8.3-input-from-a-file/input-from-a-file-006.png?featherlight=false&width=90pc)
7. Để chạy chương trình, nhập câu lệnh dưới đây vào terminal:
```
python lab_5_input_text_file.py
```
* Nhấn **Enter**. Chúng ta sẽ thấy rằng nó trả về văn bản từ file **text.txt**
![Dictionaries](/images/8-input/8.3-input-from-a-file/input-from-a-file-007.png?featherlight=false&width=90pc)

Bây giờ chúng ta có thể đọc đầu vào từ một tệp.