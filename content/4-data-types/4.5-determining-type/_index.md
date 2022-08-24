+++
title = "Determining Type"
date = 2020
weight = 5
chapter = false
pre = "<b>4.5. </b>"
+++
#### Determining Type

Sometimes your code will raise a TypeError. These can be frustrating to fix. The first step is often to find out what type of data python thinks the object is.

The way to find out what type of data python has stored in a variable is to use the type() method.

1. Type or copy the following into the python interactive mode
```
my_variable = "A string"
print(type(my_variable))
```
* Press **Enter**. We will see the result.
![Determining Type](/images/4-data-types/4.5-determining-type/determining-type-001.png?featherlight=false&width=90pc)

{{% notice note %}} 
Once you know the type data, you can fix the issue by being explicit about how you want python to treat the data.
{{% /notice %}}

2. Type or copy the following into the python interactive mode
```
my_number = 50
some_string = "The number is "
print(some_string + my_number)
```
* Press **Enter**. We will see the result.
![Determining Type](/images/4-data-types/4.5-determining-type/determining-type-002.png?featherlight=false&width=90pc)
3. We can fix the **TypeError** by telling python to convert **my_number** to a string.
* Type or copy the following into the python interactive mode
```
my_number = 50
some_string = "The number is "
print(some_string + my_number)
```
* Press **Enter**. We will see the result. That error was fixxed.
![Determining Type](/images/4-data-types/4.5-determining-type/determining-type-003.png?featherlight=false&width=90pc)