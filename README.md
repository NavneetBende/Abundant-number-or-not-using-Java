# Abundant-number-or-not-using-Java

Abundant number or not using Java
Check Whether or Not the Number is an Abundant Number in Java
Given an integer input, the objective is to check whether the sum of all the factors of a number except the number itself is greater than the number or not. Therefore, we’ll write a code to Check Whether or Not the Number is an Abundant Number in Java.

Example
Input : 18
Output : Yes, it's an Abundant Number
abundant or not in java
Check Whether or Not the Number is an Abundant Number in Java Language
Given an integer input, the objective is to check whether or not the sum of all the factors of the number, except the number itself is greater than the number. For any number to be an Abundant Number, the sum of it’s factors except itself must be greater than the number. Therefore, we’ll first find all the factors of the number without the number itself within the range 1 to the number/2. We’ll keep summing the factors meanwhile and finally check with the actual number. If we Include the number itself as a factors then the sum must be divided by 2 before comparing. Here are some of the methods to Check Whether or Not the Number is an Abundant Number in Java Language

Method 1: Using Range until Number
Method 2: Using Range until Sqrt( Number )
We’ll discuss the above mentioned methods in detail in the upcoming sections. Do check out the blue box given below for better understanding of the above mentioned questions.

Abundant Numbers
A Number that is smaller than the sum of all it's factors except the number itself is known as an Abundant number.
Let's try and understand the concept better using an example

Example
Input : Number = 18
Output : Yes, It's an Abundant Number
Explanation : The Factors for the number 18 are, 1, 2, 3, 6 and 9. We don't want to include the number itself.
Now the sum of the factors except the number itself is :
1 + 2 + 3 + 6 + 9 = 21
as the number 21>18 , the number itself.
It's an abundant number.
We'll discuss on how to check for an Abundant Number in the upcoming sections.
Method 1: Using Range until Number
Java Code
Run
public class Main
 {
   public static void main (String[]args)
   {

     int n = 12, sum = 0;

     for (int i = 1; i < n; i++) { if (n % i == 0) sum = sum + i; } if (sum > n)
       {
     	System.out.println (n + " is an Abundant Number");
     	System.out.println ("The Abundance is: " + (sum - n));
       }
     else
       System.out.println (n + " is not an Abundant Number");
   }
 }
Output
12 is an Abundant Number
The Abundance is: 4
Method 2: Using Range until sqrt( Number )
Java Code
Run
public class Main
{
  public static void main (String[]args)
  {

    int n = 12; 

    int sum = getSum(n); 

    if(sum > n)
      {
    	System.out.println (n + " is an Abundant Number");
    	System.out.println ("The Abundance is: " + (sum - n));
      }
    else
      System.out.println (n + " is not an Abundant Number");
  }
  
  static int getSum(int n){
    
    int sum = 0;
    
    for(int i = 1; i < Math.sqrt(n); i++) 
    { 
        if (n % i == 0) 
        { 
            // For n : (1, n) will always be pair of divisor 
            // acc to def., we must ignore adding n itself as divisor 
            // when calculating for abundant number 
            if(i == 1) 
                sum = sum + i; 

            // Example For 100 (10,10) will be one of the pair 
            // But, we should add value 10 to the sum just once 
            else if(i == n/i) 
                sum = sum + i; 

            // add both pairs as divisors 
            // For any divisor i, n/i will also be a divisor 
            else 
                sum = sum + i + n/i; 
        } 
    } 
    return sum; 
} 
}
Output
12 is an Abundant Number
The Abundance is: 4
