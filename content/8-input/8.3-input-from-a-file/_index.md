+++
title = "Input from a file"
date = 2020
weight = 3
chapter = false
pre = "<b>4.3. </b>"
+++
#### Input from a file

So far all our inputs have been provided either by a human interaction with the command prompt or via human configuration at the command line.

The **open** function is a built-in function. The [documentation](https://docs.python.org/3/library/functions.html#open) shows that there is an optional mode that can be passed in. we will pass in **r**. This indicates that the file is opened as read-only. To write to the file you need to use **w**.

To get input from an external file we use the format:
```
with open(filename, 'r' ) as variable_name:
    <Do something with the variable here>
```

1. Create a new file called **lab_5_input_text_file.py**
* Click on the **+** 
* Click **New File** to create a new file
![Dictionaries](/images/8-input/8.3-input-from-a-file/input-from-a-file-001.png?featherlight=false&width=90pc)
2. In the editor add the following:
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
3. Press **Ctrl + s** shortcuts.
* In the **Filename** section, type ```lab_5_input_text_file.py```
* Click **Save**
![Dictionaries](/images/8-input/8.3-input-from-a-file/input-from-a-file-003.png?featherlight=false&width=90pc)
4. Create a new file called **text.txt**
* Click on the **+** 
* Click **New File** to create a new file
![Dictionaries](/images/8-input/8.3-input-from-a-file/input-from-a-file-004.png?featherlight=false&width=90pc)
5. In the editor add the following:
```
"The Quick Brown Fox"
```
![Dictionaries](/images/8-input/8.3-input-from-a-file/input-from-a-file-005.png?featherlight=false&width=90pc)
6. Press **Ctrl + s** shortcuts.
* In the **Filename** section, type ```text.txt```
* Click **Save**
![Dictionaries](/images/8-input/8.3-input-from-a-file/input-from-a-file-006.png?featherlight=false&width=90pc)
7. To run the program, enter the following command in the terminal:
```
python lab_5_input_text_file.py
```
* Press **Enter**. We will see that it returns the text from **text.txt**
![Dictionaries](/images/8-input/8.3-input-from-a-file/input-from-a-file-007.png?featherlight=false&width=90pc)

We can now read input from a file.