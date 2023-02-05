Question 3
Write a function that accepts a character array, a zero-based start position and
a length. It should return a character array containing lengthCharacters starting with
the startCharacter of the input array. The function should do error checking on the start
position and the length and return null if the either value is not legal.

The function signature is:
char[] f(char[] a, int start, int len)


if the input parameters are is | return                                                      
--------------------------------|--------------------------------------------------------------
 {'a','b','c'}, 0, 4            | null                                                         
 {'a','b','c'}, 0, 3            | {'a','b','c'}                                                
 {'a','b','c'}, 0, 2            | {'a','b'}                                                    
 {'a','b','c'}, 0, 1            | {'a'}                                                        
 {'a','b','c'}, 1, 3            | null                                                         
 {'a','b','c'}, 1, 2            | {'b','c'}                                                    
 {'a','b','c'}, 1, 1            | {'b'}                                                        
 {'a','b','c'}, 2, 2            | null                                                         
 {'a','b','c'}, 2, 1            | {'c'}                                                        
 {'a','b','c'}, 3, 1            | null                                                         
 {'a','b','c'}, 1, 0            | {}                                                           
 {'a','b','c'}, -1, 2           | null                                                         
 {'a','b','c'}, -1, -2          | null                                                         
 {}, 0, 1                       | null                                                         


<details>
<summary>See Answer</summary>
 
 ```ruby
public static char[] getSubarray(char[] arr, int start, int length) {
    if (start < 0 || start >= arr.length || length <= 0 || start + length > arr.length) {
        return null;
    }

    char[] subarray = new char[length];
    for (int i = 0; i < length; i++) {
        subarray[i] = arr[start + i];
    }
    return subarray;
} 
 
```

### Explanation
 
1. The function starts by checking if the start position or length is not legal. The start position must be greater than or equal to 0 and less than the length of the input array arr. The length must also be greater than 0 and the start position plus the length must be less than or equal to the length of the input array. If either of these conditions is not met, the function immediately returns null.

2. If the start position and length are legal, the code declares a new character array subarray with a length equal to length.

3. The code then uses a for loop to copy length characters from the input array arr starting at the start position into the subarray. The code uses the variable i as the loop counter and adds i to the start position to get the index of the next character to be copied in each iteration.

4. Finally, the code returns the subarray after all characters have been copied into it.

</details>
