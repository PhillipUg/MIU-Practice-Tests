Question 10
A fancy number is a number in the sequence 1,1,5,17,61,... Note the first two fancy numbers
are 1 and any fancy number other than the first two is sum of three times previous one and two times
the one before that. see below

- 1,
- 1,
- 3*1 + 2*1 = 5,
- 5*3 + 2*1 = 17,
- 17*3 + 5*2 = 61

Write a function named isFancy that returns 1, if it's integer argument is a Fancy number,
otherwise it returns 0.


<details>
<summary>See Answer</summary>

```ruby
  public static int isFancy(int n) {
    if (n == 1 || n == 2) {
        return 1;
    }

    int f1 = 1;
    int f2 = 1;
    int f3 = 0;

    while (f3 < n) {
        f3 = 3 * f2 + 2 * f1;
        f1 = f2;
        f2 = f3;
    }

    if (f3 == n) {
        return 1;
    } else {
        return 0;
    }
}

```
                  
### Explanation
                  
This function works by using a loop to generate the fancy numbers and comparing each generated number to the given n argument. If n matches a generated number, the function returns 1, indicating that n is a fancy number. If the loop ends without finding a match, the function returns 0, indicating that n is not a fancy number.

</details>
