Question 19
A prime number is an integer that is divisible only by 1 and itself. A porcupine number is a prime
number whose last digit is 9 and the next prime number that follows it also ends with the digit 9.
For example 139 is a porcupine number because:
a - it is prime
b - it ends in a 9
c - The next prime number after it is 149 which also ends in 9.
Note that 140, 141, 142, 143, 144, 145, 146, 147, and 148 are not prime so 149 is the next prime
number after 139.

Write a method named findPorcupineNumber which takes an integer argument n and returns the first
porcupine number that is greater than n. So findPorcupineNumber(0) would return 139 (because 139
happens to be the first porcupine number) and so would findPorcupineNumber(138).
But findPorcupineNumber(139) would return 409 which is the second porcupine number.

The function signature is
int findPorcupineNumber(int n)
You may assume that a porcupine number greater than n exists.
You may assume that a function isPrime exists that returns 1 if its argument is prime, otherwise
it returns 0. e.g isPrime(7) returns 1 and isPrime(8) returns 0.
Hint: Use modulo base 10 arithmetic to get last digit of a number.

<details>
<summary>See Answer</summary>

```ruby
  public static int findPorcupineNumber(int n) {
    while (true) {
        n++; # Increment n by 1 to start searching for the next porcupine number after the input n

        if (isPrime(n) && n % 10 == 9) { # Check if the current number is prime and ends with 9
            int nextPrime = n + 2; # Set the next prime to n + 2, since all primes except 2 are odd
            while (!isPrime(nextPrime)) { # Keep searching for the next prime starting from n + 2
                nextPrime += 2; # Increment nextPrime by 2, since all primes except 2 are odd
            }
            if (nextPrime % 10 == 9) { # Check if the next prime after n also ends with 9
                return n; # If both conditions are met, return the current n as the porcupine number
            }
        }
    }
}

private static boolean isPrime(int n) {
    if (n <= 1) { # A number less than or equal to 1 is not prime
        return false;
    }
    for (int i = 2; i <= Math.sqrt(n); i++) { # Check all integers less than or equal to the square root of n
        if (n % i == 0) { # If n is divisible by any number in this range, it is not prime
            return false;
        }
    }
    return true; # If no divisors are found in the range, n is prime
}

```
  
### Explanation

The findPorcupineNumber method uses a while loop to keep incrementing num until it finds a porcupine number that is greater than n. The method first checks if the last digit of num is 9. If it's not, the loop continues and num is incremented again. If the last digit of num is 9, the method checks if num is prime using the isPrime method. If num is not prime, the loop continues and num is incremented again. If num is prime, the method checks if num + 10 is also prime. If it is, the method returns num as the porcupine number. If num + 10 is not prime, the loop continues and num is incremented again. The isPrime method uses a for loop to check if num is divisible by any integer between 2 and the square root of num. If it is, the method returns false. If the loop finishes without finding a divisor, the method returns true and num is considered to be prime.

</details>
