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
2. Collection expressions
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
4. ref readonly parameters
5. Default lambda parameters
6. Alias any type
7. Inline arrays
8. Experimental attribute
9. Interceptors

