Question 21
The Stanton measure of an array is computed as follows. Count the number of 1s in the array.
Let this count be n. The Stanton measure is the number of times that n appears in the array.
For example, the Stanton measure of {1,4,3,2,1,2,3,2} is 3 because 1 occurs 2 times in the array and
2 occurs 3 times.
Write a function named stantonMeasure that returns the Stanton measure of its array argument.
If you are programming in Java or C#, the function prototype is
int stantonMeasure(int[] a)
Examples

 if a is                 | return   | reason                                                     
-------------------------|----------|------------------------------------------------------------
 {1}                     | 1        | 1 occurs 1 time, 1 occurs 1 time                           
 {0}                     | 1        | 1 occurs 0 times, O occurs 1 time                          
 {3,1,1,4}               | 0        | 1 occurs 2 times, 2 occurs 0 times                         
 {1,3,1,1,3,3,2,3,3,3,4} | 6        | 1 occurs 3 times, 3 occurs 6 times                         
 {}                      | 0        | 1 occurs 0 times, 0 occurs 0 times                         


<details>
<summary>See Answer</summary>

```ruby
 public static int stantonMeasure(int[] arr) {
    int count = 0;
    int stantonMeasure = 0;
    for (int i = 0; i < arr.length; i++) {
        if (arr[i] == 1) {
            count++;
        }
    }
    for (int i = 0; i < arr.length; i++) {
        if (arr[i] == count) {
            stantonMeasure++;
        }
    }
    return stantonMeasure;
}
```
 
 ### Explanation
 
 The function stantonMeasure takes an integer array as an argument. The purpose of this function is to find the Stanton measure of the given array.

The Stanton measure of an array is defined as the number of times that the count of 1s in the array appears in the array.

Here's how the algorithm works:

First, we count the number of 1s in the array and store it in a variable n.

Then, we initialize a variable count to zero. This variable will keep track of how many times n occurs in the array.

We use a loop to iterate over the elements of the array.

For each element in the array, if it is equal to n, we increment the count variable by 1.

After the loop, we return the value of count as the result of the function.

The function returns the Stanton measure of the given array, which is the number of times that the count of 1s appears in the array.

</details>
