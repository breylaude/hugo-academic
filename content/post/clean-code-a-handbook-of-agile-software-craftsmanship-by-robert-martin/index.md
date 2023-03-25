---
title: '"Clean Code: A Handbook of Agile Software Craftsmanship," by Robert Martin'
date: 2023-03-25T01:10:28.369Z
summary: 'Here is a book review that I wrote about "Clean Code: A Handbook of
  Agile Software Craftsmanship," by Robert Martin.'
draft: false
featured: false
tags:
  - Software Engineering
  - Book Review
image:
  filename: featured
  focal_point: Smart
  preview_only: false
---
Reading Clean Code and following its advice will make you a better computer programmer. Applying the programming techniques described in Clean Code to your work is like stripping layers of paint from fine woodwork in an older home. You end up with improvements that make life better. Your source code will be easier to understand, easier to test, and easier to maintain. Other programmers will be able to understand it. \
 \
Clean Code has 17 chapters written by eight authors. Most of the chapters are written by the principal author, Robert Martin. With one exception, each chapter has a single author. Each chapter tackles a different subject and covers the topic by breaking it down into a cohesive set of paragraphs, with each paragraph having a meaningful subtitle. Even with eight authors, Clean Code reads like a book written by one voice. The authors wrote this book with the same care they apply to their computer programs, by reducing its complexity to a system of small parts. It is a seamless piece of work. \
 \
Clean Code can be read three ways: 1) as a quick read, skipping most of the source code samples and case studies; 2) as the authors intended; 3) in a way not suggested by the authors-- read the text, skip large sections of Java code, and find your own examples and case studies to convert from messy code into clean code. \
 \
The authors warn against the first option, "This is not a feel good book that you read on an airplane and finish before you land. You'll be reading code--lots of code. And you will be challenged to think about what's right about that code and what's wrong with it." The authors want you to study each and every line of Java code listed in the book, and this book is loaded with examples and case studies. They mean it. Reading and understanding all of the examples and case studies in this book is daunting. \
 \
The problem for me, however, is that all of the examples are in Java and I'm a C/C++ programmer. I took the third approach. I studied the simple examples, but I glossed over the more complex case studies. Instead, I applied the techniques to a C++ program that I had already programmed--making that code much, much better. I worked quite hard at this. This book is applicable to all object oriented programming languages, not just Java. It worked for me. \
 \
Clean Code explains how to make your code more readable by giving all variables meaningful names. It explains how programs become polluted with out-of-date comments and how to write code that requires little or no comments. It explains how to design and program classes that are small and easy to understand. It is loaded with examples of refactoring complex code into more simple code. The authors speak from experience and all their assertions are backed up with examples and case studies. \
 \
This book is loaded with ways to write better code. Here are some examples: \
 \
"The ideal number of arguments for a function is zero (niladic). Next comes one (monadic), followed closely by two (dyadic). Three arguments (triadic) should be avoided where possible. More than three (polyadic) requires very special justification--and then shouldn't be used anyway." (I particularly like the terms niladic, monadic, dyadic, triadic, and polyadic.) \
 \
"Output arguments are harder to understand than input arguments. When we read a function, we are used to the idea of information going into the function through arguments and out through the return value. We don't usually expect information to be going out through the arguments. So output arguments often cause us to do a double-take." \
 \
"Flag arguments are ugly. Passing a Boolean into a function is a truly terrible practice. It immediately complicates the signature of the method, loudly proclaiming that this function does more than one thing. It does one thing if the flag is true and another if the flag is false!" \
 \
"Clear and expressive code with few comments is far superior to cluttered and complex code with lots of comments. Rather than spend your time writing the comments that explain the mess you've made, spend it cleaning that mess." \
 \
"The first rule of classes is that they should be small. The second rule is that they should be smaller than that." \
 \
These quotes are only a small sample of better programming concepts that are so well described in this book. The booked is filled with similar tips to write better software. For example, Chapter 4: Comments, has the best advice for writing comments that I've ever read. The authors tell you what makes a bad comment and why most comments are, in fact, not very helpful. That chapter alone is worth the price of the book. Chapter 7: Error Handling, has a number of techniques on how to handle errors with "grace and style." These error handling techniques make sense and their use results in more robust programs. \
 \
Even though all of the case studies and examples are in Java, reading this book should not be a problem for non-Java programmers. With careful reading, you can follow the examples and you will learn some Java as you read the book. If you are not programming in an object oriented language, however, this book will make little sense. A pre-requisite to reading Clean Code is proficiency in object oriented programming. \
 \
My one criticism of the book is that the authors are a bit dogmatic in saying that their techniques are the best. For example, they disdain switch statements. I didn't find their argument for their dislike of switch statements to be very compelling. I can accept and forgive this, however, as their collective experience is impressive. They speak from many years of experience. \
 \
Chapter 15: JUnit Internals, has the best example. The author includes an example of high quality, clean code, taken from the Java framework. Then the authors improve the code, explaining all their changes as they go. They call this the Boy Scout Rule: "Leave the campground cleaner than you found it." They visited the code, studied it, and improved it, showing that even good code can become better code. They left the code cleaner than they found it.