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

The concept ```await``` is used as a key word to control a loop passed as an event. Both synchronous and asynchronous uses tasks perfomed while the whole code is executed. The only main difference between being sync and async is the code's threads, so referering to the explanation at the beginning of this doc, a sync code has only one thread, while an async code has multiple threads because of a code block's awaiting. 

In the previous example, we have some asyncio's methods and this is trully important. That will allow us to make a code asynchronous and there are plenty of methods you as a programmer can use, but just let's take a look. 

```python
print(await asyncio.gather(test(word="Hello")))
```
What we are doing in this sniṕpet code? First, let's define what does  ```asyncio.gather()``` means. Asyncio provides this method to call awaitable objects together. In our example, it doesn't make too sense because we are using just one object to call  ```test(word: str)``` and it's just one arg, but it's useful when we have +2 objects calling 'em at the same time. I've got this well-written [doc](https://superfastpython.com/asyncio-gather/) for you if you wanna play with gathering objects. 

```python
await asyncio.sleep(0.5)
```
This snippet code seems pretty easy to understand, but hold up, not too fast eh.  ```time``` (another Python module) already has a similar method, named  ```time.sleep()```. Ok, so what's the main difference? Yeah, one's for async threads and the other one for a single-thread code. Mmm, not so close, because we are talking about something really important. 

If we use ```time.sleep()```, we are suspending a whole single-thread execute until with an specific time range. 





In async programming, we count with 3 main objects:
- Tasks
- Courutines
- Futures



