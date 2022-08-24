+++
title = "Dictionaries"
date = 2020
weight = 3
chapter = false
pre = "<b>4.3. </b>"
+++
#### Dictionaries

A **dictionary** is a way of storing related information in **key-value** pairs. It uses a **key** as an identifier and a **value** to store the information. For example, the key could be **first_name** and the value could be **Ada**.

A dictionary when written in python would look like **{"first_name":"Ada"}**. A **dictionary** in python is abbreviated to dict and has the following syntax **{"key":"value"}**. The key is a string providing an identifier and the value can be the same kind of values you would store in a variable.

Dictionaries are very common in AWS, so you will see them frequently:
* They are used to exchange information between different services and functions
* They are returned by Application Programming Interfaces (API)
* They are used as Tag values

#### Create

Dictionaries can be created by assigning the key-values you want to store in the dictionary.

1. Create a dictionary has the contents:
* Type or copy the following into the python interactive mode
```
user = {"first_name":"Ada"}
print(user)
```
* Press **Enter**. We will see the result.
![Dictionaries](/images/4-data-types/4.3-dictionaries/dictionaries-001.png?featherlight=false&width=90pc)
2. Create an empty dictionary (two ways):
* Assigning **{}** to a variable, type or copy the following into the python interactive mode
```
first_empty_dictionary = {}
print(first_empty_dictionary)
```
* Press **Enter**.
* Using the **dict()** constructor, type or copy the following into the python interactive mode
```
second_empty_dictionary = dict()
print(second_empty_dictionary)
```
* Press **Enter**. We will see the result.
![Dictionaries](/images/4-data-types/4.3-dictionaries/dictionaries-002.png?featherlight=false&width=90pc)

#### Read

To read the value associated with a key, you need to provide the name of the dictionary and the the value of the key inside square brackets.

3. Type or copy the following into the python interactive mode
```
user = {"first_name":"Ada"}
print(user["first_name"])
```
* Press **Enter**. We will see the result. We read the value associated with the **first_name** key of the **user** dictionary.
![Dictionaries](/images/4-data-types/4.3-dictionaries/dictionaries-003.png?featherlight=false&width=90pc)

#### Update

Dictionaries are mutable, which means they can be changed after you create them. You can add, update or delete the key-value pairs in a dictionary.

4. To add an additional **key-value** to a dictionary, provide the dictionary name, the new **key** in **[]** and a value after an **=** sign.
* Type or copy the following into the python interactive mode
```
user["family_name"] = "Byron"
print(user)
```
* Press **Enter**. We will see the result. We added a **key-value** to the **user** dictionary.
![Dictionaries](/images/4-data-types/4.3-dictionaries/dictionaries-004.png?featherlight=false&width=90pc)
5. To modify a value in a similar way to adding it. You provide the new value after the **=** sign.
* Type or copy the following into the python interactive mode
```
user["family_name"] = "Lovelace"
print(user)
```
* Press **Enter**. We will see the result. We changed the value associated with the **first_name** key to **"Lovelace"**
![Dictionaries](/images/4-data-types/4.3-dictionaries/dictionaries-005.png?featherlight=false&width=90pc)
6. To remove a **key-value pair** you use the **del** statement with the name of the dictionary and the key you want to delete.
* Type or copy the following into the python interactive mode
```
del user["family_name"]
print(user)
```
* Press **Enter**. We will see the result. We deleted the **key-value pair** whose key is **first_name**
![Dictionaries](/images/4-data-types/4.3-dictionaries/dictionaries-006.png?featherlight=false&width=90pc)

A dictionary, like a variable can contain other data types, including other dictionaries and lists. You will use dictionaries a lot in AWS as input and outputs.