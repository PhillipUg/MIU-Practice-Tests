Question 13
Consider the positive integer 50. Note that 50 = 25 + 25 = 5^2 + 5^2 and 50 = 1 + 49 = 1^2 + 7^2,
Thus 50 can be expressed as a sum of the two squares in two different ways.
Write a method whether or not a positive integer n can be expressed as a sum of two squares in
exactly two different ways.
The signature of the function is
int answerOne(int n)


<details>
<summary>See Answer</summary>

```ruby
public static boolean isTwoSquares(int n) {
        int count = 0;
        for (int i = 1; i * i <= n / 2; i++) {
            for (int j = i + 1; j * j <= n / 2; j++) {
                if (i * i + j * j == n) {
                    count++;
                }
                if (count == 2) {
                    return true;
                }
            }
        }
        return false;
    }
```

### Explanation

The method isTwoSquares takes a positive integer n as input and returns a boolean indicating whether or not it can be expressed as a sum of two squares in exactly two different ways.
We start by defining a variable count to keep track of the number of times n can be expressed as a sum of two squares.
Then, we use two nested loops to iterate through all possible combinations of two squares.
For each combination, we check if the sum of the two squares equals n. If it does, we increment count.
If count reaches 2, it means n can be expressed as a sum of two squares in exactly two different ways, so we return true.
If we loop through all combinations and count never reaches 2, it means n can only be expressed as a sum of two squares in less than or more than 2 ways, so we return false.

</details>
