# 🧠Practical Interview Questions & Answers

A curated list of **.NET and C# practical interview questions** to help you prepare for technical interviews — from array manipulations to OOP concepts and LINQ tricks.

---

## 📚 Table of Contents
1. [Write a C# program to remove duplicate characters from a string](#1-remove-duplicate-characters-from-a-string)
2. [Reverse a string](#2-reverse-a-string)
3. [Check if a string is a palindrome.](#3-check-palindrome)
4. [Find first non-repeated character in a string](#4-Findfirst-non-repeated-character-in-a-string)
5. [Remove duplicates from an integer array](#5-Remove-duplicates-from-an-integer-array)
6. [Find Common Elements Between Two Arrays](#6-Find-Common-Elements-Between-Two-Arrays)
7. [Find Second Largest Number in array](#7-Find-Second-Largest-Number-in-array)
8. [8. Find Duplicate characters in string](#8-Find-Duplicate-characters-in-string)


---

### 1. remove-duplicate-characters-from-a-string
**Answer:**  
Use a HashSet  
```csharp
public static void Main()
{
    int[] array = { 1, 2, 3, 4, 4, 5, 5, 6 };

    Console.WriteLine("Using LINQ:");
    int[] result1 = RemoveDuplicatesWithLinq(array);
    DisplayArray(result1);

    Console.WriteLine("\nWithout LINQ (Using HashSet):");
    int[] result2 = RemoveDuplicatesWithoutLinq(array);
    DisplayArray(result2);
}

// Using LINQ
public static int[] RemoveDuplicatesWithLinq(int[] array)
{
    return array.Distinct().ToArray();
}

// Without LINQ
public static int[] RemoveDuplicatesWithoutLinq(int[] array)
{
    HashSet<int> set = new HashSet<int>();

    foreach (int num in array)
    {
        set.Add(num);
    }

    return set.ToArray();
}

public static void DisplayArray(int[] array)
{
    foreach (int num in array)
    {
        Console.WriteLine(num);
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

use pointers
```csharp
public static class Program
{
    public static void Main()
    {
        Console.WriteLine(ReverseString("Animal"));
    }

    public static string ReverseString(string input)
    {
        char[] chars = input.ToCharArray();
        int left = 0;
        int right = input.Length - 1;

        while (left < right)
        {
            char temp = chars[left];
            chars[left] = chars[right];
            chars[right] = temp;

            left ++;
            right--;

        }
        return new string(chars);

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
### 5. Remove-duplicates-from-an-integer-array
**Answer:**  
```csharp
namespace InterviewPractice
{
    class Program
    {
        static int[] RemoveDuplicate(int[] arr)
        {
            return arr.Distinct().ToArray();
        }

        static void Main(string[] args)
        {
            int[] array = { 1, 2, 3, 3, 4 };
            int[] newarr = RemoveDuplicate(array);
            for (int i = 0; i < newarr.Length; i++)
            {
                Console.WriteLine(newarr[i]);
            }
        }
    }
}
```
### 6. Find-Common-Elements-Between-Two-Arrays
**Answer:**  
```csharp
namespace InterviewPractice
{
    class Program
    {
        //common way
        public static void FindCommonElements(int[] arr1, int[] arr2)
        {
            List<int> common = new List<int>();
            for (int i = 0; i < arr1.Length; i++)
            {
                for (int j = 0; j < arr2.Length; j++)
                {
                    if (arr1[i] == arr2[j])
                    {
                        if (!common.Contains(arr1[i]))
                        {
                            common.Add(arr1[i]);
                        }
                    }
                }
            }
            Console.WriteLine("Common elements: " + string.Join(", ", common));
        }

        //Using Dictionary or hashset
        public static void FindCommonElementsOptimized(int[] arr1, int[] arr2)
        {
            HashSet<int> set = new HashSet<int>(arr1);
            List<int> common = new List<int>();

            foreach (int i in arr2)
            {
                if (set.Contains(i)) common.Add(i);
            }
            Console.WriteLine("Common elements: " + string.Join(", ", common));
        }

        static void Main(string[] args)
        {
            int[] array1 = { 1, 2, 3, 4 };
            int[] array2 = { 2, 3, 4 };
            FindCommonElements(array1, array2);
            FindCommonElementsOptimized(array1, array2);
        }
    }
}
```
### 7. Find Second Largest Number in array
**Answer:**  
```csharp
public static void Main()
{
    int[] numbers = { 5, 10, 3, 8, 2 };
    Console.WriteLine( FindSecondLargestNumber(numbers));

}

public static int FindSecondLargestNumber(int[] array)
{
    int largest = int.MinValue;
    int secondLargest = int.MinValue;

    foreach (int num in array)
    {
        if(num > largest)
        {
            secondLargest = largest;
            largest = num;
        }
        else if (num > secondLargest && num != largest )
        {
           secondLargest= num;
        }            
    }
    return secondLargest;
}
```

### 8. Find Duplicate characters in string
**Answer:**  
```csharp
public static class Program
{
    public static void Main()
    {
        string input = "Hellosrilanka";

        FindDuplicates(input);
        FindDuplicatesWithHashset(input);


    }

    public static void FindDuplicates(string input)
    {
        {
            Dictionary<char, int> map = new Dictionary<char, int>();

            foreach(char c in input)
            {
                //Checks if the character c already exists in the dictionary
                if (map.ContainsKey(c))
                {
                    map[c]++;
                }
                else
                {
                    map[c] = 1;
                }
            }

            foreach (var item in map)
            {
                Console.WriteLine(item);
                if (item.Value > 1)
                    Console.WriteLine($"Duplicate character: {item.Key}");
            }
        }
    }

public static void FindDuplicatesWithHashset(string input)
{
    {
        HashSet<char> seen = new HashSet<char>();
        HashSet<char> duplicates =new HashSet<char>();

        foreach(char c in input )
        {
            if (!seen.Add(c))
            {
                duplicates.Add(c);
            }
        }
        foreach (char c in duplicates)
        {
            Console.WriteLine(c);
        }
    }
}
    
}
```
