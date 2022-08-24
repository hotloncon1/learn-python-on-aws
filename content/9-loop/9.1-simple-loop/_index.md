+++
title = "Simple Loops"
date = 2020
weight = 1
chapter = false
pre = "<b>9.1. </b>"
+++
#### Simple Loops

we will create a simple example in the python interactive environment to show how looping over a list works.

1. Create a list and assign it to a variable:
* Type or copy the following into the python interactive mode
```
fruit = ['apples','oranges','bananas']
```
* Press **Enter**
![Simple Loops](/images/9-loop/9.1-simple-loop/simple-loop-001.png?featherlight=false&width=90pc)
2. Create a **for** loop and print out the items in the list one by one
* Type or copy the following into the python interactive mode
```
for item in fruit:
   print(f'The best fruit now is {item}')
```
* Double pressing **Enter**. We will see the result
![Simple Loops](/images/9-loop/9.1-simple-loop/simple-loop-002.png?featherlight=false&width=90pc)
3. If you want to want to use a loop as a counter, you could create a list of numbers and assign it to a variable
* Type or copy the following into the python interactive mode
```
numbers = [0,1,2,3,4,5,6,7,8,9,10]
```
* Press **Enter**
![Simple Loops](/images/9-loop/9.1-simple-loop/simple-loop-003.png?featherlight=false&width=90pc)
4. Type or copy the following into the python interactive mode
```
for number in numbers:
   print(f'The next number is {number}')
```
{{% notice info %}} 
This example print all the numbers from 0 to 10
{{% /notice %}}
* Double pressing **Enter**. We will see the result
![Simple Loops](/images/9-loop/9.1-simple-loop/simple-loop-004.png?featherlight=false&width=90pc)
5. Previous example print all the numbers from 0 to 10, but what if you wanted to count to 1000. It would be tedious to write all the numbers out in this way.Instead we use the **range()** function.
* Type or copy the following into the python interactive mode
```
for number in range(10):
   print(f'The next number is {number}')
```
* Double pressing **Enter**. We will see the result
![Simple Loops](/images/9-loop/9.1-simple-loop/simple-loop-005.png?featherlight=false&width=90pc)
6. We can see that computers start counting at 0 as the first number, If we want to start counting at 1, we can still use the **range()** method.
* Type or copy the following into the python interactive mode
```
for number in range(1,10):
   print(f'The next number is {number}')
```
* Double pressing **Enter**. We will see the result
![Simple Loops](/images/9-loop/9.1-simple-loop/simple-loop-006.png?featherlight=false&width=90pc)
7. If we want to increment the counter by more than the default value of 1, perhaps if we wanted only odd numbers or even numbers for example. To do this you add a third parameter to the range() function
* Type or copy the following into the python interactive mode
```
for number in range(1,10,2):
   print(f'The next number is {number}')
```
{{% notice info %}} 
The **range(start, stop, step)** function includes:\
**start** parameter: Optional. An integer number specifying at which position to start. Default is 0.\
**stop** parameter: Required. An integer number specifying at which position to stop (not included).\
**step** parameter: Optional. An integer number specifying the incrementation. Default is 1
{{% /notice %}}
* Double pressing **Enter**. We will see the result
![Simple Loops](/images/9-loop/9.1-simple-loop/simple-loop-007.png?featherlight=false&width=90pc)