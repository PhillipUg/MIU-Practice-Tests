Question 16
A Madhav array has the following property.
a[0] = a[1] + a[2] = a[3] + a[4] + a[5] = a[6] + a[7] + a[8] + a[9] = ...
The length of a Madhav array must be n*(n+1)/2 for some n.
Write a method named isMadhavArray that returns 1 if its array argument is a Madhav array,
otherwise it returns 0. If you are programming in Java or C# the function signature is
int isMadhavArray(int[] a)

Examples

if a is                           | return| reason                                            
-----------------------------------|-------|---------------------------------------------------
 {2,1,1}                           | 1     | 2 = 1 + 1                                         
 {2,1,1,4,-1,-1}                   | 1     | 2 = 1 + 1, 2 = 4 + -1 + -1                        
 {6,2,4,2,2,2,1,5,0,0}             | 1     | 6 = 2 + 4, 6 = 2 + 2 + 2, 6 = 1 + 5 + 0 + 0       
 {18,9,10,6,6,6}                   | 0     | 18 != 9 + 10                                      
 {-6,-3,-3,8,-5,-4}                | 0     | -6 != 8 + -5 + -4                                 
 {0,0,0,0,0,0,0,0,0,0,1,1,1,-2,-1} | 1     | 0 = 0+0, 0 = 0+0+0, 0 = 0+0+0+0, 0 = 1+1+1+-2+-1  
 {3,1,2,3,0}                       | 0     | The length of the array is 5, but 5 != n*(n+1)/2
 
 
 <details>
<summary>See Answer</summary>

```ruby
public static int isMadhavArray(int[] a) {
    int n = 1;
    int i = 0;
    while (i < a.length) {
        int sum = 0;
        for (int j = i; j < i + n; j++) {
            sum += a[j];
        }
        if (sum != a[0]) {
            return 0;
        }
        i += n;
        n++;
    }
    return 1;
}
```

### Explanation

The n variable is used to keep track of how many items should be summed up at once.
The i variable is used to keep track of where we are in the array.
The while loop continues until i reaches the end of the array.
In each iteration of the loop, we sum up n items starting from i and check if the sum is equal to a[0].
If the sum is not equal to a[0], we immediately return 0 because the array is not a Madhav array.
If the while loop completes without returning 0, it means that all the sums are equal to a[0], so we return 1.

</details>
