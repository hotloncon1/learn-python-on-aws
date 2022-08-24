+++
title = "Virtual Environments"
date = 2020
weight = 3
chapter = false
pre = "<b>2.3. </b>"
+++
#### Create a Virtual Environment

A virtual environment in python is a container in which all your code and other python packages reside. It allows you to keep your python configuration separate from other versions on your system. It is a good idea to always use a virtual environment when developing python code.

You can choose a name for your virtual environment such as ```my_environment```, but often you see a virtual environment called ```venv```.

1. To create a virtual environment we will use the following command:
```
python -m venv my_venv
```
![Virtual Environments](/images/2-prepare/2.3-virtual-environment/virtual-environment-001.png?featherlight=false&width=90pc)

Once the virtual environment has been created, you need to activate it. Once activated, your code runs inside the environment, including any packages you install.

2. To activate the environment use one of the following commands
* For Linux/macOS, execute the following command:
```
source my_venv/bin/activate
```
* For Windows (Git-Bash), execute the following command:
```
source my_venv/Scripts/activate
```
* For Windows (PowerShell), execute the following command:
```
.\my_venv\Scripts\Activate.ps1
```
![Virtual Environments](/images/2-prepare/2.3-virtual-environment/virtual-environment-002.png?featherlight=false&width=90pc)

To know you are inside the virtual environment your command prompt will have the prefix **(my_venv)**. Now any packages you use will be stored in a folder structure inside your virtual environment.

To exit from the virtual environment, you type ```deactivate``` and the command prompt will no longer be prefixed by **(my_venv)**.
