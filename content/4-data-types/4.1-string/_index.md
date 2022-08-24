+++
title = "Strings"
date = 2020
weight = 1
chapter = false
pre = "<b>4.1. </b>"
+++
#### Strings

In python a **string**, is shortened to **str** and refers to anything inside quotes. The quotes can be double or single. The examples below are identical to python.

```
"The quick brown fox jumped over the lazy dog"
'The quick brown fox jumped over the lazy dog'
```

If you want to include a direct quote in your sentence, then use single quotes for the string and double quotes for the direct quote or other ways. For example:

```
'The error message was "Incorrect DataType"'
"The error message was \"Incorrect DataType\""
'The error message was \'Incorrect DataType\''
"The error message was 'Incorrect DataType'"
```

This allows you the flexibility to use single quotes to wrap the string and double quotes inside the string for a direct quote, without python getting confused.

1. In the terminal, type ```python``` and press **Enter** to onpen the **Interactive Mode**
![Virtual Environments](/images/4-data-types/4.1-string/string-001.png?featherlight=false&width=90pc)
2. Strings, like all data types, can be assigned to a variable. 
* Type or copy the following into the python interactive mode
```
first_name = "Monty"
last_name = "Python"
```
* Press **Enter**
![Virtual Environments](/images/4-data-types/4.1-string/string-002.png?featherlight=false&width=90pc)

{{% notice info %}} 
We have just created a python variable called **first_name** and given it a value **"Monty"**.\
We have just created another python variable called **last_name** and given it a value **"Python"**.
{{% /notice %}}

3. We can print the value of these variables using **print** function.
* Type or copy the following into the python interactive mode
```
print(first_name)
print(last_name)
```
* Press **Enter**. We will see the result.
![Virtual Environments](/images/4-data-types/4.1-string/string-003.png?featherlight=false&width=90pc)
4. You can add strings together using variables. This concatenates them.
* Type or copy the following into the python interactive mode
```
print(first_name + last_name)
```
* Press **Enter**. We will see the result.
![Virtual Environments](/images/4-data-types/4.1-string/string-004.png?featherlight=false&width=90pc)
5. You can see that there isn't a space in **MontyPython**. To include a space, you need to either add it to the beginning or end of your word or add it as a separate string.
* Type or copy the following into the python interactive mode
```
print(first_name + " " + last_name)
```
* Press **Enter**. We will see the result.
![Virtual Environments](/images/4-data-types/4.1-string/string-005.png?featherlight=false&width=90pc)

#### Using Variables in Strings

Imagine we want to use the value of a variable in the middle of a string. This can be done a few ways in python.

6. Use **.format()** to use the value of a variable in the middle of a string
{{% notice info %}} 
In this method you can use the **{}** in your string to indicate where the variable should go. Then use **.format(variable_name)** after the quotation marks. If you have multiple variables, for each variable you use a **{}**. In the **.format()** separate each variable with a comma. For example **.format(variable_1, variable_2)**.
{{% /notice %}}
* Type or copy the following into the python interactive mode
```
first_name = "John"
surname = "Doe"
print("My first name is {}. My family name is {}".format(first_name, surname))
```
* Press **Enter**. We will see the result.
![Virtual Environments](/images/4-data-types/4.1-string/string-006.png?featherlight=false&width=90pc)
7. Use **f strings** to use the value of a variable in the middle of a string
{{% notice info %}} 
Since python version 3.6 it has been possible to use a format called **f-strings** to include variables in your strings. Some people find this format easier to read.
{{% /notice %}}
* Type or copy the following into the python interactive mode
```
print(f"My first name is {first_name}. My family name is {surname}")
```
* Press **Enter**. We will see the result.
![Virtual Environments](/images/4-data-types/4.1-string/string-007.png?featherlight=false&width=90pc)

There are more actions we can perform on strings, but we have enough information to start using python with AWS. You can either continue to learn more, or move on to Integers.