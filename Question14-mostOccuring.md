Question 14
Write a function that will return the most occurring number in an array. If there is more than
one such number, the function may return any one of them.
If you are programming in Java or C#, the function signature is int answerTwo(int[] a)

Examples

 a                       | return   | Explanation                                                
-------------------------|----------|------------------------------------------------------------
 {6,8,1,8,2}             | 8        | 8 occurs two times. No other number occurs 3 or more times 
 {6,8,1,8,6}             | 8 or 6   | 8, 6. The Function may return either 8 or 6                

<details>
<summary>See Answer</summary>

```ruby
public static int mostOccurring(int[] arr) {
    int maxCount = 0;
    int mostOccurring = arr[0];
    for (int i = 0; i < arr.length; i++) {
        int count = 0;
        for (int j = 0; j < arr.length; j++) {
            if (arr[i] == arr[j]) {
                count++;
            }
        }
        if (count > maxCount) {
            maxCount = count;
            mostOccurring = arr[i];
        }
    }
    return mostOccurring;
}
```

### Explanation

In this solution, we use a HashMap to store the count of each number in the array. The key of the HashMap is the number, and the value is the count.

We use a for-each loop to iterate through the array, and for each number, we use the getOrDefault method to get its count from the HashMap. If the count is not present, it returns 0. Then, we increment the count and update the HashMap with the new count.

Finally, we check if the current count is greater than the previous maximum count. If it is, we update the maxCount and mostOccurring variables.

This solution is more efficient because it only needs to go through the array once, while the previous solution used two nested loops, making its time complexity O(n^2). The time complexity of this solution is O(n), which is more efficient for large arrays

</details>
