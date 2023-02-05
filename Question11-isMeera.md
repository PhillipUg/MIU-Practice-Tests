Question 11
A Meera array is any array that contains the value 1 if and only if it contains 9.
The array {7,9,0,10,1} is a Meera array because it contains 1 and 9.
The array {6,10,8} is a Meera array because it contains no 1 and no 9.
The array {7,6,1} is not a Meera array because it contains 1 but does not contain a 9.
The array {9,10,0} is not a Meera array because it contains a 9 but does not contain 1.
It is okay if a Meera array contains more than one value 1 and more than one 9.
So the array {1,1,0,8,0,9,9,1} is a Meera array.
Write a function named isMeera that returns 1 if it's array argument is a Merra array
and returns 0 otherwise.
If you are programming in Java or C#, the function signature is int isMeera(int[] a)


<details>
<summary>See Answer</summary>

  ```ruby
  public static int isMeera(int[] arr) {
    boolean has1 = false;
    boolean has9 = false;
    for (int i = 0; i < arr.length; i++) {
        if (arr[i] == 1) {
            has1 = true;
        }
        if (arr[i] == 9) {
            has9 = true;
        }
    }
    if (has1 == true && has9 == true) {
        return 1;
    }
    if (has1 == false && has9 == false) {
        return 1;
    }
    return 0;
}

  ```
 
 ### Explanation

In this function, we have two boolean variables: "has1" and "has9".
We use a for loop to go through each element in the array, and check if the value is 1 or 9.
If we find a 1, we set "has1" to true. If we find a 9, we set "has9" to true.

After the for loop, we check if either both "has1" and "has9" are true or if neither are true.
If either are true, that means the array is a Meera array and we return 1.
If neither are true, then the array is not a Meera array and we return 0.

</details>
