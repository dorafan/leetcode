[toc]



### **Java Coding Interview Questions** 

Apart from having good knowledge about concepts of Java programming, you are also tested for your skills in coding in Java programming language. Given below are Java Coding Interview Questions that are relevant for freshers and are quite popular amongst Java programming interviews.

#### **Question: Take a look at the two code snippets below:**

**i.**

```java
class Adder {
Static int add(int a, int b)
{
return a+b;
}
Static double add( double a, double b)
{
return a+b;
}
public static void main(String args[])
{
System.out.println(Adder.add(11,11));
System.out.println(Adder.add(12.3,12.6));
}}
```

**ii.**

```java
class Car {
void run(){
System.out.println(“car is running”);
}
Class Audi extends Car{
void run()
{
System.out.prinltn(“Audi is running safely with 100km”);
}
public static void main( String args[])
{
Car b=new Audi();
b.run();
}
}
```

#### **What is the important difference between the two?**

**Answer**: Code snippet **i.** is an example of method overloading while the code snippet **ii.** demonstrates method overriding.

#### **Questions: Program for string reversal without using inbuilt function**

**Answer:**

```java
public class Reversal
{
public static void main(String args[])
{
String input = "Java Interview";
System.out.println("Given String -> " + "Java Interview");
char charArray[] = input.toCharArray();
System.out.println("Reversed String -> ");
for(int i = charArray.length-1;i>=0; i--)
{
System.out.print(charArray[i]);
}
System.out.println();
}
}
```

#### **Questions: Program to delete duplicate from an array**

**Answer:**

```java
import java.util.ArrayList;
import java.util.LinkedHashSet;
import java.util.List;
import java.util.Set;
class RemoveDuplicates
{
public static void main(String args[])
{
/*create ArrayList with duplicate elements*/
ArrayList duplicate = new ArrayList();
duplicate.add(5);
duplicate.add(7);
duplicate.add(1);
duplicate.add(4);
duplicate.add(1);
duplicate.add(7);
System.out.println("Given array: "+ duplicate);
Set <Integer> withoutDuplicates = new LinkedHashSet<Integer>(duplicate)
duplicate.clear();
duplicate.addAll(withoutDuplicates);
System.out.println("Array without duplicates: "+ duplicate);
}
}
```

#### **Questions: Program to reverse a number**

**Answer:**

```java
import java.util.Scanner;
public class NumberReversal
{
public static void main(String args[])
{
System.out.println("Please enter the number to be reversed");
Scanner sc = new Scanner (System.in);
int number = sc.nextInt();
int reverse = reverse(number);
System.out.println("Reverse of number: " + number + " is " + reverse(number));
}
public static int reverse(int number){
int reverse = 0;
int remainder = 0;
do{
remainder = number%10;
reverse = reverse*10 + remainder;
number = number/10;
}while(number > 0);
   return reverse;
}
}
```

#### **Questions: Program for binary search**

**Answer:**

```java
import java.util.Scanner;
import java.util.Arrays;
public class Binary {
public static void main(String[] args) {
System.out.println("Enter total number of elements : ");
Scanner s = new Scanner (System.in);
int length = s.nextInt();
int[] input = new int[length];
System.out.printf("Enter %d integers", length);
for (int i = 0; i < length; i++) {
input[i] = s.nextInt();
}
/* binary search requires the input array to be sorted so we must sort the array first*/
Arrays.sort(input);
System.out.print("the sorted array is: ");
for(int i= 0; i<= length-1;i++)
{
System.out.println(input[i] + " ,");
}
System.out.println("Please enter number to be searched in sorted array");
int key = s.nextInt();
int index = BSearch(input, key);
if (index == -1) {
System.out.printf("Sorry, %d is not found in array %n", key);
} else {
System.out.printf("%d is found in array at index %d %n", key,
index);
}
}
public static int BSearch(int[] input, int number) {
int low = 0;
int high = input.length - 1;
while (high >= low) {
int middle = (low + high) / 2;
if (input[middle] == number) {
return middle;
} else if (input[middle] < number) {
low = middle + 1;
} else if (input[middle] > number) {
high = middle - 1;
}
}
return -1;
}
}
```

