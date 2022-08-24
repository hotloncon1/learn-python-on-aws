+++
title = "Boto3"
date = 2020
weight = 2
chapter = false
pre = "<b>6.2. </b>"
+++
#### Boto3

We are going to use Amazon Translate to translate some text from English to French.

First, look at the [Boto3 documentation for Amazon Translate](https://boto3.amazonaws.com/v1/documentation/api/latest/reference/services/translate.html)

In the section marked [client](https://boto3.amazonaws.com/v1/documentation/api/latest/reference/services/translate.html#id11), it tells us how to use the translate service in our program.

In the Boto3 documentation for AWS Translate, we can see that it supports different methods. You can explore each of these if you wish. We are going to be using the [translate_text()](https://boto3.amazonaws.com/v1/documentation/api/latest/reference/services/translate.html#id11) method in our program.

In the translate text method, the documentation starts with **translate_text(\*\*kwargs)** and then further down has a section with the title **Request Syntax**. The request syntax is as follows:
```
response = client.translate_text(
    Text='string',
    TerminologyNames=[
        'string',
    ],
    SourceLanguageCode='string',
    TargetLanguageCode='string'
)
```

With these pieces of information we can build our python function. In a python function the **()** at the end, prior to the **:** is used to provide parameters which are inputs to your function.

In Boto3 the methods use **(\*\*kwargs)**. In python, this indicates that the function will accept an arbitrary number of keyword arguments. We will come back to the use of **kwargs** later.

Reading the documentation you will see that **translate_text()** has three **[REQUIRED]** inputs and one optional input.
* **Text** - **REQUIRED**
* **TerminologyNames** - this is optional because it is not shown as required
* **SourceLanguageCode** - **REQUIRED**
* **TargetLanguageCode** - **REQUIRED**

All of these are the type **String**, with the exception of **TerminologyNames**, which is a **list** containing comma separated values of the type **String**. For now, to simplify our function further we are going to remove the **TerminologyNames**, which is not required and provide hard coded values to our variables.

The **SourceLanguageCode** and **TargetLanguageCode** are listed in the [documentation](https://boto3.amazonaws.com/v1/documentation/api/latest/reference/services/translate.html#id11)

1. We will be using **English** and **French**, with the codes **en** and **fr**.
* Click on the **+** 
* Click **New File** to create a new file
![Boto3](/images/6-functions/6.2-boto3/boto3-001.png?featherlight=false&width=90pc)
2. In the editor add the following:
```
import boto3

client = boto3.client('translate')

#### Add the new text below this line ####

def translate_text(): # declare the function using def, name, braces for parameters and a colon  
    response = client.translate_text(
        Text='I am learning to code in AWS', # Assigning the value of the string to the variable Text
        SourceLanguageCode='en', # We are using a two letter language code from the documentation (en = English)
        TargetLanguageCode='fr' # We use a second two letter language code from the documentation (fr = French)
    )
```
{{% notice info %}} 
When something new is introduced the code is marked up with comments, subsequently to keep the program looking clean the comment will be removed. In python, anything following the **'#'** will be a comment and ignored by python.\
First, we need to tell python to use the boto3 package we installed using pip in the python packages section of the workshop. This is done using the **import boto3** statement.\
Second, we need to tell python which specific service we want to use within the boto3 package. This is done with **client = boto3.client('translate')**.
{{% /notice %}}
![Boto3](/images/6-functions/6.2-boto3/boto3-002.png?featherlight=false&width=90pc)
3. Press **Ctrl + s** shortcuts.
* In the **Filename** section, type ```lab_2_intro_to_boto3.py```
* Click **Save**
![Boto3](/images/6-functions/6.2-boto3/boto3-003.png?featherlight=false&width=90pc)
4. We have built our function and assigned values to our variables, we need to tell python to run the function and to output the response so we can see it.
* Modify the **lab_2_intro_to_boto3.py** file as follows:
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
* Press **Ctrl + s** shortcuts to save.
![Boto3](/images/6-functions/6.2-boto3/boto3-004.png?featherlight=false&width=90pc)
5. To run the program, enter the following command in the terminal:
```
python lab_2_intro_to_boto3.py
```
* Press **Enter**. We will see the result.
![Boto3](/images/6-functions/6.2-boto3/boto3-005.png?featherlight=false&width=90pc)

If you refer to the documentation, it will show the following:
```
Return type
    dict

Returns
    Response Syntax

    {
        'TranslatedText': 'string',
        'SourceLanguageCode': 'string',
        'TargetLanguageCode': 'string',
        'AppliedTerminologies': [
            {
                'Name': 'string',
                'Terms': [
                    {
                        'SourceText': 'string',
                        'TargetText': 'string'
                    },
                ]
            },
        ]
    }
```

This is telling us that AWS is returning data as a dictionary with a specific syntax.

Compare what has been returned from your program with the structure in the documentation. You will see that it follows the structure outlined in the documentation plus some metadata from the AWS service. This format is not easy for a human to read but it is a format used to exchange information between programs and modules. In a later lab we will find out how to extract data from this structure to present it in a format that is easier for humans to read.

If you look at the TranslatedText value, you should see **"J'apprends à coder dans AWS"**. This is the french text returned by Amazon Translate. You have just written your first python program that uses AWS. You have already learned some key concepts about variables and functions.