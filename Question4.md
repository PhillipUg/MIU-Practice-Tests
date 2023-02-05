Question 4
Write a function to reverse an integer using numeric operators and without
using any arrays or other data structures.

The signature of the function is:
int f(int n)
Examples

 if the input integer is        | return                                                       
--------------------------------|---------------
 1234                           | 4321                                                         
 12005                          | 50021                                                        
 1                              | 1                                                            
 1000                           | 1                                                            
 0                              | 0                                                            
 -12345                         | -54321       
 
 
<details>
<summary>See Answer</summary>

```ruby
 public static int reverse(int num) {
    int reversed = 0;
    while (num != 0) {
        int digit = num % 10;
        reversed = reversed * 10 + digit;
        num /= 10;
    }
    return reversed;
}
 
 ```
 
 ### Explanation 
 
In this implementation, the function uses a while loop to extract each digit of the integer num using the modulo operator (%), and add it to a running total stored in the reversed variable. The reversed variable is multiplied by 10 each iteration to make room for the next digit, and the num variable is updated by dividing it by 10 each iteration to remove the last digit. The final value of reversed is returned as the reversed integer.
 
 When you call the modulo operator on a number, it returns the remainder after division. In other words, it gives you the "leftover" after dividing the number by the other number.

For example, when you divide the number 123 by 10, you get 12 with a remainder of 3. The modulo operator gives you this remainder, which is 3.

So, when you call num % 10 in the code, it gives you the last digit of num because the last digit is the remainder after dividing num by 10.

Think of it like this: when you take a number and divide it by 10, you move its last digit one place to the right. If you repeat this process enough times, you'll eventually get to a number that's less than 10, which is just a single digit. The single digit that you're left with is the last digit of the original number.

For example, let's say you have the number 123. To find the last digit, you would divide 123 by 10 to get 12 with a remainder of 3. That remainder of 3 is the last digit of 123.

</details>
