# __CC2, Tetris Project__

## _26th of September:_
With all the new (harder) topics and subjects being built upon eachother and really piling up, this past week has been slower than before.
### _Reflection Questions for 26/09/2021_
1. What was your goal for this deliverable, as defined on your Learning Plan?
My goal was to have the lesson "Arrays and Loops" on Codeacademy (the program I've been using to learn C#) completed.
2. Did you meet this goal?
I did not.
3. What needs to happen for you to stay on schedule from this point forward?
According to the timeline, I should start working on the foundation of the game, but I still don't feel I have a good grasp of C#. Especially because I haven't yet completed the "Loops" lesson, which I already know is going to be vital to my project. I think I'll spend the next few lessons still working on learning C#.

### _Learning_
{insert video link here}

#### *Examples*
_Ex. 1:_ This is an example of _Lambda Expressions_, which passes a method as an argument. The result is the Console printing "At least one space rock has reached the Earth's surface!", because _makesContact_ is true. _makesContact_ is set to true because it's objective is to check if "meteoroid", "meteor" or "meteorite" exist, which it does because of the _Lamba Expression_. The argument is on line 11, while the method is on line 19.
```
using System;

namespace AlternateExpressions
{
  class Program
  {
    static void Main(string[] args)
    {
      string[] spaceRocks = {"meteoroid", "meteor", "meteorite"};
      
      bool makesContact = Array.Exists(spaceRocks, (string s) => s == "meteorite");
      
      if (makesContact)
      {
        Console.WriteLine("At least one space rock has reached the Earth's surface!");
      } 
    } 
    
    static bool HitGround(string s)
    {
      return s == "meteorite";
    }
  }
}
```
_Ex. 2:_ The following is an example of an _Array_ (line 11). It's essentially a list of things and I can use different properties to find and exploit information from the list. Line 7, for example, states that _if_ the length of the _array_ is equal to 8, the console will print a message. There are also 2 more messages concerning the length of the _array_.
```
using System;

namespace ArrayLength
{
  class Program
  {
    static void Main(string[] args)
    {
      string[] summerStrut;

      summerStrut = new string[] { "Juice", "Missing U", "Raspberry Beret", "New York Groove", "Make Me Feel", "Rebel Rebel", "Despacito", "Los Angeles", "Bandit" };
      if (summerStrut.Length == 8)
      {
        Console.WriteLine("summerStrut Playlist is ready to go!");
      }
      else if (summerStrut.Length > 8)
      {
        Console.WriteLine("Too many songs!");
      }
      else if (summerStrut.Length < 8)
      {
        Console.WriteLine("Add some songs!");
      }

    
    }
  }
}

```

## _20th of September:_
So far I have been learning C# using Codeacademy and I think it's going well, albeit a bit slower than I anticipated.
### _Reflection Questions for 20/09/2021_
1. What was your goal for this deliverable, as defined on your Learning Plan?
Because I didn't know how fast and comfortable I would be with C#, I hadn't set a concrete goal. Now I've added one and also achieved it. I added "Understanding the logic of C#" as my goal, which I feel I completed when I finished the "logic" unit on Codeacademy.
2. Did you meet this goal?
I did.
3. What needs to happen for you to stay on schedule from this point forward?
From now on, if I want to have the full game completed by the end of the semester, I'll also have to start thinking about how to actually build and design a game like that, aside from just learning C#.

### _Learning_
Starting off with the most basic of basic: printing text. Honestly it was really annoying to type out **"Console.WriteLine();"** every time instead of just "print()" like I learned with Python. I'm used to it now, however. 
I also learned about different **data types**, which are similar to Python, though there are some differences. There's "string" and "int" which are the most fundamental, but then you also have "double" which is for numbers with decimals. The first time I saw it, it really caught me off guard, because I thought it would double a value.
My goal was understanding the logic operators that C# uses, which was quite easy. They're incredibly similar to Python, just slightly more tedious, I'd say. You have the same things like ==, !=, <=, >= and simple commonly used Math operators. Another "Logic" thing would be the **if/else statements** which are pretty familiar, again from Pyhthon. As useful as this *can* be, I don't think I'll be using it much for my project. The last 2 "Logic" things in Codeacademy were pretty foreign to me. Namely **Switch Statements** and **Ternary Operators**. Switch statements make the code a lot more compact and seems incredibly useful, but still not for my project. Instead of changing the value of the variable, you can just go: 
```
switch (variable name)
{
case "new variable name"
// some code that is dependant on variable name
break;
case "new variable name"
// some code that is dependant on variable name
break;
}
```
and you can do make a new case as much as you want.

Ternary Operators return a value depending on the result of a boolean logic statement. It might be useful for collisions or swapping Tetris pieces, but I'm not sure how valuable this can be yet.

The newest thing I learned is the basic of **Methods**. It feels weird because I've been writing in the Main Method the entire time and just ignored anything outside of the main brackets. So being able to make a new area where I can write whatever I want and use paramaters as a shortcut, it feels really weird.

#### *Examples*
```
using System;

namespace ReviewMethodCallsAndInput
{
  class Program
  {
    static void Main(string[] args)
    {
      NamePets("Bobby", "Johnny");
      VisitPlanets(numberOfPlanets: 3);
    }
    
    static void NamePets()
    {
      Console.WriteLine("Aw, you have no spacefaring pets :(");
    }
    
    static void NamePets(string pet1, string pet2)
    {
      Console.WriteLine($"Your pets {pet1} and {pet2} will be joining your voyage across space!");
    }  
    
    static void NamePets(string pet1, string pet2, string pet3)
    {
      Console.WriteLine($"Your pets {pet1}, {pet2}, and {pet3} will be joining your voyage across space!");
    }  
    
    static void VisitPlanets(
      string adjective = "brave",
      string name = "Cosmonaut", 
      int numberOfPlanets = 0,
      double gForce = 4.2)
    {
      Console.WriteLine($"Welcome back, {adjective} {name}.");
      Console.WriteLine($"You visited {numberOfPlanets} new planets...");
      Console.WriteLine($"...while experiencing a g-force of {gForce} g!");
    }
    
  }
}
```
```
using System;

namespace IfElseStatement
{
  class Program
  {
    static void Main(string[] args)
    {
      int people = 12;
      string weather = "bad";

      if (people <= 10 && weather == "nice")
      {
        Console.WriteLine("SaladMart");
      }
      else
      {
        Console.WriteLine("Soup N Sandwich");
      }

    }
  }
}
```
