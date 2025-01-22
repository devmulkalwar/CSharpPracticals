```C#
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
```C#
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
