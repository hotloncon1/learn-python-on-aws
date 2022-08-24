+++
title = "Arguments and Parameters"
date = 2020
weight = 7
chapter = false
pre = "<b>7. </b>"
+++

Arguments are used to pass values between programs, subroutines or functions. When an argument is used to customize a program, it is called a parameter.
In other words, A parameter is a variable in a method definition. When a method is called, the arguments are the data you pass into the method's parameters.

#### Positional Arguments

The positional arguments, as the name suggests the order that the argument is passed to the function depends on order within the brackets **()**.

1. Create a new file called **lab_4_positional_arguments.py**
* Click on the **+** 
* Click **New File** to create a new file
![Arguments and Parameters](/images/7-arguments-and-parameters/arguments-and-parameters-001.png?featherlight=false&width=90pc)
2. In the editor add the following:
```
import boto3

def translate_text():
    client = boto3.client('translate')
    response = client.translate_text(
        Text='I am learning to code in AWS', 
        SourceLanguageCode='en', 
        TargetLanguageCode='fr' 
    )
    print(response) 

def main():
    translate_text()

if __name__=="__main__":
    main()
```
![Arguments and Parameters](/images/7-arguments-and-parameters/arguments-and-parameters-002.png?featherlight=false&width=90pc)
3. Press **Ctrl + s** shortcuts.
* In the **Filename** section, type ```lab_4_positional_arguments.py```
* Click **Save**
![Arguments and Parameters](/images/7-arguments-and-parameters/arguments-and-parameters-003.png?featherlight=false&width=90pc)
4. Amend the function so that we have some positional arguments and save:
```
import boto3

def translate_text(text, source_language_code, target_language_code): # we define the positional arguments in the ()
    client = boto3.client('translate')
    response = client.translate_text(
        Text=text, # we remove the hard coded value
        SourceLanguageCode=source_language_code, # we used the positional argument instead
        TargetLanguageCode=target_language_code
    )
    print(response) 

def main():
    translate_text('I am learning to code in AWS','en','fr') # we provide the value for the arguments when we call the function in the correct positional order.

if __name__=="__main__":
    main()
```
{{% notice info %}} 
The values: **'I am learning to code in AWS'**, **'en'**, **'fr'** are positional arguments were passed to the parameters: **text**, **source_language_code**, **target_language_code**.
{{% /notice %}}
* To run the program, enter the following command in the terminal:
```
python lab_4_positional_arguments.py
```
* Press **Enter**. We will see the result.
![Arguments and Parameters](/images/7-arguments-and-parameters/arguments-and-parameters-004.png?featherlight=false&width=90pc)

#### Keyword Arguments

A keyword argument is a name-value pair that is passed to the function. Here are some of the advantages:

* If the values passed with positional arguments are wrong, you will get an error or unexpected behavior. Keyword arguments can be passed in any order.
* When used with the **\*\*** we can pass an arbitrary number of keyword arguments.
* We can reduce the number of lines in our code.

5. Create a new file called **lab_4_keyword_arguments.py**
* Click on the **+** 
* Click **New File** to create a new file
![Arguments and Parameters](/images/7-arguments-and-parameters/arguments-and-parameters-005.png?featherlight=false&width=90pc)
6. In the editor add the following:
```
import boto3

def translate_text(text, source_language_code, target_language_code): 
    client = boto3.client('translate')
    response = client.translate_text(
        Text=text, 
        SourceLanguageCode=source_language_code, 
        TargetLanguageCode=target_language_code
    )
    print(response) 

def main():
    translate_text('I am learning to code in AWS','en','fr')

if __name__=="__main__":
    main()
```
![Arguments and Parameters](/images/7-arguments-and-parameters/arguments-and-parameters-006.png?featherlight=false&width=90pc)
7. Press **Ctrl + s** shortcuts.
* In the **Filename** section, type ```lab_4_keyword_arguments.py```
* Click **Save**
![Arguments and Parameters](/images/7-arguments-and-parameters/arguments-and-parameters-007.png?featherlight=false&width=90pc)
8. Modify the file called **lab_4_keyword_arguments.py** as follows:
```
import boto3

def translate_text(**kwargs): 
    client = boto3.client('translate')
    response = client.translate_text(**kwargs)
    print(response) 

def main():
    translate_text(Text='I am learning to code in AWS',SourceLanguageCode='en',TargetLanguageCode='fr')

if __name__=="__main__":
    main()
```
{{% notice info %}} 
We replaced the positional arguments with keyword arguments. This is done using the **\*\*kwargs**.\
We removed all the parameters such as **Text=text** which shortens our code and replaced it with **response = client.translate_text(\*\*kwargs)**.\
We defined the keyword arguments when we called the function using the syntax **Text='I am learning to code in AWS'**.
{{% /notice %}}
* Save
![Arguments and Parameters](/images/7-arguments-and-parameters/arguments-and-parameters-008.png?featherlight=false&width=90pc)
9. To run the program, enter the following command in the terminal:
```
python lab_4_keyword_arguments.py
```
* Press **Enter**. We will see the result.
![Arguments and Parameters](/images/7-arguments-and-parameters/arguments-and-parameters-009.png?featherlight=false&width=90pc)
10. We will swap the order of the keyword arguments around to see that there is any change.
* Modify the file called **lab_4_keyword_arguments.py** as follows:
```
import boto3

def translate_text(**kwargs): 
    client = boto3.client('translate')
    response = client.translate_text(**kwargs)
    print(response) 

def main():
    translate_text(SourceLanguageCode='en',Text='I am learning to code in AWS',TargetLanguageCode='fr')

if __name__=="__main__":
    main()
```
* Save
![Arguments and Parameters](/images/7-arguments-and-parameters/arguments-and-parameters-010.png?featherlight=false&width=90pc)
11. To run the program, enter the following command in the terminal:
```
python lab_4_keyword_arguments.py
```
* Press **Enter**. We should see the result. We will see the result doesn't have any change. We will see the keyword arguments don't depend on order within the brackets **()**.
![Arguments and Parameters](/images/7-arguments-and-parameters/arguments-and-parameters-011.png?featherlight=false&width=90pc)
12. We will use dictionaries as keyword arguments
* Modify the file called **lab_4_keyword_arguments.py** as follows:
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
{{% notice info %}} 
We defined a variable called kwargs containing a dictionary of **key\\:value** pairs.\
We replaced the keyword arguments when we called the function with **\*\*kwargs**. The **\*\*** tells python that it is an arbitrary number of arguments, **kwargs** is the function name we defined.
We put each **key\\:value** pair on a separate line to make it easy to read.
{{% /notice %}}
* Save
![Arguments and Parameters](/images/7-arguments-and-parameters/arguments-and-parameters-012.png?featherlight=false&width=90pc)
13. To run the program, enter the following command in the terminal:
```
python lab_4_keyword_arguments.py
```
* Press **Enter**. We should see the result.
![Arguments and Parameters](/images/7-arguments-and-parameters/arguments-and-parameters-013.png?featherlight=false&width=90pc)













