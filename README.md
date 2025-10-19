# 🧠 .NET Practical Interview Questions & Answers

A curated list of **.NET and C# practical interview questions** to help you prepare for technical interviews — from array manipulations to OOP concepts and LINQ tricks.

---

## 📚 Table of Contents
1. [Write a C# program to remove duplicate characters from a string.](#1-remove duplicate characters from a string.)
2. [Reverse a string](#2-reverse-a-string)
3. [Check palindrome](#3-check-palindrome)
4. [Count vowels in a string](#4-count-vowels-in-a-string)
5. [Find largest number in an array](#5-find-largest-number-in-an-array)
6. [Find second highest number](#6-find-second-highest-number)
7. [Count occurrence of each character](#7-count-occurrence-of-each-character)
8. [Swap two numbers without third variable](#8-swap-two-numbers-without-third-variable)
9. [Factorial of a number](#9-factorial-of-a-number)
10. [Prime number check](#10-prime-number-check)
11. [Fibonacci series](#11-fibonacci-series)
12. [Find duplicates in a list using LINQ](#12-find-duplicates-in-a-list-using-linq)
13. [Find missing number in array 1..n](#13-find-missing-number-in-array-1n)
14. [Difference between ref and out](#14-difference-between-ref-and-out)
15. [Difference between const and readonly](#15-difference-between-const-and-readonly)
16. [Use of async/await](#16-use-of-asyncawait)
17. [Boxing and Unboxing](#17-boxing-and-unboxing)
18. [Value type vs Reference type](#18-value-type-vs-reference-type)
19. [Interface vs Abstract class](#19-interface-vs-abstract-class)
20. [Polymorphism example](#20-polymorphism-example)

---

### 1. Remove duplicates from an array
**Answer:**  
Use a HashSet or LINQ `Distinct()`  
```csharp
var result = arr.Distinct().ToArray();
