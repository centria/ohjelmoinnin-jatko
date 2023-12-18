---
title: "Random"
nav_order: 111
hidden: false
---

# Random

Encryption algorithms, machine learning and making computer games less predictable all require randomness. We can model randomness using random numbers. C# offers ready-made **System.Random** class for creating random numbers. An instance of the Random class can be used as follows:

```cpp
namespace Exercise001
{
  using System;
  
  class Program
  {
    public static void Main(String[] args)
    {
      Random ladyLuck = new Random(); // create Random object ladyLuck

      for (int i = 0; i < 10; i++)
      {
        // Draw and print a random number
        int randomNumber = ladyLuck.Next(10);
        Console.WriteLine(randomNumber);
      }
    }
  }
}
```

Above we create an instance of the Random class. It has **Next** method, which gets an integer as a parameter. The method returns a random number between [0, integer[ or 0..(integer -1).

The program output is not always the same. One possible output is the following:

```console
2 
9 
4 
3 
4 
5 
6 
0 
7 
8
```

We can use the **Next** method to create diverse randomness. For example, we might need a program to give us a temperature between \[-30,50\]. We can do this by first creating random a number between 0 and 80 and then subtracting 30 from it.


```cpp
Random weatherMan = new Random();
int temperature = weatherMan.Next(81) - 30;
Console.WriteLine(temperature);
```

A more reasonable way to do this, how ever, is to use **Random.Next(lowerLimit, upperLimit)**, like follows:

```cpp
Random weatherMan = new Random();
int temperature = weatherMan.Next(-30, 51);
Console.WriteLine(temperature);
```

<Note> The lowerLimit is inclusive but the upperLimit is always exclusive, so we are still getting random between -30 and 50!</Note>

A Random object can also be used to create random doubles. These can for example be used for calculating probabilities. Computers often simulate probabilities using doubles between \[0..1\].

The **NextDouble** method of the Random class creates random doubles. Let's assume the weather follows these probabilities:

* There is 0.1 probability it rains (10%)
* There is 0.3 probability it snows (30%)
* There is 0.6 probability the sun shines (60%)

Let's create a weather forecast using these probabilities.

```cpp
namespace Exercise001
{
  using System;

  public class WeatherMan
  {
    private Random random;

    public WeatherMan()
    {
      this.random = new Random();
    }

    public string Forecast()
    {
      double propability = this.random.NextDouble();

      if (propability <= 0.1)
      {
        return "It rains";
      }
      else if (propability <= 0.4)
      { // 0.1 + 0.3
        return "It snows";
      }
      else
      { // rest, 1.0 - 0.4 = 0.6
        return "The sun shines";
      }
    }
  }
}
```

Let's now add a main which uses the WeatherMan class.

```cpp
namespace Exercise001
{
  using System;
  using System.Collections.Generic;

  class Program
  {
    public static void Main(string[] args)
    {
      WeatherMan forecaster = new WeatherMan();

      // save days of the week to a list
      List<string> days = new List<string>();
      days.Add("Mon");
      days.Add("Tue");
      days.Add("Wed");
      days.Add("Thu");
      days.Add("Fri");
      days.Add("Sat");
      days.Add("Sun");

      Console.WriteLine("Next week's weather forecast:");

      foreach (string day in days)
      {
        string weatherForecast = forecaster.Forecast();

        Console.WriteLine(day + ": " + weatherForecast + ".");
      }
    }
  }
}
```

One output could be

```console
Next week's weather forecast:
Mon: The sun shines.
Tue: It snows.
Wed: The sun shines.
Thu: The sun shines.
Fri: The sun shines.
Sat: It snows.
Sun: It snows.
```

We can predict how computers work, because they slavishly execute any command we give them. Is a random number generated by a computer then really random?

Random numbers used by computer programs are typically pseudorandom. They seem like random numbers, but in reality they follow some algorihmically created series of numbers. Most of the time pseudorandom is good enough -- for example the user will not notice any difference when YouTube random play is pseudorandom. On the other hand if random numbers are used for scientific calculations, using a weak pseudorandom number generator can lead to questionable results. One example is IBM's [**RANDU**](https://en.wikipedia.org/wiki/RANDU) which was used for a short while in the 1960's.

All randomness in computer programs is not pseudorandom. Programs aiming for stronger randomness use, among other things, real life random phenomena to generate random numbers. For example space radiation or [**lava lamps**](https://www.cloudflare.com/learning/ssl/lava-lamp-encryption/) are thought to be random phenomena.


You can read more about randomness from [**https://www.random.org/randomness/**](https://www.random.org/randomness/).


# Exercises

<Exercise title={'001 Dice'}>

The exercise template contains a class **Die**, which has the following body:

```cpp
namespace Exercise
{
  using System;
  public class Die
  {
    private Random random;
    private int numberOfFaces;

    public Die(int numberOfFaces)
    {
      this.random = new Random();
      // Initialize the value of numberOfFaces here
    }
    public int ThrowDie()
    {
      // generate a random number which may be any number
      // between one and the number of faces, and then return it
      return 0;
    }
  }
}
```

Modify the class, such that the constructor **Die(int numberOfFaces)** creates a new die-object with the given number of faces (i.e. the number of "sides" with a number). Also, modify the method **ThrowDie** so it returns the result of a random throw of the die, which should be a value withing the range 1 ... number of faces.

The following is a Main program for testing the die:

```cpp
Die die = new Die(6);

for (int i = 0; i < 10; i++)
{
  Console.WriteLine(die.ThrowDie());
}
```

The output could be as follows:

```console
5
3
2
6
4
2
4
1
2
5
```

</Exercise>

<Exercise title={'002 Lottery Row'}>

Your assignment is to complete the class **LotteryRow**, which is used to draw the week's winning numbers. The numbers are in range 1--40, and 7 numbers will be drawn in total. In other words, a lottery row consists of seven different numbers that are all in range 1--40.

We wish to implement the following functions in the class:

* the constructor **LotteryRow** creates a new LotteryRow object that contains new randomized numbers.
* the method **Numbers** returns the drawn lottery numbers of this lottery row
* the method **ContainsNumber** tells whether the given number is included in the drawn numbers
* the method **RandomizeNumbers** randomizes new numbers for the lottery row.  

The basic structure of the class is as follows:

```cpp
namespace Exercise
{
  using System;
  using System.Collections.Generic;

  public class LotteryRow
  {
    private List<int> numbers;

    public LotteryRow()
    {
      this.RandomizeNumbers();
    }

    public List<int> Numbers()
    {
      return this.numbers;
    }

    public bool ContainsNumber(int number)
    {
      // Tests whether the number is already among the randomized numbers
      return false;
    }

    public void RandomizeNumbers()
    {
      // initialize the list for numbers
      this.numbers = new List<int>();
      // Implement the randomization of the numbers by using the method ContainsNumber() here
    }

  }
}
```

The following Main program is supplied in the exercise base:

```cpp
LotteryRow row = new LotteryRow();
List<int> lotteryNumbers = row.Numbers();

Console.WriteLine("Lottery numbers:");
foreach (int number in lotteryNumbers)
{
  Console.Write(number + " ");
}

Console.WriteLine("");
```

Here are a few possible outputs of the program:

```console
Lottery numbers:
2 10 14 15 22 26 33
```


```console
Lottery numbers:
6 8 10 26 31 35 40
```

<Note>The same number can only appear once in a lottery row. Remember to also Sort() your list at the end of RandomizeNumbers.</Note>


</Exercise>