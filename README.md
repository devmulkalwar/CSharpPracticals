```cs
using System;

public class HelloWorld
{
    public static bool isPrime(int n){
        if(n<0){
            Console.WriteLine("Number is not a prime number ");
            return false;
        }
        for(int i=2;i<n;i++){
            if(n%i==0){
                return false;
            }
        }
        
        return true; 
        
    }
    public static void Main(string[] args)
    {
        int n = 0;
        Console.WriteLine("Enter a number : ");
        
        string input = Console.ReadLine();
        n = int.Parse(input); 

        string result = isPrime(n) ? "Number is a prime number" : "Number is not a prime number";
        Console.WriteLine(result);
    }
}
```
```cs
using System;

public class HelloWorld
{
    public static void ArmStrong(int n){
        if(n>=0&&n<10){
             Console.WriteLine("Armstrong number");
             return;
        }
        int org = n;
        int temp = n;
        int sum =0;
        int digits =0 ;
        while(temp>0){
            digits++;
            temp=temp/10;
        }
        
        Console.WriteLine(digits);
        
        while(n>0){
            int a = n%10;
            sum = sum + (int)Math.Pow(a,digits);
            n=n/10;
        }
        
        Console.WriteLine(sum);
        if(sum == org){
            Console.WriteLine("Armstrong number");
        }else{
            Console.WriteLine("Not a armstrong number");
        }
    }
    public static void Main(string[] args)
    {
        int n = 0;
        Console.WriteLine("Enter a number : ");
        
        string input = Console.ReadLine();
        n = int.Parse(input); 

        Console.WriteLine("You entered: " + n);
        
        ArmStrong(n);
    }
}
```
```cs
using System;

public class PrePostDemo
{
    public static void Main()
    {
        int x, y;
        int i;

        x = 1;
        Console.WriteLine("Series generated using Postfix y = x + x++;");
        for (i = 0; i < 10; i++)
        {

            y = x + x++; // postfix ++ 

            Console.WriteLine(y + " ");
        }
        Console.WriteLine();

        x = 1;
        Console.WriteLine("Series generated using Prefix y = x + ++x;");
        for (i = 0; i < 10; i++)
        {

            y = x + ++x; // prefix ++ 

            Console.WriteLine(y + " ");
        }
        Console.WriteLine();

    }
}
```
```cs
using System;

public class HelloWorld
{
    public static void Main(string[] args)
    {
        int n = 0;
        Console.WriteLine("Enter a number : ");
        
        n = int.Parse(Console.ReadLine()); 
        
        for(int i=0;i<n;i++){
            for (int j=0;j<n;j++){
                if(i>=j){
                    Console.Write("* ");
                }
            }
            Console.WriteLine("");
        }
    }
}
```
```cs
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Practical5
{
    internal class Program
    {
        static void ChangeValue(int x)
        {
            x = 200;
            Console.WriteLine(x);
        }
        static void Main(string[] args)
        {
            int i = 100;
            Console.WriteLine(i);
            ChangeValue(i);
            Console.WriteLine(i);
        }
    }
}

```
```cs
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

static void ChangeReferenceType(Student std2)
{
    std2.StudentName = "Steve";
}


static void Main(string[] args)
{
    Student std1 = new Student();
    std1.StudentName = "Bill";
    
    ChangeReferenceType(std1);


    Console.WriteLine(std1.StudentName);
}
```
```cs
using System;

class VolumeCalculator
{
    public static double CalculateVolume(double side)
    {
        return Math.Pow(side, 3);
    }

    public static double CalculateVolume(double radius, double height)
    {
        return Math.PI * Math.Pow(radius, 2) * height;
    }

    public static double CalculateVolume(double length, double width, double height)
    {
        return length * width * height;
    }

    static void Main()
    {
        Console.WriteLine("Volume Calculator");

        double cubeSide = 3;
        double cylRadius = 2, cylHeight = 5;
        double boxLength = 4, boxWidth = 3, boxHeight = 6;

        Console.WriteLine($"Volume of Cube (side {cubeSide}): {CalculateVolume(cubeSide):F2}");
        Console.WriteLine($"Volume of Cylinder (radius {cylRadius}, height {cylHeight}): {CalculateVolume(cylRadius, cylHeight):F2}");
        Console.WriteLine($"Volume of Rectangular Box (length {boxLength}, width {boxWidth}, height {boxHeight}): {CalculateVolume(boxLength, boxWidth, boxHeight):F2}");

        Console.WriteLine("Press any key to exit...");
        Console.ReadKey();
    }
}
```