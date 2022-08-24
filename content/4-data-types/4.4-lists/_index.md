+++
title = "Lists"
date = 2020
weight = 4
chapter = false
pre = "<b>4.4. </b>"
+++
#### Lists

A list is an ordered sequence of values separated by spaces. For example: **[0, 1, 2, 3, 4]** or **["apples", "oranges", "bananas"]**

A list can contain other objects(for example dictionaries). For example: **[{"fruit_type" : "apples"}, {"number" : 50}]**

#### Create a list
1. Lists can be created by assigning the values you want to store in a list to a variable
* Type or copy the following into the python interactive mode
```
fruit = ["apples","oranges","bananas"]
print(fruit)
```
* Press **Enter**. We will see the result.
![Lists](/images/4-data-types/4.4-lists/lists-001.png?featherlight=false&width=90pc)
2. If you are going to be adding the contents of the list later, you can declare an empty list. You can create an empty list in two ways:
* Assigning **[]** to a variable. Type or copy the following into the python interactive mode
```
first_empty_list = []
print(first_empty_list)
```
* Press **Enter**. We will see the result.
* Using the **list()** constructor. Type or copy the following into the python interactive mode
```
second_empty_list = list()
print(second_empty_list)
```
* Press **Enter**. We will see the result.
![Lists](/images/4-data-types/4.4-lists/lists-002.png?featherlight=false&width=90pc)


#### Read

Objects stored in list are given an index number starting at 0. To read an element from a list you use the index number of the stored value.
3. Type or copy the following into the python interactive mode
```
fruit = ["apples","oranges","bananas"]
print(fruit[1])
```
* Press **Enter**. We will see the result.
{{% notice note %}} 
In the example above python has printed the value stored at the index position 1, which has returned **oranges**, because the first index is position 0.
{{% /notice %}}
![Lists](/images/4-data-types/4.4-lists/lists-003.png?featherlight=false&width=90pc)
4. To find the length of a list using len()
* Type or copy the following into the python interactive mode
```
len(fruit)
```
* Press **Enter**. We will see the result.
![Lists](/images/4-data-types/4.4-lists/lists-004.png?featherlight=false&width=90pc)
5. We can return the last value in a list or work backwards from the last item using a negative index value. For example to return the last value in the list we use the index value is **-1**
* Type or copy the following into the python interactive mode
```
print(fruit[-1])
print(fruit[-2])
```
* Press **Enter**. We will see the result.
![Lists](/images/4-data-types/4.4-lists/lists-005.png?featherlight=false&width=90pc)

#### Update

Lists are mutable, which means they can be changed after you create them. You can add, update, delete and reorder elements in a list.

6. We can use **append()** to add an element to the end of the list.
* Type or copy the following into the python interactive mode
```
fruit.append("kiwi")
print(fruit)
```
* Press **Enter**. We will see the result. We added an element to the end of the **fruit** list
![Lists](/images/4-data-types/4.4-lists/lists-006.png?featherlight=false&width=90pc)
7. If we want add an element at a specific point in the list you can use the index value with the **insert()** method.
* Type or copy the following into the python interactive mode
```
fruit.insert(2, "passion fruit")
print(fruit)
```
* Press **Enter**. We will see the result.
![Lists](/images/4-data-types/4.4-lists/lists-007.png?featherlight=false&width=90pc)

#### Organizing a list

The elements in a list are not sorted automatically.

8. If we want to return information which is sorted, but retain the original order of the list, you can use the **sorted()** function.
* Type or copy the following into the python interactive mode
```
print(sorted(fruit))
print(fruit)
```
* Press **Enter**. We will see the result.
![Lists](/images/4-data-types/4.4-lists/lists-008.png?featherlight=false&width=90pc)

{{% notice info %}} 
In the example above you can see that the **sorted()** function return a sorted list, but does not alter the original order of the list.
{{% /notice %}}

9. If we want to permanently sort the list, you should use the **sort()** method.
* Type or copy the following into the python interactive mode
```
fruit.sort()
print(fruit)
```
* Press **Enter**. We will see the result.
![Lists](/images/4-data-types/4.4-lists/lists-009.png?featherlight=false&width=90pc)
10. To reverse the order of a list you can use the **reverse()** method. This will permanently reverse the order of the list.
* Type or copy the following into the python interactive mode
```
fruit.reverse()
print(fruit)
```
* Press **Enter**. We will see the result.
![Lists](/images/4-data-types/4.4-lists/lists-010.png?featherlight=false&width=90pc)

#### Delete

11. We can remove elements from a list using the **del** statement if you know the index position.
* Type or copy the following into the python interactive mode
```
del fruit[1]
print(fruit)
```
* Press **Enter**. We will see the result.
![Lists](/images/4-data-types/4.4-lists/lists-011.png?featherlight=false&width=90pc)

12. If we want to use the value after removing it from a list you use the **pop()** method. To use **pop()**, we need to store the value you have removed from the list inside another variable.
* Type or copy the following into the python interactive mode
```
favorite_fruit = fruit.pop()
print(favorite_fruit)
```
* Press **Enter**. We will see the result.
![Lists](/images/4-data-types/4.4-lists/lists-012.png?featherlight=false&width=90pc)
13. **pop()** has returned the last element in the list, which is the default for **pop()**. You can return any element with the **pop()** by using the index value.
* Type or copy the following into the python interactive mode
```
fresh_fruit = fruit.pop(1)
print(fresh_fruit)
```
* Press **Enter**. We will see the result.
![Lists](/images/4-data-types/4.4-lists/lists-013.png?featherlight=false&width=90pc)
14. If you don't know the index position, or you don't want to remove the last item in the list, you can use the **remove()** method to specify the value of the element you want to remove.
* Type or copy the following into the python interactive mode
```
fruit.remove('bananas')
print(fruit)
```
* Press **Enter**. We will see the result.
![Lists](/images/4-data-types/4.4-lists/lists-014.png?featherlight=false&width=90pc)

{{% notice note %}} 
When you use **del**, **pop()** or **remove()**, the element is permanently deleted from the original list. If the list is printed out, you will see that those elements are no longer stored in the list.
{{% /notice %}}