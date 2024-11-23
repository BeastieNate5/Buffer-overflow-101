# Introduction
Hello Cisco Academy. This lesson I have created for you guys will teach you on what a buffer overflow is and how to preform the exploit. This is important to know if your going into cybersecurity as 70% of vulnerabilities in 2019 were because of a memory exploit which buffer overflows are a part of that. Of course be responsible with this knowledge 🙏 

# Getting Started
You will first need to download and complile the source code in this lesson. To do that enter these following commands on a linux machine.

Moves you to your home directory
```
cd ~
```
Downloads all the code in this lesson from GitHub
```
git clone https://github.com/BeastieNate5/Buffer-overflow-101
```

Moves you into the downloaded code
```
cd Buffer-overflow-101
```

This will compile the code I created for this lesson
```
make
```
This will produce a executable program in the current directory called `main` if you wish to run the program enter the following
```
./main
```

# Content
## What is a buffer overflow?
First you need to know what a buffer is. A buffer is just simply just a container that hold can multiple values. When you create list in Python your basically just creating a buffer that can hold multiple values. In Python you don't need to specify the size of the list. Python will automatically determine how much space it needs to allocate in memory. In other languages like C where you need to compile your code you need to say how big the list/buffer is going to be.

Python (Interpreted language)
```py
buffer = []
```
C (Compiled language)
```c
char buffer[5];
```
Above I created a buffer in both Python and C. Python will automically do the heavy lifting and determine how big `buffer` needs to be. But In C I have to very specific. I first need to say what type of values the buffer will hold. Here I say `char` which means it will store singler characters like 'a'. I then use `[5]` which means I want to store 5 characters. Each character is just a ASCII value and ASCII characters are just one byte. If you don't know what ASCII is, it's just the number representation of a letter, for example 'A' = 65. ASCII values go from 0-127 so all ASCII values are one byte, [ascii chart](https://www.asciitable.com). So if a single character is just one byte and I want 5 of them, that means the `buffer` was allocated 5 bytes.