+++
title = "Add input validation"
date = 2020
weight = 4
chapter = false
pre = "<b>10.4. </b>"
+++
#### Add input validation

We will add our input validation as a function, each of the **if-elif-else** statements will return **True** or **False** boolean values. We will add a call to the input validation function to the for loop in the **translate_loop()** function.

1. Create a new file called **lab_7_input_validation.py**
* In the Cloud9 IDE, click on the **+** 
* Click **New File** to create a new file
![Add input validation](/images/10-if-statements/10.4-add-input-validation/add-input-validation-001.png?featherlight=false&width=90pc)
2. In the editor add the following:
```
# Standard Imports
import argparse
import json

# 3rd Party Imports
import boto3

# Arguments
parser = argparse.ArgumentParser(description="Provides translation  between one source language and another of the same set of languages.")
parser.add_argument(
    '--file',
    dest='filename',
    help="The path to the input file. The file should be valid json",
    required=True
    )

args = parser.parse_args()

# Functions

# Open the input file to get the json.
def open_input():
    with open(args.filename) as file_object:
        contents = json.load(file_object)
        return contents['Input']

# Boto3 function to use Amazon Translate to translate the text and only return the Translated Text
def translate_text(**kwargs):
    client = boto3.client('translate')
    response = client.translate_text(**kwargs)
    print(response['TranslatedText'])

# Add a Loop to iterate over the json file.
def translate_loop():
    input_text = open_input()
    for item in input_text:
        if input_validation(item) == True:
            translate_text(**item)
        else:
            raise SystemError

# Add our input validation as a function here.
def input_validation(item):
    languages = ["af","sq","am","ar","az","bn","bs","bg","zh","zh-TW","hr","cs","da","fa-AF",
                "nl","en","et","fi","fr","fr-CA","ka","de","el","ha","he","hi","hu","id","it",
                "ja","ko","lv","ms","no","fa","ps","pl","pt","ro","ru","sr","sk","sl","so","es",
                "sw","sv","tl","ta","th","tr","uk","ur","vi"
                ]
    json_input=item
    SourceLanguageCode = json_input['SourceLanguageCode']
    TargetLanguageCode = json_input['TargetLanguageCode']

    if SourceLanguageCode == TargetLanguageCode:
        print("The SourceLanguageCode is the same as the TargetLanguageCode - nothing to do")
        return False
    elif SourceLanguageCode not in languages and TargetLanguageCode not in languages:
        print("Neither the SourceLanguageCode and TargetLanguageCode are valid - stopping")
        return False
    elif SourceLanguageCode not in languages:
        print("The SourceLanguageCode is not valid - stopping")
        return False
    elif TargetLanguageCode not in languages:
        print("The TargetLanguageCode is not valid - stopping")
        return False
    elif SourceLanguageCode in languages and TargetLanguageCode in languages:
        print("The SourceLanguageCode and TargetLanguageCode are valid - proceeding")
        return True
    else:
        print("There is an issue")
        return False

# Main Function - use to call other functions
def main():
    translate_loop()

if __name__ == "__main__":
    main()
```
![Add input validation](/images/10-if-statements/10.4-add-input-validation/add-input-validation-002.png?featherlight=false&width=90pc)
3. Press **Ctrl + s** shortcuts 
* In the **Filename** section, type ```lab_7_input_validation.py```
* Click **Save**
![Add input validation](/images/10-if-statements/10.4-add-input-validation/add-input-validation-003.png?featherlight=false&width=90pc)
4. To run the program, enter the following command in the terminal:
```
python lab_7_input_validation.py --file translate_input.json
```
* Press **Enter**. See the result
![Add input validation](/images/10-if-statements/10.4-add-input-validation/add-input-validation-004.png?featherlight=false&width=90pc)