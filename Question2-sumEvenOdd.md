Question 2
Write a function that takes an array of integers as an argument and returns a
value based on the sums of the even and odd numbers in the array. Let X = the sum of the odd
numbers in the array and let Y = the sum of the even numbers. The function should return X - Y
The signature of the function is:
int f(int[] a)
Examples:

if input array is     | return                                                                
-----------------------|-----------------------------------------------------------------------
 {1}                   | 1                                                                     
 {1,2}                 | -1                                                                    
 {1,2,3}               | 2                                                                     
 {1,2,3,4}             | -2                                                                    
 {3,3,4,4}             | -2                                                                    
 {}                    | 0                                                                     

<details>
<summary>TITLE</summary>

```ruby
 
 public static int sumDifference(int[] arr) {
    int sumOdd = 0;
    int sumEven = 0;

    for (int num : arr) {
        if (num % 2 == 0) {
            sumEven += num;
        } else {
            sumOdd += num;
        }
    }

    return sumOdd - sumEven;
}
 
```
 
 ### Explanation

1. The code declares two variables sumOdd and sumEven to keep track of the sums of the odd and even numbers in the array, respectively. These variables are initialized to 0.

2. The code then uses a for loop to iterate over each element of the input array arr.

3. For each element num in the array, the code checks if it is even or odd using the modulo operator (num % 2). If the result is 0, it means that the number is even and the code adds it to the sumEven variable. If the result is non-zero, it means that the number is odd and the code adds it to the sumOdd variable.

4. After the loop has completed, the code returns the difference between the sum of the odd numbers and the sum of the even numbers by subtracting sumEven from sumOdd. The result of this subtraction is the return value of the function.

</details>
