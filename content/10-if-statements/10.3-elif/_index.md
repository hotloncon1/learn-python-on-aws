+++
title = "Elif"
date = 2020
weight = 3
chapter = false
pre = "<b>10.3. </b>"
+++
#### Elif

The **and** statement is a logical operator that combines the check for both source language and target language. The **elif** statement allows us to introduce multiple different logical checks.

1. Create a new file called **lab_7_elif.py**
* In the Cloud9 IDE, click on the **+** 
* Click **New File** to create a new file
![Elif](/images/10-if-statements/10.3-elif/elif-001.png?featherlight=false&width=90pc)
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

SourceLanguageCode = json_input['Input'][0]['SourceLanguageCode']
TargetLanguageCode = json_input['Input'][0]['TargetLanguageCode']

# Uses an if-elif-else statements to check that the SourceLanguageCode is in the languages list.
if SourceLanguageCode == TargetLanguageCode:
    print("The SourceLanguageCode is the same as the TargetLanguageCode - nothing to do")
elif SourceLanguageCode not in languages and TargetLanguageCode not in languages:
    print("Neither the SourceLanguageCode and TargetLanguageCode are valid - stopping")
elif SourceLanguageCode not in languages:
    print("The SourceLanguageCode is not valid - stopping")
elif TargetLanguageCode not in languages:
    print("The TargetLanguageCode is not valid - stopping")
elif SourceLanguageCode in languages and TargetLanguageCode in languages:
    print("The SourceLanaguageCode and TargetLanguageCode are valid - proceeding")
else:
    print("There is an issue")
```
![Elif](/images/10-if-statements/10.3-elif/elif-002.png?featherlight=false&width=90pc)
3. Press **Ctrl + s** shortcuts 
* In the **Filename** section, type ```lab_7_elif.py```
* Click **Save**
![Elif](/images/10-if-statements/10.3-elif/elif-003.png?featherlight=false&width=90pc)
4. To run the program, enter the following command in the terminal:
```
python lab_7_elif.py
```
* Press **Enter**. See the result
![Elif](/images/10-if-statements/10.3-elif/elif-004.png?featherlight=false&width=90pc)
5. We will test the code by changing the values of the **SourceLanguageCode** and the **TargetLanguageCode**
* Make the **SourceLanguageCode** and **TargetLanguageCode** identical values. Modify **lab_7_elif.py** as follows:
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
        "TargetLanguageCode":"en"
        }
    ]
}
"""

json_input = json.loads(json_string)

SourceLanguageCode = json_input['Input'][0]['SourceLanguageCode']
TargetLanguageCode = json_input['Input'][0]['TargetLanguageCode']

# Uses an if-elif-else statements to check that the SourceLanguageCode is in the languages list.
if SourceLanguageCode == TargetLanguageCode:
    print("The SourceLanguageCode is the same as the TargetLanguageCode - nothing to do")
elif SourceLanguageCode not in languages and TargetLanguageCode not in languages:
    print("Neither the SourceLanguageCode and TargetLanguageCode are valid - stopping")
elif SourceLanguageCode not in languages:
    print("The SourceLanguageCode is not valid - stopping")
elif TargetLanguageCode not in languages:
    print("The TargetLanguageCode is not valid - stopping")
elif SourceLanguageCode in languages and TargetLanguageCode in languages:
    print("The SourceLanaguageCode and TargetLanguageCode are valid - proceeding")
else:
    print("There is an issue")
```
* Save
* To run the program, enter the following command in the terminal:
```
python lab_7_elif.py
```
* Press **Enter**. See the result
![Elif](/images/10-if-statements/10.3-elif/elif-005.png?featherlight=false&width=90pc)

Do the same making the **SourceLanguageCode** and **TargetLanguageCode** identical values, we test the following case and see the result:
* Change the **SourceLanguageCode** and **TargetLanguageCode** to different but not valid values.
* Change the **SourceLanguageCode** to a value not supported and **TargetLanguageCode** to a supported value.
* Change the **SourceLanguageCode** to a supported value and the **TargetLanguageCode** to a not supported value.
* Change both the **SourceLanguageCode** and **TargetLanguageCode** to supported but different values.