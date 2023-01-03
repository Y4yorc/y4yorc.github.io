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

* * *

 

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
Now, in order to code asynchronous programming, is important to import a library called ```asyncio```, which provides high-level APIs, structured network code and asynchronous frameworks. You
can find more information about this library [here](https://docs.python.org/3/library/asyncio.html).

That's very important at the time we need to schedule a function that's needed to be executed. And I say "schedule" because as I mentioned
before, you need to code a sequence of statements inside a block of code. To add more fundamental concepts related to this, first check this snippet code:

```python
import asyncio
import time

async def test(word: str):
    return word

async def main():
    print("Time started at: ", time.strftime('%X'))
    print(await asyncio.gather(test(word="Hello")))
    await asyncio.sleep(0.5)

    print("World")

    print("Time finished at: ", time.strftime('%X'))

if __name__ == "__main__":
    asyncio.run(main())

```
When you run this, your console should show you something like this:

```
$ python3 some_code.py
Time started at:  15:34:02
['Hello']
World
Time finished at:  15:34:02
$
```
And yea, I can read your mind and I'd say you have no idea what I just code. Lemme explain you better. In case you have some experience
with Python, you can see that the first function is just returning an string object. In the main function we are calling it but, there's something new for non-async programmers and that's known as Task-based Asynchronous Pattern (TAP), using async/await syntax. 


 

