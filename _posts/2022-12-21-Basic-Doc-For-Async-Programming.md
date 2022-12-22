---
title: Basic Documentation for Async Programming in Python
published: true
---

## Basics

When a programmer is writing some code, usually is noted that a function requires to be executed, making 
this code synchronous. Here's a basic example. 

```python 
# Add 2 numbers

def sum_numbers(x, y):
     return x + y

def main():
     x, y = 4, 5
     print(sum_numbers(x, y))

main()
```

In this example, the interpreter knows that the args in the function above needs to be known
to be executed. Because of this, the numbers are known calling the main function. (What is to 
be expected.) In this example, the output will be 9. 				

* * *

## Async Basics 

However, there's another way to code in a simply way, when 2 (or more) functions are being executed at the same time, with different responses and 
one after the other. I know this seems pretty confusing, so I'm gonna explain it to you in a more simple way. 

```python 
def sum_numbers(x, y):
     return x + y
```

From the previous example, we can note that there's a return value. However, we're not calling the function, so there will be no output. When this function is being called 
while another function is running, this is what is known as asynchronous code. In Python (and JavaScript), it's being denoted by the key word ```async```. So, refering as a main 
function, it is something like: 

```python
async def main():
     # Code here
```
 

