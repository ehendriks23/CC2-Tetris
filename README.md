# __CC2, Tetris Project__

# HEAVY DISCLAIMER
I followed a tutorial for most of the code once I realized how tough this project was for a complete beginner like me. 
The tutorial is called "TETRIS IN UNITY - TUTORIAL" by Clipper, https://www.youtube.com/watch?v=nlFbKkoyJIs&t=2113s&ab_channel=Clipper.
I also realized my idea isn't entirely original (having Tetrominos made up of 5 blocks, instead of 4) as mid-development I realized something called "Pentris" exists, which is exactly that idea.
I did handwrite all of the code and I also ran into a few obstacles, because of mistakes I made, alternative lines of code I wrote, which often didn't end up working. 
My major obstacle came from the fact that the video explains how to make normal Tetris, not "Pentris", but overall it wasn't that big of an issue.

# Process Documentation

## Iterative Development:
I don't have any screenshots of past bugs or failures, however I remember at the start I had a lot of issues with Unity and Vis Studio. The one that confused me the most was when Unity and Visual Studio's Intellisense wasn't properly integrated, so none of the Unity parts of my code were working. For example, in the code, you'll find a lot of "gameObject"'s present. A gameObject is basically _anything_ in Unity, so being able to alter it in the code is incredibly useful. However, when the Unity/Vis Studio integration wasn't working, all of the gameObject's in the code would be rendered obsolete. This wasn't a code problem, so much a software problem. I watched a 5 step video on how to get Intellisense to work properly.

A more practical issue I ran into was when Unity loaded the position of my Tetromino blocks somewhere completely seperate from the actual sprites. So in the code, everything would be working fine, but the player wouldn't be able to see the actual Tetromino. I ended up deleted all my sprites and some of the code attached to them and recreated everything, which somehow ended up working. To this day, I'm still not quite sure what changed.

## Incremental Development:
The first of my three stages was when I created a single sprite and had it fall to the ground at a constant rate. This was when I just began using Unity, so it felt like a big accomplishment.

The second stage was creating rotations. All in all it's a pretty simple line of code along the lines of 
```
if (Input.GetKeyDown(KeyCode.Space))
            {
                rig.transform.eulerAngles += new Vector3(0, 0, 90);
```
However, by that time I had created all my Tetrominos, created left and right movement, manual dropping and wall and floor collisions.

The last stage would be having the feature of clearing lines. The big difference between the second and third stage would be collision between Tetrominos, which lead to the ability to clear a line, a distinct feature of Tetris.

## Feedback:


## _6th of December:_

Because time is running out on the project and I keep running into roadblocks, I started following a tutorial for normal Tetris, however I'll still have to adjust everything to my liking and my modifications to the game. I'll be sure to make it clear what I had to change in order for the game to function. 
The video I'm following is: "How to make Tetris in Unity (Complete Tutorial) https://www.youtube.com/watch?v=ODLzYI4d-J8"

### _Reflection Questions for 06/12/2021_
1. What was your goal for this deliverable, as defined on your Learning Plan?
As stated in my previous reflection questions, I've just been ignoring my Learning Plan. So far I'm just following the video and working on the "Tetromino Data" and "Spawning/Setting" part of the video.
2. Did you meet this goal?
Yes, though it's not really a goal but just something I'm following for now.
3. What needs to happen for you to stay on schedule from this point forward?
I need to thoroughly keep working during the Winter Break.

## _29th of November:_

### _Feedback Plan_
For my feedback, I'll probably just send the game to a couple of friends and have them play test for as long as they want (maybe a deadline of a day or two?).

### _Reflection Questions for 29/11/2021_
1. What was your goal for this deliverable, as defined on your Learning Plan?
As stated in my previous reflection questions, I've just been ignoring my Learning Plan. In my mind I also haven't really come up with a different goal.
2. Did you meet this goal?
Because I didn't have a goal, I'll just state what I've done. So far, I've created the all different sprites and a general playing area. I'm still struggling with the implementation of the sprites. 
3. What needs to happen for you to stay on schedule from this point forward?
I'll work a lot during Winter Break at home, since I'm not going anywhere and it's also just a lot more comfortable to work at home instead of at school.


## _16th of November:_
I continued to work a bit on CodeAcademy, but nothing was that notable. Most of the time, I instead tried figuring out Unity. There was actually a problem with that for a bit because Unity has some built in features, separate from C#, that just weren't working for me. Eventually I figured it out, so now it's working.

### _Reflection Questions for 16/11/2021_
1. What was your goal for this deliverable, as defined on your Learning Plan?
After having discussed with Mr. Bowman, I haven't really been sticking to my Learning Plan. In my mind, my goal was to just having something falling moving in Unity. 
2. Did you meet this goal?
I met the one I set in my mind, not the one on the Learning Plan.
3. What needs to happen for you to stay on schedule from this point forward?
With Winter Break coming soon, I can do a lot of work then. During class, however, now that I'm working with sprites and GameObjects it's quite annoying and tough to do a lot of work, because I'm working on just my laptop. My plan from now is to finally start the Tetris game.


## _12th of October:_
I haven't really focused that much on learning C# or followed the lessons step-by-step because I felt like what I was learning wouldn't be _that_ useful for what I want to create. Instead I skipped a few lessons and learned what I felt was truly necessary.

### _Reflection Questions for 12/10/2021_
1. What was your goal for this deliverable, as defined on your Learning Plan?
My goal was to have "A general play field, Tetris Sprites and Gravity Physics" all completely coded in Unity.
2. Did you meet this goal?
I did not, sort of. I haven't properly coded anything yet, but instead I wrote all necessary elements of a Tetris game into a document I made. It isn't in proper coding syntax, but the ideas are all there.
3. What happens for you to stay on schedule from this point forward?
From now on I should start actually coding my project, which I have yet to start. On top of that, I should also start using familiarizing myself with Unity.

### _Learning_
https://watch.screencastify.com/v/CALvv4invHaaNdBaoiru

### Examples
_Ex. 1:_ I learned how to define a class, which is pretty simple but I was stuck for a while because I simply didn't realise there had to be a seperate .cs file. This example is of a class with 4 brief lines of code, called fields.

```
Forest.cs
using System;

namespace BasicClasses
{
  class Forest
  {
    public string name;
    public int trees;
    public int age;
    public string biome;
  }
}
```
In program.cs, it connects the fields written in Forest.cs.
```
using System;

namespace BasicClasses
{
  class Program
  {
    static void Main(string[] args)
    {
      Forest f = new Forest();
      f.name = "Amazon Rain Forest";
      f.trees = 100000000;
      f.age = 3000;
      f.biome = "Jungle";
      Console.WriteLine(f.name);
    }
  }
}
```
_Ex. 2:_ I also fully learned about loops and different types of loops, which I really need when making Tetris. The following is a for loop, which will repeat "CreateTemplate;" 17 times, which is visible in line 9. The entire piece of code basically creates an automatic template which includes important announcements for each week.
```
using System;

namespace ForLoop
{
  class Program
  {
    static void Main(string[] args)
    { 
      for (int i = 0; i < 17; i++)
      {
        CreateTemplate(i);
      }

    }
    
    static void CreateTemplate(int week)
    {
      Console.WriteLine($"Week {week}");
      Console.WriteLine("Announcements: \n \n \n ");
      Console.WriteLine("Report Backs: \n \n \n");
      Console.WriteLine("Discussion Items: \n \n \n");
    }
    
    
  }
}
```


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
https://watch.screencastify.com/v/CALvv4invHaaNdBaoiru

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
