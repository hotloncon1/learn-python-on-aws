+++
title = "Looping over JSON"
date = 2020
weight = 2
chapter = false
pre = "<b>9.2. </b>"
+++
#### Looping over Dictionaries and JSON

1. Open the file called **translate_input.json**
* Modify the **translate_input.json** file as follows:
```
{
    "Input":[
        {
        "Text":"What is cloud computing?",
        "SourceLanguageCode":"en",
        "TargetLanguageCode":"fr"
        },
        {
        "Text":"Cloud computing is the on-demand delivery of IT resources over the Internet with pay-as-you-go pricing.",
        "SourceLanguageCode":"en",
        "TargetLanguageCode":"fr"
        },
        {
        "Text":"Instead of buying, owning, and maintaining physical data centers and servers, you can access technology services, such as computing power, storage, and databases, on an as-needed basis from a cloud provider like Amazon Web Services (AWS)",
        "SourceLanguageCode":"en",
        "TargetLanguageCode":"fr"
        },
        {       
        "Text":"Who is using cloud computing?",
        "SourceLanguageCode":"en",
        "TargetLanguageCode":"fr"
        },
        {       
        "Text":"Organizations of every type, size, and industry are using the cloud for a wide variety of use cases, such as data backup, disaster recovery, email, virtual desktops, software development and testing, big data analytics, and customer-facing web applications.",
        "SourceLanguageCode":"en",
        "TargetLanguageCode":"fr"
        },
        {       
        "Text":"For example, healthcare companies are using the cloud to develop more personalized treatments for patients. Financial services companies are using the cloud to power real-time fraud detection and prevention.",
        "SourceLanguageCode":"en",
        "TargetLanguageCode":"fr"
        },        
        {       
        "Text":"And video game makers are using the cloud to deliver online games to millions of players around the world.",
        "SourceLanguageCode":"en",
        "TargetLanguageCode":"fr"
        }
    ] 
} 
```
* Save
![Looping over JSON](/images/9-loop/9.2-looping-over-json/looping-over-json-001.png?featherlight=false&width=90pc)
2. Create a new file called **lab_6_loops.py**
* Click on the **+** 
* Click **New File** to create a new file
![Looping over JSON](/images/9-loop/9.2-looping-over-json/looping-over-json-002.png?featherlight=false&width=90pc)
3. In the editor add the following:
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
    required=True)

args = parser.parse_args()

# Functions
def open_input():
    """This function returns a dictionary containing the contents of the Input section in the input file""" 
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
    for item in input_text: # Here we iterate over all dictionaries in the Input list
        translate_text(**item)

# Main Function - use to call other functions
def main():
    translate_loop()

if __name__ == "__main__":
    main()
```
![Looping over JSON](/images/9-loop/9.2-looping-over-json/looping-over-json-003.png?featherlight=false&width=90pc)
4. Press **Ctrl + s** shortcuts.
* In the **Filename** section, type ```lab_6_loops.py```
* Click **Save**
![Looping over JSON](/images/9-loop/9.2-looping-over-json/looping-over-json-004.png?featherlight=false&width=90pc)
5. To run the program, enter the following command in the terminal:
```
python lab_6_loops.py --file translate_input.json
```
* Press **Enter**. We will see the result.
![Looping over JSON](/images/9-loop/9.2-looping-over-json/looping-over-json-005.png?featherlight=false&width=90pc)