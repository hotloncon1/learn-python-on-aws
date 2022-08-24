+++
title = "The main() function"
date = 2020
weight = 3
chapter = false
pre = "<b>6.3. </b>"
+++
#### The main() function

The **main()** function sets the entry point for a python program. A python program will run line by line, but it won't run the functions until it comes to a line which calls the function.

In the section 6.2, we called the **translate_text()** function by the line **translate_text()**. We can review this below.
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
When this code is run, the interpreter will define a special variable called **\_\_name\_\_** and assign the value of **"\_\_main\_\_"** to the code in this python file. So the code in our python file becomes **\_\_name\_\_ == "\_\_main\_\_"**.

When we use import statements, we can import code from other files into our python program. When this happens, the imported code is set a **\_\_name\_\_** value of the modules name.

By setting the **\_\_name\_\_=="\_\_main\_\_"** we can control the order in which the code in this file is executed, telling python to run the code in this file which has the name of **\_\_main\_\_** rather than the code imported from another file. This avoids situations where your code could run an imported script, resulting in unwanted behavior.

We do this using an if statement. **If** statements are covered in more detail later. At this stage, all you need to understand is that it is telling the python interpreter that if the **\_\_name\_\_** is equal to **\_\_main\_\_** which relates to the code in this python file, then run the **main()** function.

The **main()** function therefore sets the start point for our code to control the order in which our code executes. It is conventional to include all the calls to your functions within the **main()** function. This will help others to read your code and understand the logic and flow.

1. We will use the **main()** function in the next python file.
* Click on the **+** 
* Click **New File** to create a new file
![The main() function](/images/6-functions/6.3-main-function/main-function-001.png?featherlight=false&width=90pc)
2. In the editor add the following:
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
3. Press **Ctrl + s** shortcuts.
* In the **Filename** section, type ```lab_3_main_function.py```
* Click **Save**
![The main() function](/images/6-functions/6.3-main-function/main-function-003.png?featherlight=false&width=90pc)
4. To run the program, enter the following command in the terminal:
```
python lab_3_main_function.py
```
* Press **Enter**. We will see the result.
![The main() function](/images/6-functions/6.3-main-function/main-function-004.png?featherlight=false&width=90pc)

This topic can be confusing. If you have struggled to understand what is going on here, don't worry! You will see this used throughout the rest of the workshop and you will soon start to recognize how to use it, you can then return to this lab to refresh your understanding.