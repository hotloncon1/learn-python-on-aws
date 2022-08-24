+++
title = "Simple Function"
date = 2020
weight = 1
chapter = false
pre = "<b>6.1. </b>"
+++
#### Simple Function

In python we can declare a function using the syntax: ```def function_name():```

A function begins with **def**, has a name in lower case, with words separated by underscores to improve readability, a set of **()** which contain parameters (more on this later) and ends in **:**.

#### Create A Simple Function
1. In the top section of the Cloud9 IDE.
* Click on the **+** 
* Click **New File** to create a new file
![Simple Function](/images/6-functions/6.1-simple-function/simple-function-001.png?featherlight=false&width=90pc)
2. In the editor add the following:
```
# A function that prints hello world
def hello_world():
    print('hello world')

# This line calls (runs) the function
hello_world()
```
![Simple Function](/images/6-functions/6.1-simple-function/simple-function-002.png?featherlight=false&width=90pc)
3. Press **Ctrl + s** shortcuts 
* In the **Filename** section, type ```lab_1_hello_world.py```
{{% notice info %}} 
The py on the end denotes that it is a python file.
{{% /notice %}}
* Click **Save**
![Simple Function](/images/6-functions/6.1-simple-function/simple-function-003.png?featherlight=false&width=90pc)
4. To run the program, enter the following command in the terminal:
```
python lab_1_hello_world.py
```
* Press **Enter**
![Simple Function](/images/6-functions/6.1-simple-function/simple-function-004.png?featherlight=false&width=90pc)

#### Returning information from a function

When a function performs some kind of activity, by default the information it remains contained within the boundary of the function. To pass the information to other parts of your code, you need to use **return**. The value the function returns is called the **return value** and it is passed back to the line which called the function.

5. Modify **lab_1_hello_world.py** as follows:
```
# A function that returns hello world
def hello_world():
    return 'hello world'

# Assign the hello_world() function to a variable.
greeting = hello_world()
print(greeting)
```
* Save.
![Simple Function](/images/6-functions/6.1-simple-function/simple-function-005.png?featherlight=false&width=90pc)