+++
title = "Checking Values in a List"
date = 2020
weight = 2
chapter = false
pre = "<b>10.2. </b>"
+++
#### Checking Values in a List

Amazon Translate will only support a defined list of languages. The list of language codes that Amazon Translate will accept are provided in the [Developer Guide](https://docs.aws.amazon.com/translate/latest/dg/what-is.html). We can use an if statement to perform some input validation to check that the language code is in the list.

1. Create a new file called **lab_7_check_language.py**
* In the Cloud9 IDE, click on the **+** 
* Click **New File** to create a new file
![Checking Values in a List](/images/10-if-statements/10.2-checking-value-in-the-list/checking-value-in-the-list-001.png?featherlight=false&width=90pc)
2. In the editor add the following:
```
import json

# A defined list of languages supported by Amazon Translate
languages = ["af","sq","am","ar","az","bn","bs","bg","zh","zh-TW","hr","cs","da","fa-AF","nl","en","et","fi","fr","fr-CA","ka","de","el","ha","he","hi","hu","id","it","ja","ko","lv","ms","no","fa","ps","pl","pt","ro","ru","sr","sk","sl","so","es","sw","sv","tl","ta","th","tr","uk","ur","vi"]

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

json_input = json.loads(json_string)

# Extracts the SourceLanguageCode and TargetLanguageCode from the JSON
SourceLanguageCode = json_input['Input'][0]['SourceLanguageCode']
TargetLanguageCode = json_input['Input'][0]['TargetLanguageCode']

# Uses an if-else statement to check that the SourceLanguageCode is in the languages list.
if SourceLanguageCode in languages:
    print("The SourceLanguageCode is valid - proceeding")
else:
    print("The SourceLanguageCode is not valid - stopping")
```
![Checking Values in a List](/images/10-if-statements/10.2-checking-value-in-the-list/checking-value-in-the-list-002.png?featherlight=false&width=90pc)
3. Press **Ctrl + s** shortcuts 
* In the **Filename** section, type ```lab_7_check_language.py```
* Click **Save**
![Checking Values in a List](/images/10-if-statements/10.2-checking-value-in-the-list/checking-value-in-the-list-003.png?featherlight=false&width=90pc)
4. To run the program, enter the following command in the terminal:
```
python lab_7_check_language.py
```
* Press **Enter**. We will see the result
![Checking Values in a List](/images/10-if-statements/10.2-checking-value-in-the-list/checking-value-in-the-list-004.png?featherlight=false&width=90pc)
{{% notice info %}} 
We used the **if** statement combined with **in** to check if the language code for the source language is valid.
{{% /notice %}}