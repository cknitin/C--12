# C#-12
All new C# 12 features

## 1. Primary constructors

```
public class Employee(string firstName, string lastName)
{
    public void ShowEmployeeName()
    {
        Console.WriteLine(lastName + ", " + firstName);
    }
}
```

## 2. Collection expressions

```
 List<int> numbers = new List<int> { 1, 2, 3, 4, 5 };
 foreach (var number in numbers)
 {
     Console.WriteLine(number);
 }

 // Create an array:
 int[] a = [1, 2, 3, 4, 5, 6, 7, 8];

 // Create a list:
 List<string> b = ["one", "two", "three"];

 // Create a span
 Span<char> c = ['a', 'b', 'c', 'd', 'e', 'f', 'h', 'i'];

 // Create a jagged 2D array:
 int[][] twoD = [[1, 2, 3], [4, 5, 6], [7, 8, 9]];

 // Create a jagged 2D array from variables:
 int[] row0 = [1, 2, 3];
 int[] row1 = [4, 5, 6];
 int[] row2 = [7, 8, 9];
 int[][] twoDFromVariables = [row0, row1, row2];
```

## 3. ref readonly parameters

```
public struct Point
{
    public int X { get; }
    public int Y { get; }

    public Point(int x, int y)
    {
        X = x;
        Y = y;
    }

    public void PrintCoordinates(ref readonly Point point)
    {
        // We can read the values but cannot modify them
        Console.WriteLine($"X: {point.X}, Y: {point.Y}");
    }
}

 Point point = new Point(5, 10);
 point.PrintCoordinates(ref point);
```

## 4. Default lambda parameters

```
public void ShowDefaultLambdaParameters()
{
    var IncrementBy = static (int source = 20, int increment = 1) =>
    {
        return source + increment;
    };

    Console.WriteLine(IncrementBy(10));     // 11
    Console.WriteLine(IncrementBy(10, 20)); // 30
    Console.WriteLine(IncrementBy()); // 21
}
```

## 5. Alias any type

```
using MyAlias = System.Console;

namespace CSharp12._5._Alias_any_type
{
    using x1 = int;
    internal class Demo4
    {
        public void PrintMessage()
        {
            x1 a = 10;
            int b = 20;

            MyAlias.WriteLine("Sum = a + b - ", a + b);
        }
    }
}
```

## 6. Inline arrays

traditional approach

```
int sum = 0;
int[] numbers = new int[] { 1, 2, 3, 4, 5 };
for (int i = 0; i < numbers.Length; i++)
{
    sum += numbers[i];
}
```

inline arrays

```
int sum = Array.Sum([1, 2, 3, 4, 5]);
```


```
 public class Demo5
 {
     [System.Runtime.CompilerServices.InlineArray(10)]
     public struct Buffer
     {
         private int _element0;
     }

     public void ShowInlineArray()
     {
         var buffer = new Buffer();
         for (int i = 0; i < 10; i++)
         {
             buffer[i] = i;
         }

         foreach (var i in buffer)
         {
             Console.WriteLine(i);
         }
     }

 }
```

## 7. Experimental attribute

```
 [Experimental(diagnosticId: "Test001")]
 public class Demo6
 {
     public void ExperimentalMethod()
     {
         Console.WriteLine("This is a Experimental Method new feature in C# 12");
     }
 }

 #pragma warning disable Test001
     Demo6 demo6 = new Demo6();
     demo6.ExperimentalMethod();
 #pragma warning restore Test001

```

## 8. Interceptors

