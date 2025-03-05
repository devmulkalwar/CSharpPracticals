# Index

| #  | Program Title      | Link            |
|----|-------------------|----------------|
| 1  | Program 1        | [Go to Program 1](#program-1)  |
| 2  | Program 2        | [Go to Program 2](#program-2)  |
| 3  | Program 3        | [Go to Program 3](#program-3)  |
| 4  | Program 4        | [Go to Program 4](#program-4)  |
| 5  | Program 5        | [Go to Program 5](#program-5)  |
| 6  | Program 6        | [Go to Program 6](#program-6)  |
| 7  | Program 7        | [Go to Program 7](#program-7)  |
| 8  | Program 8        | [Go to Program 8](#program-8)  |
| 9  | Program 9        | [Go to Program 9](#program-9)  |
| 10 | Program 10       | [Go to Program 10](#program-10) |
| 11 | Program 11       | [Go to Program 11](#program-11) |
| 12 | Program 12       | [Go to Program 12](#program-12) |
| 13 | Program 13       | [Go to Program 13](#program-13) |

---

# Program 1
## Write a program in Console application in c# to check whether given number is prime or not.
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
---
# Program 2
## Write a program in Console application in c# to check whether given number is armstrong number or not.
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
---
# Program 3
## Write a program in Console application in c# to demonstrate the difference between prefix and postfix forms of  ++.

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
---
# Program 4
## Write a program in Console application in c# to draw the structure (CO2)
⭐ <br>
⭐⭐<br>
⭐⭐⭐<br>
⭐⭐⭐⭐<br>
⭐⭐⭐⭐⭐

## 
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
---
# Program 5
## Write a program in Console application in c# to demonstrate passing  structure to function
### I)Pass by value       
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
### II)Pass by reference  
```cs
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

class Student
{
    string StudentName="";
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
}

```
---
# Program 6
## Write a program in Console application in c# to calculate volume of cube, cylinder and square box by using concept of method function overloading 
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
---
# Program 7
## Write a program in Console application in C# to sort the list of numbers using an array.
```cs
using System;

namespace Program5
{
    internal class Program
    {
        
        
        static void Main(string[] args)
        {
            int[] arr = new int[] { 5, 4, 3, 2, 1 };
            Array.Sort(arr);
            Console.WriteLine("Increasing order : ");
            foreach (int i in arr)
            {
                Console.WriteLine(i);
            }

            Array.Reverse(arr);
            Console.WriteLine("Decreasing order : ");
            foreach(int i in arr)
            {
                Console.WriteLine(i);
            }
        }
    }
}

```
---
# Program 8
## Write a program in Console application in c# to illustrate the concept of method overriding
```cs
using System;

class baseClass {

	// show() is 'virtual' here
	public virtual void show()
	{
		Console.WriteLine("Base class");
	}
}
class derived : baseClass
{
	
	//'show()' is 'override' here
	public override void show()
	{
		Console.WriteLine("Derived class");
	}
}

class GFG {
	// Main Method
	public static void Main()
	{
		baseClass obj;

		// 'obj' is the object
		// of class 'baseClass'
		obj = new baseClass();
		
		// it invokes 'show()'
		// of class 'baseClass'
		obj.show();
	
	// the same object 'obj' is now
		// the object of class 'derived'
		obj = new derived();
		
		// it invokes 'show()' of class 'derived'
		// 'show()' of class 'derived' is overridden
		// for 'override' modifier
		obj.show();
		
	}
}
```
---
# Program 9
## Write a program in Console application in c# to use multiple implementations of an interface
```cs
using System;

// Creating interfaces
interface firstinterface
{
	
	// Declaring Method
	void myfun1();
}

interface secondinterface
{
	
	// Declaring Method
	void myfun2();
}

interface thirdinterface
{
	
	// Declaring Method
	void myfun3();
}

// Here Int_Class implements three interfaces
class Int_Class : firstinterface, secondinterface, thirdinterface
{
	
	// Definition of Method
	public void myfun1()
	{
		Console.WriteLine("Hello! i am method of firstinterface");
	}
	
	// Definition of Method
	public void myfun2()
	{
		Console.WriteLine("Hello! i am method of secondinterface");
	}
	
	// Definition of Method
	public void myfun3()
	{
		Console.WriteLine("Hello! i am method of thirdinterface");
	}
}

class GFG{

// Driver code
public static void Main(String[] args)
{
	
	// Creating the objects of Int_Class class
	firstinterface obj1;
	secondinterface obj2;
	thirdinterface obj3;
	
	obj1 = new Int_Class();
	obj2 = new Int_Class();
	obj3 = new Int_Class();
	
	// Call the methods from firstinterface,
	// secondinterface, and thirdinterface
	obj1.myfun1();
	obj2.myfun2();
	obj3.myfun3();
}
}
```
---
# Program 10
## Write a program in Console application in c# to demonstrate jagged array.
```cs
using System;

class GFG {
	
	// Main Method
	public static void Main()
	{
		
		// Declare the Jagged Array of four elements:
		int[][] jagged_arr = new int[4][];

		// Initialize the elements
		jagged_arr[0] = new int[] {1, 2, 3, 4};
		jagged_arr[1] = new int[] {11, 34, 67};
		jagged_arr[2] = new int[] {89, 23};
		jagged_arr[3] = new int[] {0, 45, 78, 53, 99};

		// Display the array elements:
		for (int n = 0; n < jagged_arr.Length; n++) {

			// Print the row number
			System.Console.Write("Row({0}): ", n);

			for (int k = 0; k < jagged_arr[n].Length; k++) {

				// Print the elements in the row
				System.Console.Write("{0} ", jagged_arr[n][k]);
			}
			System.Console.WriteLine();
		}
	}
}
```
---
# Program 11
## Write a program in Console application in c# for boxing and unboxing
### Boxing
```cs
using System;
class GFG {

	// Main Method
	static public void Main()
	{

		// assigned int value
		// 2020 to num
		int num = 2020;

		// boxing
		object obj = num;

		// value of num to be change
		num = 100;

		System.Console.WriteLine
		("Value - type value of num is : {0}", num);
		System.Console.WriteLine
		("Object - type value of obj is : {0}", obj);
	}
}
```
### Unboxing
```cs
using System;
class GFG {
	// Main Method
	static public void Main()
	{
		// assigned int value
		// 23 to num
		int num = 23;
		// boxing
		object obj = num;

		// unboxing
		int i = (int)obj;

		// Display result
		Console.WriteLine("Value of ob object is : " + obj);
		Console.WriteLine("Value of i is : " + i);
	}
}
```
---
# Program 12
## Write a program in Console application in c# how to implement delegates
```cs
using System;
namespace GeeksForGeeks {
	
// declare class "Geeks"
class Geeks {
	
// Declaring the delegates
// Here return type and parameter type should
// be same as the return type and parameter type
// of the two methods
// "addnum" and "subnum" are two delegate names
public delegate void addnum(int a, int b);
public delegate void subnum(int a, int b);
	
	// method "sum"
	public void sum(int a, int b)
	{
		Console.WriteLine("(100 + 40) = {0}", a + b);
	}

	// method "subtract"
	public void subtract(int a, int b)
	{
		Console.WriteLine("(100 - 60) = {0}", a - b);
	}

// Main Method
public static void Main(String []args)
{
	
	// creating object "obj" of class "Geeks"
	Geeks obj = new Geeks();
	addnum del_obj1 = new addnum(obj.sum);
	subnum del_obj2 = new subnum(obj.subtract);

	// pass the values to the methods by delegate object
	del_obj1(100, 40);
	del_obj2(100, 60);

	// These can be written as using
	// "Invoke" method
	// del_obj1.Invoke(100, 40);
	// del_obj2.Invoke(100, 60);
             }
       }
}
```
---
# Program 13 
### Design a windows form in c# to calculate addition, subtraction, multiplication, division of two numbers
```cs
using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Windows.Forms;

namespace MyWinApp
{
    public partial class Form1 : Form
    {
        public Form1()
        {
            InitializeComponent();
        }

        private void btnAdd_Click(object sender, EventArgs e)
        {
            lblResult.Text = (Convert.ToInt32(txtInput1.Text) + Convert.ToInt32(txtInput2.Text)).ToString();
        }

        private void btnSub_Click(object sender, EventArgs e)
        {
            lblResult.Text = (Convert.ToInt32(txtInput1.Text) - Convert.ToInt32(txtInput2.Text)).ToString();
        }

        private void btnMul_Click(object sender, EventArgs e)
        {
            lblResult.Text = (Convert.ToInt32(txtInput1.Text) * Convert.ToInt32(txtInput2.Text)).ToString();
        }

        private void btnDiv_Click(object sender, EventArgs e)
        {
            lblResult.Text = (Convert.ToInt32(txtInput1.Text) / Convert.ToInt32(txtInput2.Text)).ToString();
        }       
    }
}
```
---
