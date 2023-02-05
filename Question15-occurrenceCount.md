Question 15
Write a function that will return 1 if an integer array satisfies the following conditions and returns 0 otherwise.
1. it has even numbers of elements
2. Sum of all the numbers in the first half of the array is equal to the sum of all the numbers in the second half of the array.

If you are programming in Java, the function Signature is
int answerThree(int[] a)
Examples

 a                 | return | Explanation                                                           
-------------------|--------|-----------------------------------------------------------------------
 {5,4,3,2,3,4,6,1} | 1      | There are 8 (even) number of elements in the array. Thus condition 1 satisfied. The sum of all the numbers in the first half = 5+4+3+2 = 14          


<details>
<summary>See Answer</summary>

 ```ruby
 public static int mostOccurring(int[] arr) {
    HashMap<Integer, Integer> countMap = new HashMap<>();
    int maxCount = 0;
    int mostOccurring = arr[0];
    for (int num : arr) {
        int count = countMap.getOrDefault(num, 0) + 1;
        countMap.put(num, count);
        if (count > maxCount) {
            maxCount = count;
            mostOccurring = num;
        }
    }
    return mostOccurring;
}
 ```
 
 ### Explanation
 
 In this solution, we use a HashMap to store the count of each number in the array. The key of the HashMap is the number, and the value is the count.

We use a for-each loop to iterate through the array, and for each number, we use the getOrDefault method to get its count from the HashMap. If the count is not present, it returns 0. Then, we increment the count and update the HashMap with the new count.

Finally, we check if the current count is greater than the previous maximum count. If it is, we update the maxCount and mostOccurring variables.

This solution is more efficient because it only needs to go through the array once, while the previous solution used two nested loops, making its time complexity O(n^2). The time complexity of this solution is O(n), which is more efficient for large arrays.

</details>
