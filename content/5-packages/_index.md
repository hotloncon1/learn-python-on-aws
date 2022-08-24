+++
title = "Python Packages"
date = 2020
weight = 5
chapter = false
pre = "<b>5. </b>"
+++

#### Python Packages

We are nearly ready to start interacting with AWS. Before we do this we need to install some additional software called a package.

A python package is code comprising of individual components called modules that we can use in our code. Packages save us from having to write every aspect of our program from scratch by allowing us to use other peoples code. By importing packages into our program we can use the features of that package. Python has common packages that are included, others have to be installed into our virtual environment using the python package manager [pip](https://pypi.org/project/pip/)

To work with AWS you will need to install the [Boto3](https://pypi.org/project/pip/) package

1. At the command prompt in the terminal type:
```
pip install boto3
```
![Python Packages](/images/5-packages/packages-001.png?featherlight=false&width=90pc)

{{% notice note %}} 
If you get an error message. Check you have exited from the python interactive environment indicated by >>>. You should be at $ prompt in the shell.
{{% /notice %}}

2. We can see what packages we have installed at any time by typing the following:
```
pip freeze
```
* We will see the result.
![Python Packages](/images/5-packages/packages-002.png?featherlight=false&width=90pc)