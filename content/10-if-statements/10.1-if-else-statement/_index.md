+++
title = "The If - Else Statement"
date = 2020
weight = 1
chapter = false
pre = "<b>10.1. </b>"
+++

We will add some conditional tests, using the **if** statement. We will perform some input validation to make sure that the parameters provided are valid values that Amazon Translate will accept.

#### Equivalence

Sometimes we want to check if two values are equal. We cannot use the **=** as this is reserved for declaring a variable. To check if two values are equivalent you need to use the **==** sign.

Where two values are equal this will return a **True** and where they are not equal it will return **False**

1. We will test the **==** sign:
* Type or copy the following into the python interactive mode
```
SourceLanguageCode = "en"
TargetLanguageCode = "fr"
SourceLanguageCode == TargetLanguageCode
```
* Press **Enter**. **"en"** differs with **"fr"** so **SourceLanguageCode == TargetLanguageCode** will return **False**
![The If - Else Statement](/images/10-if-statements/10.1-if-else-statement/if-else-statement-001.png?featherlight=false&width=90pc)
2. Type or copy the following into the python interactive mode
```
SourceLanguageCode = "fr"
TargetLanguageCode = "fr"
SourceLanguageCode == TargetLanguageCode
```
* Press **Enter**. **"fr"** and **"fr"** are equivalent so **SourceLanguageCode == TargetLanguageCode** will return **True**
![The If - Else Statement](/images/10-if-statements/10.1-if-else-statement/if-else-statement-002.png?featherlight=false&width=90pc)
{{% notice note %}} 
We can use **ctrl + d** or **exit()** to exit from the interactive python session.
{{% /notice %}}
3. We will the **if** statement to prevent an error where you try to translate from **"en"** to **"en"**.
* In the Cloud9 IDE, click on the **+** 
* Click **New File** to create a new file
![The If - Else Statement](/images/10-if-statements/10.1-if-else-statement/if-else-statement-003.png?featherlight=false&width=90pc)
4. In the editor add the following:
```
import json

# This uses a json string as an input 
json_string = """
{
    "Input":[
        {
        "Text":"I am learning to code in AWS",
        "SourceLanguageCode":"en",
        "TargetLanguageCode":"fr"
        }
    ]
}
"""

json_input = json.loads(json_string) # We use loads as we are loading from a string.

# Defines two variables to store the language code from the input.
SourceLanguageCode = json_input['Input'][0]['SourceLanguageCode']
TargetLanguageCode = json_input['Input'][0]['TargetLanguageCode']

# The if statement checks to see if the language code is the same as the source code
if SourceLanguageCode == TargetLanguageCode:
    print("The SourceLanguageCode is the same as the TargetLanguageCode - stopping")
else:
    print("The Source Language and Target Language codes are different - proceeding")
```
![The If - Else Statement](/images/10-if-statements/10.1-if-else-statement/if-else-statement-004.png?featherlight=false&width=90pc)
5. Press **Ctrl + s** shortcuts 
* In the **Filename** section, type ```lab_7_equivalence.py```
* Click **Save**
![The If - Else Statement](/images/10-if-statements/10.1-if-else-statement/if-else-statement-005.png?featherlight=false&width=90pc)
6. To exit from the interactive python session, we type or copy ```exit()``` the python interactive mode
* Press **Enter**
* To run the program, enter the following command in the terminal:
```
python lab_7_equivalence.py
```
* Press **Enter**
![The If - Else Statement](/images/10-if-statements/10.1-if-else-statement/if-else-statement-006.png?featherlight=false&width=90pc)
7. Modify **lab_7_equivalence.py** as follows:
```
import json

# This uses a json string as an input 
json_string = """
{
    "Input":[
        {
        "Text":"I am learning to code in AWS",
        "SourceLanguageCode":"fr",
        "TargetLanguageCode":"fr"
        }
    ]
}
"""

json_input = json.loads(json_string) # We use loads as we are loading from a string.

# Defines two variables to store the language code from the input.
SourceLanguageCode = json_input['Input'][0]['SourceLanguageCode']
TargetLanguageCode = json_input['Input'][0]['TargetLanguageCode']

# The if statement checks to see if the language code is the same as the source code
if SourceLanguageCode == TargetLanguageCode:
    print("The SourceLanguageCode is the same as the TargetLanguageCode - stopping")
else:
    print("The Source Language and Target Language codes are different - proceeding")
```
* Save.
![The If - Else Statement](/images/10-if-statements/10.1-if-else-statement/if-else-statement-007.png?featherlight=false&width=90pc)
8. To run the program, enter the following command in the terminal:
```
python lab_7_equivalence.py
```
* Press **Enter**. We will see the **if** statement to prevent an error where you try to translate from **"fr"** to **"fr"**
![The If - Else Statement](/images/10-if-statements/10.1-if-else-statement/if-else-statement-008.png?featherlight=false&width=90pc)

#### Operators

When using if statements you will often be using different operators to determine equivalence. Here are some of the operators that python supports

| Python | Meaning                     |
| ------ | --------------------------- |
| ==     | is equivalent to            |
| !=     | is not equivalent to        |
| >      | is greater than             |
| <      | is less than                |
| >=     | is equal to or greater than |
| <=     | is equal to or less than    |