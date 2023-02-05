Question 9
Write a function named primeCount with signature int primeCount(int start, int end);
The function returns the number of primes between start and end inclusive.
Recall that a prime is a positive integer greater than 1 whose only integer factors are 1 and itself.

Examples

 if start is | and end is | return  | reason                                                           
-------------|------------|---------|------------------------------------------------------------------
 10          | 30         | 6       | The primes between 10 and 30 inclusive are 11,13,17,19,23 and 29 
 11          | 29         | 6       | The primes between 11 and 29 inclusive are 11,13,17,19,23 and 29 
 20          | 22         | 0       | 20,21, and 22 are all non-prime                                  
 1           | 1          | 0       | By definition, 1 is not a prime number                           
 5           | 5          | 1       | 5 is a prime number                                              
 6           | 2          | 0       | start must be less than or equal to end                         
 -10         | 6          | 3       | primes are greater than 1. 2, 3 and 5 are prime                  


<details>
<summary>See Answer</summary>

```ruby
public static int primeCount(int start, int end) {
    int count = 0;
    for (int i = start; i <= end; i++) {
        if (isPrime(i)) {
            count++;
        }
    }
    return count;
}

private static boolean isPrime(int n) {
    if (n <= 1) return false;
    for (int i = 2; i <= Math.sqrt(n); i++) {
        if (n % i == 0) return false;
    }
    return true;
}

```

### Explanation

The primeCount function takes two arguments - start and end - which represent the range of numbers to check for prime numbers. The function isPrime is called for each number in the range to check if it is a prime number. If a number is prime, the count is incremented. Finally, the primeCount function returns the count of prime numbers in the given range.

The isPrime function uses a simple algorithm to determine if a number is prime. It first checks if the number is less than or equal to 1, and if so, it returns false. Then, it loops through all the numbers from 2 to the square root of the number, checking if the number is divisible by any of them. If it is, the function returns false, otherwise it returns true, indicating that the number is prime.

</details>
