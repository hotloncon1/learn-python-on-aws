+++
title = "List Comprehensions"
date = 2020
weight = 3
chapter = false
pre = "<b>9.3. </b>"
+++
#### List Comprehensions

1. We will generate a list of just the text we want to translate out of the provided data of the **translate_input.json** file
* Open the **lab_6_loops.py** file
* Add the following function to our code in **lab_6_loops.py**
```
# Create a list of the input text
def new_input_text_list():
    input_text = open_input()
    new_list = []
    for item in input_text:
        text = item['Text']
        new_list.append(text)
    print(new_list)
```
* Call the **new_input_text_list()** function from your **main()** look like:
```
def main():
    new_input_text_list()
    translate_loop()
```
* Save
![Looping over JSON](/images/9-loop/9.3-list-comprehensions/list-comprehensions-001.png?featherlight=false&width=90pc)
2. To run the program, enter the following command in the terminal:
```
python lab_6_loops.py --file translate_input.json
```
* Press **Enter**. See the result.
![Looping over JSON](/images/9-loop/9.3-list-comprehensions/list-comprehensions-002.png?featherlight=false&width=90pc)

We will see the return is a list look like:
```
['What is cloud computing?', 'Cloud computing is the on-demand delivery of IT resources over the Internet with pay-as-you-go pricing.', 'Instead of buying, owning, and maintaining physical data centers and servers, you can access technology services, such as computing power, storage, and databases, on an as-needed basis from a cloud provider like Amazon Web Services (AWS)', 'Who is using cloud computing?', 'Organizations of every type, size, and industry are using the cloud for a wide variety of use cases, such as data backup, disaster recovery, email, virtual desktops, software development and testing, big data analytics, and customer-facing web applications.', 'For example, healthcare companies are using the cloud to develop more personalized treatments for patients. Financial services companies are using the cloud to power real-time fraud detection and prevention.', 'And video game makers are using the cloud to deliver online games to millions of players around the world.']
```

#### List Comprehensions

3. We will use a **for** loop to generate new lists using **.append()** is a perfectly valid way of generating new lists. However, we can use a list comprehension to reduce this to a single line. It combines the **for** loop and the creation of the list into a single line.
* Open the **lab_6_loops.py** file
* Add the following function to our code in **lab_6_loops.py**
```
def new_list_comprehension():
    input_text = open_input()
    list_comprehension = [item['Text'] for item in input_text]
    print(list_comprehension)
```
* Call the **new_list_comprehension()** function from your **main()** look like:
```
def main():
    new_input_text_list()
    translate_loop()
    new_list_comprehension()
```
* Save
![Looping over JSON](/images/9-loop/9.3-list-comprehensions/list-comprehensions-003.png?featherlight=false&width=90pc)
4. To run the program, enter the following command in the terminal:
```
python lab_6_loops.py --file translate_input.json
```
* Press **Enter**. See the result.
![Looping over JSON](/images/9-loop/9.3-list-comprehensions/list-comprehensions-004.png?featherlight=false&width=90pc)

{{% notice info %}} 
We will see that it performs the same function as the for loop but on a single line. Although these look complex to start with we can break down the structure to make it easier to remember.\
We will see list comprehensions used in other code, so if we don't decide to use them, we will at least be able to determine what they are doing.
{{% /notice %}}