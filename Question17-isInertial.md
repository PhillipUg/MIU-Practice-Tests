Question 17
An array is defined to be inertial if the following conditions hold:
a. it contains at least one odd value
b. the maximum value in the array is even
c. every odd value is greater than every even value that is not the maximum value.
so {11,4,20,9,2,8} is inertial because
 - it contains at least one odd value
 - the maximum value in the array is 20 which is even
 - the two odd values (11 and 9) are greater than all the even values that are not
equal to 20 (the maximum), i.e {4,2,8}.
However, {12,11,4,9,2,3,10} is not inertial because it fails condition (c), i.e.
10 (which is even) is greater than 9 (which is odd), and 10 is not the maximum value
in the array.

Write a function called isInertial that accepts an integer array and returns 1 if the array
is inertial; otherwise it returns 0.
If you are programing in Java or C#, the function signature is
int isInertial(int[] a)

Some other examples:

 if the input array is | return | reason                                                                
-----------------------|--------|-----------------------------------------------------------------------
 {1}                   | 0      | fails condition (a) - the maximum value must be even                  
 {2}                   | 0      | fails condition (b) - the array must contain at least one odd value   
 {1,2,3,4}             | 0      | fails condition (c) - 1(which is odd) is not greater than all even values other than the maximum (1 is less than 2 which is not the max) 
 {1,1,1,1,1,1,2}       | 1      | there is no even number other than the maximum. Hence, there can be no other even values that are greater than 1.       
 {2,12,4,6,8,11}       | 1      | 11, the only odd value is greater than all even values except 12 which is the maximum value in the array.
 {2,12,12,4,6,8,11}    | 1      | same as previous, ie, it is ok if maximum value occurs more than once 
 {-2,-4,-6,-8,-11}     | 0      | -8, which is even, is not the maximum value but is greater than -11   
 {2,3,5,7}             | 0      | the maximum value is odd                                              
 {2,4,6,8,10}          | 0      | there is no odd value in the array                                    
 

<details>
<summary>See Answer</summary>

```ruby
public static int isInertial(int[] arr) {
    int maxValue = Integer.MIN_VALUE;
    int hasOdd = 0;
    
    # Loop through the array to check if the array has an odd number and find the max value in the array
    for (int i = 0; i < arr.length; i++) {
        if (arr[i] % 2 != 0) { # Check if the current value is odd
            hasOdd = 1; # Set hasOdd to 1, meaning that there's an odd number in the array
        }
        if (arr[i] > maxValue) { # Check if the current value is greater than the maxValue
            maxValue = arr[i]; # If it is, set maxValue to this current value
        }
    }
    
    # If there's no odd number or the maxValue is not even, return 0
    if (hasOdd == 0 || maxValue % 2 != 0) {
        return 0;
    }
    
    # Loop through the array again to check if all the odd numbers are greater than all the even numbers that are not the maxValue
    for (int i = 0; i < arr.length; i++) {
        if (arr[i] % 2 == 0 && arr[i] != maxValue) { # Check if the current value is even and not equal to maxValue
            for (int j = 0; j < arr.length; j++) {
                if (arr[j] % 2 != 0 && arr[j] <= arr[i]) { # Check if the current value is odd and less than or equal to the current even value
                    return 0; # If the above conditions are met, return 0
                }
            }
        }
    }
    return 1; # If none of the conditions were met, return 1
}

```

### Explanation

The code checks if an array is an "inertial array". The conditions for an array to be inertial are:

- It must contain at least one odd value
- The maximum value in the array must be even
- All odd values must be greater than all even values that are not the maximum value.
 
The code first checks if the array contains at least one odd value and if the maximum value is even. If either of these conditions are not met, the function returns 0 (false).

Then, it loops through the array, and for each even value (excluding the maximum), it checks if there are any odd values that are smaller or equal to that even value. If so, the function returns 0 (false).

If all conditions are met, the function returns 1 (true).

</details>
