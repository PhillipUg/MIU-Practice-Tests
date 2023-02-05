Question 25
An isSym (even/odd Symmetric) array is defined to be an array in which even numbers
and odd numbers appear in the same order from "both directions".
You can assume array has at least one element.
{2,7,9,10,11,5,8} is a isSym array.
Note that from left to right or right to left we have even,odd,odd,even,odd,odd,even.

{9,8,7,13,14,17} is a isSym array.
Note from left to right or right to left we have {odd,even,odd,odd,even,odd}

However, {2,7,8,9,11,13,10} is NOT a isSym array.
From left to right we have {even,odd,even,odd,odd,odd,even}
From right to left we have {even,odd,odd,odd,even,odd,even} which is not the same.

Write a function named isSym that returns 1 if its array argument is a isSym array,
otherwise it returns 0.

if you are programming in Java or C#, the function signature is:
int isSym(int[] a)

if you are programming in C or C++, the function is:
int isSym(int a[], int len) where len is the number of elements in the array.


<details>
<summary>See Answer</summary>

```ruby
public static int isSym(int[] arr) {
    int n = arr.length;
    int left = 0, right = n - 1;
    while (left <= right) {
        if (arr[left] % 2 == arr[right] % 2) {
            left++;
            right--;
        } else {
            return 0;
        }
    }
    return 1;
}

```

### Explanation

This function uses two pointers, left and right, to iterate over the array from both ends towards the middle. If at any point the parity (odd/even) of the elements at the left and right indices are different, the function immediately returns 0 as the array is not symmetric. If the loop completes, it means all elements have the same parity from both ends, so the function returns 1.

</details>
