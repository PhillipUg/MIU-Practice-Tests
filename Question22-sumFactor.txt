Question 22
The sum factor of an array is defined to be the number of times that the sum of the array appears
as an element of the array. So the sum factor of {1,-1,1,-1,1,-1,1} is 4 because the sum of the elements
of the array is 1 and 1 appears four times in the array.
And the sum factor of {1,2,3,4} is 0 because the sum of the elements of the array is 10 and 10
does not occur as an element of the array. The sum factor of the empty array is defined to be 0.

Write a function named sumFactor that returns the sum factor of its array argument.
if you are programming in Java or C#, the function signature is
int sumFactor(int[] a)

 if a is                 | return   | reason                                                     
-------------------------|----------|------------------------------------------------------------
 {3,0,2,-5,0}            | 2        | The sum of array is 0 and 0 occurs 2 times                 
 {9,-3,-3,-1,-1}         | 0        | The sum of the array is 1 and 1 does not occur in array    
 {1}                     | 1        | The sum of the array is 1 and 1 occurs once in the array   
 {0,0,0}                 | 3        | The sum of the array is 0 and 0 occurs 3 times in the array


<details>
<summary>See Answer</summary>

```ruby
public static int sumFactor(int[] arr) {
    int sum = 0;
    for (int i : arr) {
        sum += i;
    }

    int count = 0;
    for (int i : arr) {
        if (i == sum) {
            count++;
        }
    }

    return count;
}
```

### Explanation

This function calculates the sum of all elements in the input array arr, and stores the result in sum.
Then, it iterates through arr and checks if each element is equal to sum. If an element is equal to sum, it increments the count variable.
Finally, the function returns count, which is the number of times the sum of arr appears in arr.

</details>
