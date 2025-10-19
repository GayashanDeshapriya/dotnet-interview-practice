# 🧠 .NET Practical Interview Questions & Answers

A curated list of **.NET and C# practical interview questions** to help you prepare for technical interviews — from array manipulations to OOP concepts and LINQ tricks.

---

## 📚 Table of Contents
1. [Write a C# program to remove duplicate characters from a string](#1-remove-duplicate-characters-from-a-string)
2. [Reverse a string](#2-reverse-a-string)
3. [Check if a string is a palindrome.](#3-check-palindrome)
4. [Find first non-repeated character in a string](#4-Findfirst-non-repeated-character-in-a-string)

---

### 1. remove-duplicate-characters-from-a-string
**Answer:**  
Use a HashSet  
```csharp
namespace InterviewPractice
{
    class Program
    {
        static string removeDuplicates(string s)
        {
            var seen = new HashSet<char>();
            var result = new System.Text.StringBuilder();

            foreach (var c in s)
            {
                if (!seen.Contains(c))
                {
                    seen.Add(c);
                    result.Append(c);
                }
            }
            return result.ToString();
        }
        static void Main(string[] args)
        {
            Console.WriteLine("Enter your word here:");
            string? input = Console.ReadLine();
            if (input != null)
            {
                string output = removeDuplicates(input);
                Console.WriteLine("Output without duplicates: " + output);
            }
        }
    }
}
```
### 2. reverse-a-string
**Answer:**  
Use a Array
```csharp
namespace InterviewPractice
{
    class Program
    {
        static string Reverse(string s)
        {
            char[] arr = s.ToCharArray();
            Array.Reverse(arr);
            return new string(arr);
        }
        static void Main(string[] args)
        {
            Console.WriteLine("Enter your word");
            string? input = Console.ReadLine();
            if (input != null)
            {
                string output = Reverse(input);
                Console.WriteLine("Reverse Versin is: " + output);
            }
        }
    }
}
```

### 3. check-palindrome
**Answer:**  
```csharp
namespace InterviewPractice
{
    class Program
    {
        static bool Ispalidrome(string s)
        {
            int i = 0, j = s.Length - 1;
            while (i < j)
            {
                if (s[i++] != s[j--])
                {
                    return false;
                }

            }
            return true;
        }

        static void Main(string[] args)
        {
            Console.WriteLine("Enter Word:");
            String? input = Console.ReadLine();
            if (input != null)
            {
                bool value = Ispalidrome(input);
                Console.WriteLine(value);
            }

        }
    }
}
```

### 4. Findfirst-non-repeated-character-in-a-string
**Answer:**  
```csharp
namespace InterviewPractice
{
    class Program
    {
        static char ? FirstNonRepeated(string s)
        {
            var freq = new Dictionary<char, int>();
            foreach(var c in s)
            {
                freq[c] = freq.GetValueOrDefault(c, 0) + 1;

            }
            foreach(var c in s)
            {
                if (freq[c] == 1)
                {
                    return c;
                }
            }
            return null;
        }
        
        static void Main(string[] args)
        {
            Console.WriteLine("Enter your word");
            string? input = Console.ReadLine();
            if (input != null)
            {
                char? output = FirstNonRepeated(input);

                if (output != null)
                {
                    Console.WriteLine("First non-repeated character: " + output);
                }
                else
                {
                    Console.WriteLine("No non-repeated character found.");
                }
            }
        }
    }
}
```

