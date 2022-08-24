+++
title = "Liệt kê danh sách"
date = 2020
weight = 3
chapter = false
pre = "<b>9.3. </b>"
+++

1. Chúng ta sẽ tạo một danh sách chỉ gồm văn bản mà chúng tôi muốn dịch từ dữ liệu được cung cấp của file **translate_input.json**
* Mở file **lab_6_loops.py**
* Thêm hàm sau vào trong file **lab_6_loops.py**
```
# Create a list of the input text
def new_input_text_list():
    input_text = open_input()
    new_list = []
    for item in input_text:
        text = item['Text']
        new_list.append(text)
    print(new_list)
```
* Gọi hàm **new_input_text_list()** trong hàm **main()** giống như sau:
```
def main():
    new_input_text_list()
    translate_loop()
```
* Save
![Looping over JSON](/images/9-loop/9.3-list-comprehensions/list-comprehensions-001.png?featherlight=false&width=90pc)
2. Để chạy chương trình, nhập câu lệnh dưới đây vào terminal:
```
python lab_6_loops.py --file translate_input.json
```
* Nhấn **Enter**. Chúng ta cùng xem kết quả.
![Looping over JSON](/images/9-loop/9.3-list-comprehensions/list-comprehensions-002.png?featherlight=false&width=90pc)

Chúng ta sẽ thấy trả về một danh sách giống như:
```
['What is cloud computing?', 'Cloud computing is the on-demand delivery of IT resources over the Internet with pay-as-you-go pricing.', 'Instead of buying, owning, and maintaining physical data centers and servers, you can access technology services, such as computing power, storage, and databases, on an as-needed basis from a cloud provider like Amazon Web Services (AWS)', 'Who is using cloud computing?', 'Organizations of every type, size, and industry are using the cloud for a wide variety of use cases, such as data backup, disaster recovery, email, virtual desktops, software development and testing, big data analytics, and customer-facing web applications.', 'For example, healthcare companies are using the cloud to develop more personalized treatments for patients. Financial services companies are using the cloud to power real-time fraud detection and prevention.', 'And video game makers are using the cloud to deliver online games to millions of players around the world.']
```

#### List Comprehensions

3. Chúng ta sẽ sử dụng kết hợp vòng lặp **for** và tạo danh sách thành một dòng.
* Mở file **lab_6_loops.py**
* Thêm hàm sau vào trong file **lab_6_loops.py**
```
def new_list_comprehension():
    input_text = open_input()
    list_comprehension = [item['Text'] for item in input_text]
    print(list_comprehension)
```
* Gọi hàm **new_list_comprehension()** trong hàm **main()** giống như sau:
```
def main():
    new_input_text_list()
    translate_loop()
    new_list_comprehension()
```
* Lưu lại
![Looping over JSON](/images/9-loop/9.3-list-comprehensions/list-comprehensions-003.png?featherlight=false&width=90pc)
4. Để chạy chương trình, nhập câu lệnh dưới đây vào terminal:
```
python lab_6_loops.py --file translate_input.json
```
* Nhấn **Enter**. Chúng ta cùng xem kết quả.
![Looping over JSON](/images/9-loop/9.3-list-comprehensions/list-comprehensions-004.png?featherlight=false&width=90pc)