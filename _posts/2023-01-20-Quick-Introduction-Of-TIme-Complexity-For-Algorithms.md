---
title: Quick Introduction of Time Complexity for Algorithms
published: true
---


Programming is like a cooking recipe. There's a set of instructions in which, you need to follow to solve an specific problem, or to perform a task. And each task in this case, will conform the whole cooking recipe. 

Wanna make a pizza? You need some ingredients (Which from now, I'm gonna call 'em as objects to be in reference): Cheese, Tomato sauce, Pizza dough, etc. You need to assemble all ingredients and then bake it. But I'll ask u something: Don't u ever took how much time did u last making all that pizza? 

In programming, it works similar, but at the time we are coding, we can figure out why our code is taking so much long time to execute, compile, etc. Or the opposite way: Why our code is running so fast, even before noticing how many code lines we wrote?

That's a hard truth when we are talking about algorithms. I know that debugging a +10000 line code program is really difficult, frustating and also takes a lot of time in terms of releasing a project or adding new updates to that project. To avoid that (or maybe, to invest better our time doing more effectively code) we need to think how we can solve an specific problem in less time possible according to the number of statements that conforms a task, not the time that statement needs to be done.  

To measure it, we as programmers use something we call Time Complexity. And yea, the less tasks needed to be done, better. To understand it, I'll explain very simple how each complexity works with it's respective snipet code. It should be noted that I'll put C code. 

Check this out (resuming all complexities and what the O means):
- 0(1): Constant (Very Good)
- O(Log(N)): Logaritmic (Very Good)
- O(N): Linear (Good)
- O(Nlog(N)): Linearithmic (Good)
- O(N^2): Quadratic (Not good)

These are the most common ones according to the Big O Notation syntax. Notice the last word I put in each time complexity. To summarize it, simplifies the time of an algorithm with that complexity should take. But yea, I'll explain each one with an example. 

* * *

### O(1)

Refers an algorithm that doesn't need to loop or to iterate an object, which means to be constant. A constant object is an inmutable object (can't be modified), so if are outputing something or doing a conditional statement, remember that those objects once outputed can't be modified unless u modify ur code. 

Check this simply code:

```c
#include <stdio.h>

int main(int argc, char* argv[]) {
    int number = 4;
    
    if(number < 5) {
        printf("This number is lower than 5\n");
    } else {
        printf("This number is higher than 5\n");
    }

    return 0;
}
```
When I run this, it should showed me something like this: 

```
$ gcc some_code.c -o main && ./main
This number is lower than 5
$
```

Very simple. It's just a conditional statement outputing something, but to put u in reference, there's no a loop conditional inside a block of code we need to execute, so it takes less than 14 nanoseconds to output a string object. If u don't understand what are the main function's args, check this [doc](https://linuxhint.com/argc-argv-cpp/), it's the same for C and C++. 




