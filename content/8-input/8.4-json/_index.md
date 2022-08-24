+++
title = "JSON"
date = 2020
weight = 4
chapter = false
pre = "<b>8.4. </b>"
+++
#### JSON
[**JSON**](https://www.json.org/json-en.html) stands for Javascript Object Notation and is pronounced "jason". It is a very similar structure to python dictionaries and lists, with only a few exceptions. It is a very common format for computer programs to exchange information in using Application Programming Interfaces (APIs).

When we convert Python to JSON there is some conversion that takes place. The mapping is shown below:

| Python | JSON |
| ------ | ----------- |
| dict   | object |
| list,tuple   | array |
| str   | string |
| int, float   | number |
| True   | true |
| False   | false |
| None   | null |

For this reason, we need to use the json package to perform the conversion. The json package is a standard python package so there is no need to install it with pip.

#### json.loads() & json.dumps()

Before we use an external file it is worth spending time learning about **json.loads()** and **json.dumps()**. These two methods use JSON strings, denoted by the **'s'**. When learning to manipulate JSON it is easy to get confused between **json.loads()** and **json.load()** or **json.dumps()** and **json.dump()**.

Here is the easy way to know which to use.
* **json.load()** & **json.dump()** - Use to input and output JSON from files and into files.
* **json.loads()** & **json.dumps()** - Use to input and outputting JSON from strings and into strings.

1. Create a new file called **lab_5_json_input.py**
* Click on the **+** 
* Click **New File** to create a new file
![JSON](/images/8-input/8.4-json/json-001.png?featherlight=false&width=90pc)
2. In the editor add the following:
```
import json

# This uses a json string as an input 

json_string = """
{
    "Input":[
        {
        "Text":"I am learning to code in AWS",
        "SourceLanguageCode":"en",
        "TargetLanguageCode":"fr",
        "Required": true
        }
    ]
}
"""

def main():
    json_input = json.loads(json_string)
    print(json_input)

if __name__=="__main__":
    main()
```
{{% notice info %}} 
The parameters should by now look familiar as our inputs to the Amazon Translate service, with the addition of an extra parameter, **"Required": true**. This is just for illustration, and we will remove it in a moment.
{{% /notice %}}
![JSON](/images/8-input/8.4-json/json-002.png?featherlight=false&width=90pc)
3. Press **Ctrl + s** shortcuts.
* In the **Filename** section, type ```lab_5_json_input.py```
* Click **Save**
![JSON](/images/8-input/8.4-json/json-003.png?featherlight=false&width=90pc)
4. To run the program, enter the following command in the terminal:
```
python lab_5_json_input.py
```
* Press **Enter**. We will see the result.
![JSON](/images/8-input/8.4-json/json-004.png?featherlight=false&width=90pc)

{{% notice note %}} 
The parameters should by now look familiar as our inputs to the Amazon Translate service, with the addition of an extra parameter, **"Required": true**. This is just for illustration, and we will remove it in a moment.
{{% /notice %}}
5. This format is not easy to read, but we can get python to provide the same formatting of indentation as our original string that we passed in as the variable **json_string**. To do this we are going to use **json.dumps()** but with an added parameter to format the string with indentation.
* Modify the file called **lab_5_json_input.py** as follows:
```
import json

# This uses a json string as an input 

json_string = """
{
    "Input":[
        {
        "Text":"I am learning to code in AWS",
        "SourceLanguageCode":"en",
        "TargetLanguageCode":"fr",
        "Required": true
        }
    ]
}
"""

def main():
    json_input = json.loads(json_string)
    indented_format = json.dumps(json_input, indent=2)
    print(indented_format)

if __name__=="__main__":
    main()
```
* Save
![JSON](/images/8-input/8.4-json/json-005.png?featherlight=false&width=90pc)
6. To run the program, enter the following command in the terminal:
```
python lab_5_json_input.py
```
* Press **Enter**. We will see the result. We added additional formatting using **indent = 2** to make the JSON easier to read.
![JSON](/images/8-input/8.4-json/json-006.png?featherlight=false&width=90pc)

#### Navigating a JSON Structure

Learning to navigate a JSON structure to use the information you need is probably one of the most fundamental lessons you will learn when using python with AWS.

If you look at the structure above you can see that it comprises a dictionary with a key of "Input" and a value of a list containing another dictionary. This is called nesting. It is very common to have dictionaries which contain lists, which contain dictionaries. This structure can keep being nested, so you need to learn how to navigate it.

7. Modify the file called **lab_5_json_input.py** as follows:
```
import json

# This uses a json string as an input 

json_string = """
{
    "Input":[
        {
        "Text":"I am learning to code in AWS",
        "SourceLanguageCode":"en",
        "TargetLanguageCode":"fr",
        "Required": true
        }
    ]
}
"""
# Modify below this line
def main():
    json_input = json.loads(json_string)
    text = json_input['Input'][0]['Text']
    source_language_code = json_input['Input'][0]['SourceLanguageCode']
    target_language_code = json_input['Input'][0]['TargetLanguageCode']
    print(text, source_language_code, target_language_code)

if __name__=="__main__":
    main()
```
{{% notice info %}} 
We will see the navigating the JSON structure:\
First, because the JSON is in the variable **json_input** we used this as our first reference.\
Next, the first dictionary key is **"Input"** so this is placed in [] as **['Input']**.\
Next, in our structure is a list. A list uses an index, and the index starts at 0 for our first item. So to get the first item we use **[0]**.\
Next we want to get the values for **"Text"**,**"SourceLanguageCode"** and **"TargetLanguageCode"**.
{{% /notice %}}
* Save
![JSON](/images/8-input/8.4-json/json-007.png?featherlight=false&width=90pc)
8. To run the program, enter the following command in the terminal:
```
python lab_5_json_input.py
```
* Press **Enter**. We will see the result.
![JSON](/images/8-input/8.4-json/json-008.png?featherlight=false&width=90pc)

#### json.load() & json.dump()

9. We will create a file called **translate_input.json** with some JSON data that we will use for the Amazon Translate service to use.
* Click on the **+** 
* Click **New File** to create a new file
![JSON](/images/8-input/8.4-json/json-009.png?featherlight=false&width=90pc)
10. In the editor add the following:
```
{
    "Input":[
        {
        "Text":"I am learning to code in AWS",
        "SourceLanguageCode":"en",
        "TargetLanguageCode":"fr"
        }
    ]
}
```
![JSON](/images/8-input/8.4-json/json-010.png?featherlight=false&width=90pc)
11. Press **Ctrl + s** shortcuts.
* In the **Filename** section, type ```translate_input.json```
* Click **Save**
![JSON](/images/8-input/8.4-json/json-011.png?featherlight=false&width=90pc)
12. Open the file call **lab_5_json_input.py**
* Modify the file called **lab_5_json_input.py** as follows:
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
    with open(args.filename) as file_object:
        contents = json.load(file_object)
        return contents['Input'][0]

def translate_text(**kwargs): 
    client = boto3.client('translate')
    response = client.translate_text(**kwargs)
    print(response) 

# Main Function - use to call other functions
def main():
    kwargs = open_input()
    translate_text(**kwargs)

if __name__ == "__main__":
    main()
```
* Save
![JSON](/images/8-input/8.4-json/json-012.png?featherlight=false&width=90pc)
13. To run the program, enter the following command in the terminal:
```
python lab_5_json_input.py --file translate_input.json
```
* Press **Enter**. We will see the result.
![JSON](/images/8-input/8.4-json/json-013.png?featherlight=false&width=90pc)

We used **json.loads()** and **json.dumps()** to manipulate JSON strings.