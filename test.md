# Test

## C# questions

- What is a namespace? What is it good for and how do you define a namespace?
  A namespace is a container for classes and other non-method structures that should be logically grouped together, similar to how a class contains methods and properties that logically belong together.
  It's defined outside of classes, it's the outermost shell within a project.

- What is a constructor? When is it executed?
  A constructor is a method that creates a new instance of a class. It's executed upon creation of the aforementioned object.

- How do you implement inheritance in C#?
  After defining the parent class, you put " : <parent-class>" after the name of the child class.

- How do you prevent someone to inherit from a class?
  
- What is a readonly variable? Where you can assign value to readonly variables?
  A readonly variable is one whose value you can only access, not write to. You can assign value to readonly variables within the variable's class itself.

- Specify the available access modifiers in C# and briefly explain them
  Public: this means the method can be called from any class, anywhere in the program.
  Private: this means the method can only be called from within its class.
  Protected: ???

- Briefly explain the mechanism of exception handling
  A fatal runtime error is called an exception, and it happens when something occurs that causes the program to crash or stop executing. At the time of the event, if possible, the environment should
  log what type of exception occurred (IOException, IndexOutOfBounds, etc.) and show the user a (hopefully) brief message explaining what happened.

- What is the difference between an abstract class and an interface?
  An interface is a special type of class where you can define the name, return types, and parameters of shared methods but not the body of them. Each class that inherits from an interface
  must implement all interface methods and define their bodies. Unlike interfaces, abstract classes contained fully defined methods that child classes can directly inherit or override with a
  different body.

- How does using (...) {...} block work? What is the relation to interfaces and why?

- How IEnumerable<T> and IEnumerator<T> interfaces work? What properties and methods need to be implemented in classes that implements them? What are their relation to foreach loop?
  IEnumerable<T> and IEnumerator<T> are containers for collections (although not ICollections) of objects of the same type. The objects are not indexed, which is what you have to use a foreach loop instead of a for loop.
  Their purpose is to simply iterate over the items for whatever purpose you need to.

## Programming tasks

You can write your solutions in any language, you can even write pseudo code or using only your own words.
The point is not to make a perfectly running application, the point is the way you think!
Don't worry if you miss a semicolon or some parantheses. You might use the LINQ library for your solutions but none of the exercises require them

### Palindrome

Write a function which decides whether a text is palindrom(It's the same whether you read it forwards or backwards). E.g.: abba, rotator, stats.
You might assume that the input string is not null, the length is greater than 1 and less than one million. **Strive for the low memory complexity!**

Example:

```csharp
public bool IsPalindrome(string input)
{
    var result = true;
    for (int i = 0; i < Math.Ceiling(input.Length / 2); i++)
    {
        var compressed = input.Trim(" ");
        if (compressed[i] != compressed[compressed.Length - (1 + i)]
        {
            result = false;
        }
    }
    return result;
}

IsPalindrome("alma"); //false
IsPalindrome("görög"); //true
```

### Find The Duplicate

You have an array that contains strings. Every item in the array is unique except one which is present in the array exactly twice.
Write a function which finds the string that is present twice in the array.
You might assume that the input array is not null, the length is greater or equal to 2 and less than one million. **Strive for the low time complexity!**

Example: 

```csharp
public string FindTheDuplicate(string[] input)
{ 
     return input.GroupBy(s => s).Where(s => s.Count == 2).First();        
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
public void CountTheWords(string crazyLongString)
{ 
    var punctuation = new char[] { punctuation marks and space };
    var words = crazyLongString.ToLower().Split(punctuation).GroupBy(w => w);
    foreach(var word in words)
    {
        ConsoleWriteLine(word + ":" word.Count());
    }
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
The output is the following:
0
apple
System.GenericType.blah

This is because DoSomething doesn't pass anything back to Main, so the updated values aren't being used.

## SQL

- What is the PRIMARY KEY?
  The primary key is the unique identifier for each entry in a table.
- What is the difference between CLUSTERED INDEX and NONCLUSTERED INDEX?
  No idea.
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
It's possible that only some of the entries would get updated, so if you tried to run this again afterwards some employees would get a 21% raise while others would only get 10%.

## Web and HTTP

- Specify the existing HTTP request methods and describe their usage!
  Get - retrieve information from an endpoint.
  Post - send/update information at an endpoint.
  Put - send new information to an endpoint.
  Delete - delete some information that's accessed through an endpoint (like a database entry).
  Update - 
- What are the groups of HTTP response status codes? Write an example for each group!
