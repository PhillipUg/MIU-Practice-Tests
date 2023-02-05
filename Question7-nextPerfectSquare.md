Question 7
Write a function nextPerfectSquare that returns the first perfect square that is greater than
it's integer argument. A perfect square is an integer that is equal to some integer squared.

For example 16 is a perfect square because 16 = 4*4. However 15 is not a perfect square because
there is no integer n such that 15 = n*n.

The signature of the function is
int isPerfectSquare(int n)
Examples
 
 n                       | next perfect square                                          
-------------------------|--------------------------------------------------------------
 6                       | 9                                                            
 36                      | 49                                                           
 0                       | 1                                                            
 -5                      | 0                                                            
 
 <details>
<summary>See Answer</summary>

```ruby
public static int nextPerfectSquare(int num) {
    int i = 1;
    while (i * i <= num) {
        i++;
    }
    return i * i;
}

```

### Explanation

The function uses a loop to increment i starting from 1. In each iteration, it calculates i * i, and if it's less than or equal to the input num, it continues to the next iteration. When i * i is greater than num, it means that i is the first integer such that i * i is a perfect square greater than num, and the function returns i * i.

</details>
