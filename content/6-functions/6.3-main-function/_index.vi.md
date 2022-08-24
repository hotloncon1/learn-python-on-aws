+++
title = "Hàm main()"
date = 2020
weight = 3
chapter = false
pre = "<b>6.3. </b>"
+++
#### Hàm main()

Trong phần 6.2, Chúng ta đã gọi hàm **translate_text()** bằng dòng **translate_text()**. Chúng ta có thể xem lại dưới đây
```

import boto3

client = boto3.client('translate')

def translate_text(): 
    response = client.translate_text(
        Text='I am learning to code in AWS', 
        SourceLanguageCode='en', 
        TargetLanguageCode='fr' 
    )
#### Add the new text below this line ####
    print(response) # this code is inside the function and will print the contents of the variable 'response' 

translate_text() # This line will call our function. Without it, python will not do anything.
```
Khi mã này được chạy, trình thông dịch sẽ xác định một biến đặc biệt gọi là **\_\_name\_\_** và được gán giá trị của **"\_\_main\_\_"** trong code của file python này. Vì vậy, mã trong tệp python của chúng ta trở thành **\_\_name\_\_ == "\_\_main\_\_"**.

When we use import statements, we can import code from other files into our python program. When this happens, the imported code is set a **\_\_name\_\_** value of the modules name.

By setting the **\_\_name\_\_=="\_\_main\_\_"** we can control the order in which the code in this file is executed, telling python to run the code in this file which has the name of **\_\_main\_\_** rather than the code imported from another file. This avoids situations where your code could run an imported script, resulting in unwanted behavior.

We do this using an if statement. **If** statements are covered in more detail later. At this stage, all you need to understand is that it is telling the python interpreter that if the **\_\_name\_\_** is equal to **\_\_main\_\_** which relates to the code in this python file, then run the **main()** function.

The **main()** function therefore sets the start point for our code to control the order in which our code executes. It is conventional to include all the calls to your functions within the **main()** function. This will help others to read your code and understand the logic and flow.

1. Chúng ta sẽ sử dụng hàm **main()** trong file python tiếp theo.
* Click **+** 
* Click **New File**
![The main() function](/images/6-functions/6.3-main-function/main-function-001.png?featherlight=false&width=90pc)
2. Trong phần code editor, thêm nội dung dưới đây:
```
import boto3

client = boto3.client('translate')

def translate_text():
    response = client.translate_text(
        Text='I am learning to code in AWS',
        SourceLanguageCode='en',
        TargetLanguageCode='fr'
    )
    print(response) # this code is inside the function and will print the contents of the variable 'response'

def main():
    translate_text()

if __name__=="__main__":
    main()
```
![The main() function](/images/6-functions/6.3-main-function/main-function-002.png?featherlight=false&width=90pc)
3. Nhấn tổ hợp phím **Ctrl + s**.
* Tại mục **Filename**, nhập ```lab_3_main_function.py```
* Click **Save**
![The main() function](/images/6-functions/6.3-main-function/main-function-003.png?featherlight=false&width=90pc)
4. Để chạy chương trình, nhập câu lệnh dưới đây vào terminal:
```
python lab_3_main_function.py
```
* Nhấn **Enter**. Chúng ta cùng xem kết quả.
![The main() function](/images/6-functions/6.3-main-function/main-function-004.png?featherlight=false&width=90pc)

Chủ đề này có thể gây nhầm lẫn. Nếu bạn đã cố gắng để hiểu những gì đang xảy ra ở đây, đừng lo lắng! Bạn sẽ thấy điều này được sử dụng trong suốt phần còn lại của bài lab này và bạn sẽ sớm bắt đầu nhận ra cách sử dụng nó.