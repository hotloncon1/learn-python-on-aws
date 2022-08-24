+++
title = "CLI Arguments"
date = 2020
weight = 2
chapter = false
pre = "<b>4.2. </b>"
+++
#### CLI Arguments

In the previous section, we were able to prompt a user for input. This is useful for human input, but more often in AWS we want to automate our workflow, which means we need a method of passing parameters via the **Command Line Interface (CLI)**

1. Create a new file called **lab_5_cli_arguments.py**
* Click on the **+** 
* Click **New File** to create a new file
![CLI Arguments](/images/8-input/8.2-cli-arguments/cli-arguments-001.png?featherlight=false&width=90pc)
2. In the editor add the following:
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
![CLI Arguments](/images/8-input/8.2-cli-arguments/cli-arguments-002.png?featherlight=false&width=90pc)
3. Press **Ctrl + s** shortcuts.
* In the **Filename** section, type ```lab_5_cli_arguments.py```
* Click **Save**
![CLI Arguments](/images/8-input/8.2-cli-arguments/cli-arguments-003.png?featherlight=false&width=90pc)
4. We will use argparse to input arguments from the CLI
* Modify the file called **lab_5_cli_arguments.py** as follows:
```
import argparse # argparse is a built in python package, we add it with an import statement
import boto3

# Define the parser variable to equal argparse.ArgumentParser()
parser = argparse.ArgumentParser(description="Provides translation between one source language and another of the same set of languages.")

# Add each of the arguments using the parser.add_argument() method
parser.add_argument(
    '--text',
    dest="Text",
    type=str,
    help="The text to translate. The text string can be a maximum of 5,000 bytes long. Depending on your character set, this may be fewer than 5,000 characters",
    required=True
    )

parser.add_argument(
    '--source-language-code', 
    dest="SourceLanguageCode", 
    type=str, 
    help="The language code for the language of the source text. The language must be a language supported by Amazon Translate.",
    required=True
    )

parser.add_argument(
    '--target-language-code',
    dest="TargetLanguageCode",
    type=str,
    help="The language code requested for the language of the target text. The language must be a language support by Amazon Translate.",
    required=True
    )

# This will inspect the command line, convert each argument to the appropriate type and then invoke the appropriate action.
args = parser.parse_args()

def translate_text(**kwargs): 
    client = boto3.client('translate')
    response = client.translate_text(**kwargs)
    print(response) 

def main():
    # vars() is an inbuilt function which returns a dictionary object
    translate_text(**vars(args))

if __name__=="__main__":
    main()
```
{{% notice info %}} 
We used **parser.add_argument()** to add each of the arguments.\
Argument name for example **\-\-text**.\
The dest is required to make it a value keyword argument accepted by the parameter, otherwise it will use the default argument **text="value"** which should be **Text="value"**\
**type** is the data type which in this case is a **string** (str).\
**help** is the help text shown.\
**args = parser.parse_args()** will inspect the command line, convert each argument to the appropriate type and then invoke the appropriate action.\
when we call the **translate_text()** function we need to use **\*\*vars(args)**. The **\*\*vars** turns our object created by **args = parser.parse_args()** into a dictionary object which we can pass as **key\\:value** pairs to our function
{{% /notice %}}
* Save
![CLI Arguments](/images/8-input/8.2-cli-arguments/cli-arguments-004.png?featherlight=false&width=90pc)
5. To run the program, enter the following command in the terminal:
```
python lab_5_cli_arguments.py --text "we are learning python on AWS" --source-language-code en --target-language-code fr
```
* Press **Enter**.
{{% notice info %}} 
We have added the parameters on the command line.\
Each parameter relates to each block for **parser.add_argument**.
{{% /notice %}}
![CLI Arguments](/images/8-input/8.2-cli-arguments/cli-arguments-005.png?featherlight=false&width=90pc)