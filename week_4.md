# Week 4 Code Review

In this document, I will provide an exemple of code review from the code review challenge that best describes my level of code review in C#. As I've never coded in C# before, I am lacking in understanding of the language.

## Code review #3: 'A classic model'

### Code

```csharp
class Car
{
    public string model;

  // Class constructor
    public Car()
    {
        model = "Mustang"; // Set the initial value for model
    }

    static void Main(string[] args)
    {
        Car Ford = new Car();
        Console.WriteLine(Ford.model);
    }
}
```

### Code Review

There doesn't seem to be an issue with the naming of classes and functions, also the name of the constructor has to be the same as the class' (that was the only doubt I had, but after few researches, it is how it's supposed to be). Other than that, with basic knowledge of C# the code seems self explainatory and doesn't need more comentary than what it already has.

While the code on its own works, this line
```csharp
    public string model;
```
could be changed to suit better coding habits in C# as I came across online, regarding encapsulation and properties.

### Modified Code

- 1st option:

```csharp
class Car
{
    public string model {get;set;}
    
  // Class constructor
    public Car()
    {
        model = "Mustang"; // Set the initial value for model
    }

    static void Main(string[] args)
    {
        Car Ford = new Car();
        Console.WriteLine(Ford.model);
    }
}
```
- 2nd option:

```csharp
class Car
{
    public string model { get; set; } = "Mustang";

    static void Main(string[] args)
    {
        Car Ford = new Car();
        Console.WriteLine(Ford.model);
    }
}
```

### Modified Code Explained

- 1st option: I replaced the single ';' by '{get;set;}', which permits changes of properties from public to private. It will be easier to change in the futur if needed and is overall a good coding habit in C#. To change a propertie we will just need to replace 'set' by 'private set'.

- 2nd option: Here I used an auto-implemented property with an initial value directly, to reduce the number of lines in the code and make it smoother. This option works because there is only one information in the constructor, which will not often be the case. I still recommend using the constructor for good coding habit. 