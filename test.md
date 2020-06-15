# Test

## C# questions

- What is a namespace? What is it good for and how do you define a namespace?
- What is a constructor? When is it executed?
- How do you implement inheritance in C#?
- How do you prevent someone to inherit from a class?
- What is a readonly variable? Where you can assign value to readonly variables?
- Specify the available access modifiers in C# and briefly explain them
- Briefly explain the mechanism of exception handling
- What is the difference between an abstract class and an interface?
- How does using (...) {...} block work? What is the relation to interfaces and why?
- How IEnumerable<T> and IEnumerator<T> interfaces work? What properties and methods need to be implemented in classes that implements them? What are their relation to foreach loop?

## Programming tasks

You can write your solutions in any language, you can even write pseudo code or using only your own words.
The point is not to make a perfectly running application, the point is the way you think!
Don't worry if you miss a semicolon or some parantheses. You might use the LINQ library for your solutions but none of the exercises require them

### Palindrom

Write a function which decides whether a text is palindrom(It's the same whether you read it forwards or backwards). E.g.: abba, rotator, stats.
You might assume that the input string is not null, the length is greater than 1 and less than one million. **Strive for the low memory complexity!**

Example:

```csharp
public bool IsPalindrom(string input) {

}

IsPalindrom("alma"); //false
IsPalindrom("görög"); //true
```

### Find The Duplicate

You have an array that contains strings. Every item in the array is unique except one which is present in the array exactly twice.
Write a function which finds the string that is present twice in the array.
You might assume that the input array is not null, the length is greater or equal to 2 and less than one million. **Strive for the low time complexity!**

Example: 

```csharp
public string FindTheDuplicate(string[] input) { 
        
}

string[] fruitBasket = new string[] { "apple", "banana", "coconut", "durian", "banana", "elderberry", "fig", "grapefruit" };
FindTheDuplicate(fruitBasket); //should return banana
```

### Count The Words

You have a long string that has some meaning on a real language. For example a whole novel in a single string.
Write a function that counts the occurence of each word inside the string and writes them to the output in the following format: `word: number of occurences`
You might assume that the input is not null and not empty. The order of the words on the ouput does not matter.
The solution might be case insensitive, you don't have to differentiate bwetween capital and non-capital letters.
The punctuation marks and line endings are not part of the words!

Example:

```csharp
public void CountTheWords(string crazyLongString) { 
        
}

string boci = "Boci, boci tarka, se füle, se farka.";
CountTheWords(boci);

//Output:
//boci:2
//tarka:1
//se:2
//füle:1
//farka:1
```

### What Is The Output

What is the output of the following C# application? Explain your solution!

```csharp
using System;

namespace ConsoleApp2
{
  public class Person
  {
    public string Firstname { get; set; }

    public string Lastname { get; set; }

    public override string ToString() => $"{Firstname} {Lastname}";
  }

  class Program {
    static void Main(string[] args) 
    {
        int i = 0;
        string s = "apple";
        Person p = new Person{ Firstname = "Jonh", Lastname = "Doe" };
        
        DoSomething(i, s, p);
        
        Console.WriteLine(i);
        Console.WriteLine(s);
        Console.WriteLine(p);
    }
    
    static void DoSomething(int i, string s, Person p)
    {
        i = 5;
        s += "banana";
        p.LastName = "Rambo";
    }
  }
}

```

## SQL

- What is the PRIMARY KEY?
- What is the difference between CLUSTERED INDEX and NONCLUSTERED INDEX?
- There is a table called `Employees`. Let's assume that the columns exist and they have the right data type.
What is going to happen if we execute the script and we destroy the database connection during the execution? What are the possible problems that might occure?

```sql
BEGIN TRANSACTION

UPDATE Employees
SET Salary = Salary * 1.1
WHERE 
	Salary < 250000
	AND IsActiveEmployee = 1
```

## Web and HTTP

- Specify the existing HTTP request methods and describe their usage!
- What are the groups of HTTP response status codes? Write an example for each group!
