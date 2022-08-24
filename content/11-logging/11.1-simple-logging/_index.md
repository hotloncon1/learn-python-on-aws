+++
title = "Simple Logging"
date = 2020
weight = 1
chapter = false
pre = "<b>11.1. </b>"
+++
#### Simple Logging

We will replace the **print()** statements, that send output to the console with **logging**, which sends the output to logs. Using **logging** allows us to return information about how the program is functioning. Using methods like **print()** allow us to return information to the user.

1. Create a new file called **lab_8_simple_logging.py**
* In the Cloud9 IDE, click on the **+** 
* Click **New File** to create a new file
![Add input validation](/images/11-logging/11.1-simple-logging/simple-logging-001.png?featherlight=false&width=90pc)
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
        "TargetLanguageCode":"fr"
        }
    ]
}
"""

json_input = json.loads(json_string)

# Defines two variables to store the language code from the input.
SourceLanguageCode = json_input['Input'][0]['SourceLanguageCode']
TargetLanguageCode = json_input['Input'][0]['TargetLanguageCode']

# The if statement checks to see if the language code is the same as the source code
if SourceLanguageCode == TargetLanguageCode:
    print("The SourceLanguageCode is the same as the TargetLanguageCode - stopping")
else:
    print("The Source Language and Target Language codes are different - proceeding")
```
![Add input validation](/images/11-logging/11.1-simple-logging/simple-logging-002.png?featherlight=false&width=90pc)
3. Press **Ctrl + s** shortcuts 
* In the **Filename** section, type ```lab_8_simple_logging.py```
* Click **Save**
![Add input validation](/images/11-logging/11.1-simple-logging/simple-logging-003.png?featherlight=false&width=90pc)
4. We have used **print()** to output the messages to the console. This is where we need to make changes to the code to add them to logs rather than output to the console.
* Modify **lab_8_simple_logging.py** as follows:
```
# Import logging
import logging
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

json_input = json.loads(json_string)

# Defines two variables to store the language code from the input.
SourceLanguageCode = json_input['Input'][0]['SourceLanguageCode']
TargetLanguageCode = json_input['Input'][0]['TargetLanguageCode']

# The if statement checks to see if the language code is the same as the source code
if SourceLanguageCode == TargetLanguageCode:
    logging.warning("The SourceLanguageCode is the same as the TargetLanguageCode - stopping") # This will print to the console as the default level is warning
else:
    logging.info("The Source Language and Target Language codes are different - proceeding") # This will not print to the console because it is lower than warning
```
* Save
![Add input validation](/images/11-logging/11.1-simple-logging/simple-logging-004.png?featherlight=false&width=90pc)
5. To run the program, enter the following command in the terminal:
```
python lab_8_simple_logging.py --file translate_input.json
```
* Press **Enter**. See the result
![Add input validation](/images/11-logging/11.1-simple-logging/simple-logging-005.png?featherlight=false&width=90pc)
{{% notice info %}} 
This should return nothing to the console. This is because by default the logging level is set to **logging.warning**. Because the code is correct, it does not generate a warning.
{{% /notice %}}
6. Modify **lab_8_simple_logging.py** as follows:
```
# Import logging
import logging
import json

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

# Defines two variables to store the language code from the input.
SourceLanguageCode = json_input['Input'][0]['SourceLanguageCode']
TargetLanguageCode = json_input['Input'][0]['TargetLanguageCode']

# The if statement checks to see if the language code is the same as the source code
if SourceLanguageCode == TargetLanguageCode:
    logging.warning("The SourceLanguageCode is the same as the TargetLanguageCode - stopping") # This will print to the console as the default level is warning
else:
    logging.info("The Source Language and Target Language codes are different - proceeding") # This will not print to the console because it is lower than warning
```
* Save
* To run the program, enter the following command in the terminal:
```
python lab_8_simple_logging.py --file translate_input.json
```
* Press **Enter**. See the result. We will see the **WARNING** log.
![Add input validation](/images/11-logging/11.1-simple-logging/simple-logging-006.png?featherlight=false&width=90pc)