#### **Questions: Program to check if a number is prime.**

**Answer:**

```java
import java.util.Scanner;
public class Prime
{
public static void main(String args[])
{
System.out.println("Enter the number to check: ");
Scanner sc = new Scanner(System.in);
int num = sc.nextInt();
boolean isPrime = false;
  if(num!=0)
  {
  isPrime = checkPrime(num);
  }else
  {
  System.out.println("Enter valid number");
  }
  if(isPrime == false)
  {
  System.out.println(" NOT PRIME!!");
  }
  else
  {
  System.out.println("PRIME!!");
  }
}
public static boolean checkPrime(int number)
{
int sqrt = (int) Math.sqrt(number) + 1;
for(int i = 2; i<sqrt; i++)
{
if(number % i== 0)
{
return false;
}
}
return true;
}
}
```

#### **Questions: Program to print Fibonacci Series**

**Answer:**

```java
import java.util.Scanner;
public class Fibo
{
public static void main(String args[])
{
System.out.println("Enter the number upto which Fibonacci series should be printed ");
Scanner sc = new Scanner(System.in);
int num = sc.nextInt();
System.out.println("Fibonacci Series upto %d is" + num);
for(int i=1; i<=num; i++)
{
System.out.print(fib(i) + " ");
}
}
public static int fib(int n)
{
if(n ==1 || n==2)
{
return 1;
}
return fib(n-1) + fib(n-2);
}
}
```

#### **Questions: Program to check if the given string is a palindrome.**

**Answer:**

```java
import java.util.Scanner;
public class PalinDrome
{
public static void main(String args[])
{
System.out.println("Enter the string to check");
Scanner sc = new Scanner(System.in);
String str = sc.nextLine();
boolean isPalindrome;
isPalindrome = checkPalindrome(str);
if(str.equals(" "))
{
System.out.println("Enter valid string");
}
else
{
if(isPalindrome)
{
System.out.println("PALINDROME!!");
}
else
{
System.out.println("NOT A PALINDROME!!");
}
}
}
public static boolean checkPalindrome(String input)
{
int str_length = input.length();
int i=0, j= str_length-1;
while(i<j)
{
if(input.charAt(i) != input.charAt(j))
return false;
i++;
j--;
}
return true;
}
}
```

**Questions: Pattern printing**

***
***** \*
***** \* \*
***** \* \* \*
***** \* \* \* \***

**Answer:**

```java
public class Pattern
{
public static void main(String args[])
{
 for(int i=5; i>=0; i--)
 {
 System.out.println();
 for(int j=i; j<5;j++)
 {
 System.out.print(" * ");
 }
 }
 System.out.println();
}
}
```

#### **Questions: Program to swap two numbers**

**Answer:**

```java
import java.util.Scanner;
public class Swap
{
public static void main(String args[])
{
Scanner s = new Scanner(System.in);
System.out.println("Enter a number: ");
int a = s.nextInt();
System.out.println("Enter second number: ");
int b = s.nextInt();
System.out.println("Value of a and b before swapping: " + "a = " +a  + " b = " + b);
swap(a,b);
}
public static void swap(int a , int b)
{
int swap_variable;
swap_variable = a;
a = b;
b = swap_variable;
System.out.println("Value of a and b after swapping: " + "a = " +a  + " b = " + b);
}
}
```

#### **Questions: Program to check if the given number is an Armstrong number.**

**Answer:**

```java
import java.util.Scanner;
public class Armstrong
{
public static void main(String args[])
{
Scanner s = new Scanner(System.in);
System.out.println("Enter a number: ");
int number = s.nextInt();
int a=number, sum = 0, num=0;
  while(a%10 !=0)
  {
  num = a%10;
  sum = sum + (num*num*num);
a = a/10;
  }
  if(sum == number)
  {
  System.out.println("Armstrong Number!");
  }
  else
  {
  System.out.println("Not an Armstrong Number!");
  }
}
}
```