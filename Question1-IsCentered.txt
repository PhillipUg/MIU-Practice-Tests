Question 1
An array with an odd number of elements is said to be centered
if all elements (except the middle one) are strictly greater than the value
of the middle element. Note that only arrays with an odd number of elements
have a middle element. Write a function that accepts an integer array and
returns 1 if it is a centered array, otherwise it returns 0.
Examples:
 -----------------------|-----------------------------------------------------------------------
| if the input array is | return                                                                |
|-----------------------|-----------------------------------------------------------------------|
| {1,2,3,4,5}           | 0 (the middle element 3 is not strictly less than all other elements) |
|-----------------------|-----------------------------------------------------------------------|
| {3,2,1,4,5}           | 1 (the middle element 1 is strictly less than all other elements)     |
|-----------------------|-----------------------------------------------------------------------|
| {3,2,1,4,1}           | 0 (the middle element 1 is not strictly less than all other elements) |
|-----------------------|-----------------------------------------------------------------------|
| {1,2,3,4}             | 0 (no middle element)                                                 |
|-----------------------|-----------------------------------------------------------------------|
| {}                    | 0 (no middle element)                                                 |
|-----------------------|-----------------------------------------------------------------------|
| {10}                  | 1 (the middle element 10 is strictly less than all other elements)    |
 -----------------------------------------------------------------------------------------------
 
 
 <details>
<summary>TITLE</summary>

BODY CONTENT

</details>
 

<details>
  <summary>See Answer</summary>
  
    ```js
    public static int isCenteredArray(int[] arr) {
      int n = arr.length;
      if (n % 2 == 0) {
          return 0;
      }

      int middle = arr[n / 2];
      for (int i = 0; i < n; i++) {
          if (i == n / 2) {
              continue;
          }
          if (arr[i] <= middle) {
              return 0;
          }
      }
      return 1;
    }
    ```
  
   ### Explanation
     1. First, the function checks if the length of the input array arr is even or not. If the length is even, the function immediately returns 0 as   centered arrays can only have an odd number of elements.

   2. If the length of the array is odd, the code then calculates the index of the middle element and stores it in the middle variable.

   3. The code then iterates over the array using a for loop. For each element of the array, the code checks if the current index i is equal to the index of the middle element (n / 2). If so, the code skips the current iteration using the continue statement.

   4. If the current index is not equal to the index of the middle element, the code checks if the current element arr[i] is less than or equal to the middle element. If so, the function immediately returns 0 as the current element is not strictly greater than the middle element.

   5. After all elements of the array have been checked, if no elements were found to be less than or equal to the middle element, the function returns 1, indicating that the array is a centered array.
  
</details>
