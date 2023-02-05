Question 24
A Sub Array is defined to be an array in which each element is greater than sum of all
elements after that element. see example below:
{13,6,3,2} is a sub array. Note that 13 > 6+3+2, 6 > 3+2, 3>2.
{11,5,3,2} is NOT a sub array. Note that 5 is not greater than 3+2.
Write a function named isSub that returns 1 if its array argument is a Sub array. otherwise it returns 0.
if you are programming in Java or C#, the function signature is: int isSub(int[] a)

<details>
<summary>See Answer</summary>

```ruby
public static int isSub(int[] arr) {
    int n = arr.length;
    int sum = 0;
    for (int i = n - 1; i >= 0; i--) {
        if (arr[i] <= sum) {
            return 0;
        }
        sum += arr[i];
    }
    return 1;
}
```

### Explanation

The function isSub takes an integer array arr as input and returns 1 if it's a subarray and 0 otherwise.

It starts from the last element of the array and iterates backwards. For each element arr[i], it checks if it is less than or equal to the sum of all elements after it (sum). If it is, the function immediately returns 0, because this means the subarray condition is not fulfilled. If the element is greater than the sum, it adds the current element to the sum.

After the loop, if the function has not returned 0, it means all elements fulfill the subarray condition, so the function returns 1.

</details>
