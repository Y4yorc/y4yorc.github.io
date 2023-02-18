---
title: The Fizzbuzz Challenge in JavaScript
published: true
---

When we talk about a problem that's very common in an interview, we assume we already know how 
to code and solve it. We can discuss some of the most popular problems, like the fibonacci algorithm, plenty of sorting algorithms, etc. and that's a true thing. 

We surely don't know how many problems are but, I'll explain u (by my words) one problem very popular (and often is memed by the community) that's in the 98% of the times, it'll be a question you need to solve by hand in less than 5 min (well, that's the most accurate number tho). This problem's called: The FizzBuzz. 

This article will be relately short, but I'll explain the problem and how to solve it in JavaScript. I'll start saying that this problem is very simple, but it's a good way to test your logic and your ability to code it in the less time possible. 

I'll not use any GUI tools to explain the algorithm, since it's very easy. The thing is that there's lots of ways to solve this problem and each programmer has his own way to solve it according to his logic, so there's no "the best way" to solve it or, a unique rule to follow and if u don't follow it, u are disordering the time-space continuum and the universe will collapse. lol

Nah, just kidding (or not). Well, let's start. First of all, what is the FizzBuzz problem? This problem consists in a simple algorithm that prints the numbers from 1 to 100, but if the number is divisible by 3, it outputs "Fizz" instead of the number, if the number is divisible by 5, it outputs "Buzz" instead of the number and if the number is divisible by 3 and 5 (or 15), it outputs "FizzBuzz" instead of the number.

Seems easy, right? Well, as I said, there's lots of ways to solve this problem, but I'll code it in some ways I thought of. Check this out: 
    
```js
// By Yayo

const fizzbuzz = (n) => {
    for (let i = 1; i <= n; i++) {
        if (i % 15 == 0) console.log('FizzBuzz');
        else if (i % 3 == 0) console.log('Fizz');
        else if (i % 5 == 0) console.log('Buzz');
        else console.log(i);
    }
}

```

If you already know JavaScript, you are just noticing I did an if sentence. To reduce lines, I didn't use curly brackets (yea, Python memories lol). But you can use them:
    
```js
// By Yayo

const fizzbuzz = (n) => {
    for (let i = 1; i <= n; i++) {
        if (i % 15 == 0) {
            console.log('FizzBuzz');
        } else if (i % 3 == 0) {
            console.log('Fizz');
        } else if (i % 5 == 0) {
            console.log('Buzz');
        } else {
            console.log(i);
        }
    }
}

```

Let's see what happens if we call this function with the number 100 (well yea, it's 1 to 100). 

```
$ node fizzbuzz.js
1
2
Fizz
4
Buzz
Fizz
7
8
Fizz
Buzz
11
Fizz
13
14
FizzBuzz
16
17
Fizz
19
Buzz
Fizz
22
23
Fizz
Buzz
26
Fizz
28
29
FizzBuzz
31
32
Fizz
34
Buzz
Fizz
37
38
Fizz
Buzz
41
Fizz
43
44
FizzBuzz
46
47
Fizz
49
Buzz
Fizz
52
53
Fizz
Buzz
56
Fizz
58
59
FizzBuzz
61
62
Fizz
64
Buzz
Fizz
67
68
Fizz
Buzz
71
Fizz
73
74
FizzBuzz
76
77
Fizz
79
Buzz
Fizz
82
83
Fizz
Buzz
86
Fizz
88
89
FizzBuzz
91
92
Fizz
94
Buzz
Fizz
97
98
Fizz
Buzz
$
```

Damn well, that's a lot of outputed lines. What we can do in this case? Let's try creating an array which all the output will be stored in it and then, we'll print the list. 

