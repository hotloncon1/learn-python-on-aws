+++
title = "Log Level and Log File"
date = 2020
weight = 2
chapter = false
pre = "<b>11.2. </b>"
+++
#### Log Level and Log File

The default logging level is set at warning. This can be changed so that we capture more or less information in the log files.

We are going to change the default log level and save our output into a local log file on the Cloud9 instance. This is done by adding the following line to configure the logging level:
```
logging.basicConfig(filename='example.log',level=logging.DEBUG)
```

1. Create a new file called **lab_8_log_level.py**
* In the Cloud9 IDE, click on the **+** 
* Click **New File** to create a new file
![Log Level and Log File](/images/11-logging/11.2-log-level-and-log-file/log-level-and-log-file-001.png?featherlight=false&width=90pc)
2. In the editor add the following:
```
# Import logging
import logging
import json

# Set the log level in the basic configuration.  This means we will capture all our log entries and not just those at Warning or above.
logging.basicConfig(filename='example.log',level=logging.DEBUG)

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
![Log Level and Log File](/images/11-logging/11.2-log-level-and-log-file/log-level-and-log-file-002.png?featherlight=false&width=90pc)
3. Press **Ctrl + s** shortcuts 
* In the **Filename** section, type ```lab_8_log_level.py```
* Click **Save**
![Log Level and Log File](/images/11-logging/11.2-log-level-and-log-file/log-level-and-log-file-003.png?featherlight=false&width=90pc)
4. To run the program, enter the following command in the terminal:
```
python lab_8_log_level.py
```
* Press **Enter**. We will see the **example.log** file was created
![Log Level and Log File](/images/11-logging/11.2-log-level-and-log-file/log-level-and-log-file-004.png?featherlight=false&width=90pc)
5. Open the **example.log** file to see the logs
![Log Level and Log File](/images/11-logging/11.2-log-level-and-log-file/log-level-and-log-file-005.png?featherlight=false&width=90pc)
6. Open the **lab_8_log_level.py** file
* Modify **lab_8_log_level.py** as follows:
```
# Import logging
import logging
import json

# Set the log level in the basic configuration.  This means we will capture all our log entries and not just those at Warning or above.
logging.basicConfig(filename='example.log',level=logging.DEBUG)

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
python lab_8_log_level.py
```
* Press **Enter**.
![Log Level and Log File](/images/11-logging/11.2-log-level-and-log-file/log-level-and-log-file-006.png?featherlight=false&width=90pc)
7. Open the **example.log** file to see all the logs
![Log Level and Log File](/images/11-logging/11.2-log-level-and-log-file/log-level-and-log-file-007.png?featherlight=false&width=90pc)