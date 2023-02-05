Question 23
An integer array is said to be evenSpaced, if the difference between the largest value
and the smallest value is an even number.

Write a function isEvenSpaced(int[] a) that will return 1 if it is evenSpaced and 0 otherwise.
if array has less than two elements, function will return 0.

 Array              | Largest value| Smallest value | Difference     | Return value               
--------------------|--------------|----------------|----------------|----------------------------
 {100,19,131,140}   | 140          | 19             | 140 - 19 = 121 | 0                          
 {200,1,151,160}    | 200          | 1              | 200 - 1 = 199  | 0                          
 {200,10,151,160}   | 200          | 10             | 200 - 10 = 190 | 1                          
 {100,19,-131,-140} | 100          | -140           | 100-(-140)= 240| 1                          
 {80,-56,11,-81}    | 80           | -81            | 80 -(-81) = 161| 0                          

<details>
<summary>See Answer</summary>

```ruby
public static int isEvenSpaced(int[] a) {
    if (a.length == 0) {
        return 0;
    }
    int max = Integer.MIN_VALUE;
    int min = Integer.MAX_VALUE;
    for (int i = 0; i < a.length; i++) {
        max = Math.max(max, a[i]);
        min = Math.min(min, a[i]);
    }
    int diff = max - min;
    return (diff % 2 == 0) ? 1 : 0;
}
```

### Explanation

In this implementation, we first check if the input array a is empty. If it is, we return 0.

Next, we use two variables max and min to keep track of the largest and smallest values in the array. We initialize max to the smallest possible integer value and min to the largest possible integer value.

We then loop through the elements of the array and update max and min if we find a larger or smaller value, respectively.

Finally, we calculate the difference between the largest and smallest values and check if it is even. If it is, we return 1, otherwise we return 0.

</details>
