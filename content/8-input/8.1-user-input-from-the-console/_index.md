+++
title = "User input from the console"
date = 2020
weight = 1
chapter = false
pre = "<b>8.1. </b>"
+++
#### User input from the console

In this section, we learn how to provide user input when the program is run and pass this to the function.

1. Create a new file called **lab_5_console_input.py**
* Click on the **+** 
* Click **New File** to create a new file
![User input from the console](/images/8-input/8.1-user-input-from-the-console/user-input-from-the-console-001.png?featherlight=false&width=90pc)
2. In the editor add the following:
```
import boto3

def translate_text(**kwargs): 
    client = boto3.client('translate')
    response = client.translate_text(**kwargs)
    print(response) 

### Change below this line only ###

kwargs={
    "Text":"I am learning to code in AWS",
    "SourceLanguageCode":"en",
    "TargetLanguageCode":"fr"
    }

def main():
    translate_text(**kwargs)

if __name__=="__main__":
    main()
```
![User input from the console](/images/8-input/8.1-user-input-from-the-console/user-input-from-the-console-002.png?featherlight=false&width=90pc)
3. Press **Ctrl + s** shortcuts.
* In the **Filename** section, type ```lab_5_console_input.py```
* Click **Save**
![User input from the console](/images/8-input/8.1-user-input-from-the-console/user-input-from-the-console-003.png?featherlight=false&width=90pc)
4. To pass input to our function when we run the file called **lab_5_console_input.py**, we need to use a built-in function called **input()**. This will prompt the user with a message and then wait for them to provide input.
* Modify the file called **lab_5_console_input.py** as follows:
```
import boto3

def translate_text(**kwargs): 
    client = boto3.client('translate')
    response = client.translate_text(**kwargs)
    print(response) 

### Change below this line only ###

text = input("Provide the text you want translating: ")
source_language_code = input("Provide the two letter source language code: ")
target_language_code = input("Provide the two letter target language code: ") 

def main():
    translate_text(
        Text=text,
        SourceLanguageCode=source_language_code,
        TargetLanguageCode=target_language_code
        )

if __name__=="__main__":
    main()
```
* Save
![User input from the console](/images/8-input/8.1-user-input-from-the-console/user-input-from-the-console-004.png?featherlight=false&width=90pc)
5. To run the program, enter the following command in the terminal:
```
python lab_5_console_input.py
```
* Press **Enter**.
* In the line **Provide the text you want translating:**, input ```I am learning to code in AWS``` and press **Enter**
* In the line **Provide the two letter source language code:**, input ```en``` and press **Enter**
* In the line **Provide the two letter target language code:**, input ```fr``` and press **Enter**
{{% notice info %}} 
The program will wait for you to provide a value before asking for the next prompt.
{{% /notice %}}