---
title: Basic Documentation for Async Programming in Python
published: true
---



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

