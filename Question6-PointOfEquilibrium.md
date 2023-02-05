Question 6
Consider an array A with n of positive integers. An integer idx is called
a POE (point of equilibrium) of A, if A[0]+A[1]+...+A[idx-1] is equal to A[idx+1]+A[idx+2]+...+A[n-1].
Write a function to return POE of an array, if it exists and -1 otherwise.

The signature of the function is:
int f(int[] a)

Examples

 if the input arrays are | return                                                       
-------------------------|--------------------------------------------------------------
 {1,8,3,7,10,2}          | 3 Reason: a[0]+a[1]+a[2] is equal to a[4]+a[5]               
 {1,5,3,1,1,1,1,1,1}     | 2 Reason: a[0]+a[1] is equal to a[3]+a[4]+a[5]+a[6]+a[7]+a[8]
 {2,1,1,1,2,1,7}         | 5 Reason: a[0]+a[1]+a[2]+a[3]+a[4] is equal to a[6]          
 {1,2,3}                 | -1 Reason: No POE                                            
 {3,4,5,10}              | -1 Reason: No POE                                            
 {1,2,10,3,4}            | -1 Reason: No POE                                            


<details>
<summary>See Answer</summary>

```ruby
 public static int pointOfEquilibrium(int[] A) {
    int n = A.length;
    int sumLeft = 0;
    int sumRight = 0;
    
    for (int i = 0; i < n; i++) {
        sumRight += A[i];
    }
    
    for (int i = 0; i < n; i++) {
        sumRight -= A[i];
        if (sumLeft == sumRight) {
            return i;
        }
        sumLeft += A[i];
    }
    return -1;
}
```
 
 ### Explanation
 
 The function iterates through the array A twice. In the first loop, it calculates the sum of all the elements in A, and in the second loop, it checks for the point of equilibrium by subtracting each element from the right sum and comparing it to the left sum. If a point of equilibrium is found, the index is returned. If no point of equilibrium is found, the function returns -1.

</details>
