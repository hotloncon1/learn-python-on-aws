+++
title = "Biến"
weight = 3
chapter = false
pre = "<b>3. </b>"
+++
#### Biến

Biến (Variable) là một giá trị có thể thay đổi. Chúng có thể được sử dụng để lưu trữ thông tin có thể được tham chiếu và sử dụng bởi các chương trình. Thay vì sử dụng trực tiếp giá trị được lưu trữ, chúng ta có thể sử dụng biến để thay thế. Các biến có thể là một số thứ bất kỳ, chẳng hạn như một chuỗi văn bản, một danh sách hoặc một đối tượng. Sử dụng các biến làm cho code của chúng ta linh hoạt và có thể tái sử dụng. Nếu không có biến, chúng ta sẽ phải viết trực tiếp tất cả các giá trị vào (hardcode).

Tên biến được xác định khi bạn khai báo chúng. Quy ước cho tên biến được đặt ra trong [pep8](https://www.python.org/dev/peps/pep-0008/#function-and-variable-names) (hướng dẫn kiểu tên biến cho python). Chúng nên là chữ thường với các từ được phân tách bằng dấu gạch dưới.

Các biến trong python được khai báo ở định dạng ```name = value```. Trong python, chúng ta có thể lưu trữ các loại dữ liệu khác nhau mà không cần phải rõ ràng về loại của biến khi chúng ta khai báo.

Dưới đây là một vài ví dụ:

```
a_str = "This is an example of a string in quotes" # In python the word string is abbreviated to str
my_float = 5.5
an_integer = 5 # integer is abbreviated to int
shopping_list = ["apples", "oranges", "pears"]
a_dict = {"userId": "JBloggs"} # dictionary is abbreviated to dict
my_var = another_variable # variable is abbreviated to var
test_function = my_function() #function is abbreviated to func
example_tuple = ("apple", "orange", "pear")
boolean_values = True # boolean is abbreviated to bool
```