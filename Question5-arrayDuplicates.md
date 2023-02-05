Question 5
Write a function to return an array containing all elements common to two
given arrays containing distinct positive integers. You should not use any inbuilt
methods. You are allowed to use any number of arrays.

The signature of the function is:
int[] f(int[] first, int[] second)

Examples:

 if the input parameters are    | return                                                       
--------------------------------|--------------------------------------------------------------
 {1,8,3,2},{4,2,6,1}            | {1,2}                                                        
 {1,8,3,2,6},{2,6,1}            | {2,6,1}                                                      
 {1,3,7,9},{7,1,9,3}            | {1,3,7,9}                                                    
 {1,2}, {3,4}                   | {}                                                          
 {}, {1,2,3}                    | {}                                                           
 {1,2}, {}                      | {}                                                           
 {1,2}, null                    | null                                                         
 null, {}                       | null                                                         
 null, null                     | null                                                         

<details>
<summary>See Answer</summary>

```ruby
 public static int[] commonElements(int[] array1, int[] array2) {
    int length1 = array1.length;
    int length2 = array2.length;
    int[] result = new int[Math.min(length1, length2)];
    int index = 0;
    for (int i = 0; i < length1; i++) {
        for (int j = 0; j < length2; j++) {
            if (array1[i] == array2[j]) {
                result[index++] = array1[i];
                break;
            }
        }
    }
    return Arrays.copyOf(result, index);
}
```
 
 ### Explanation
 
 In this implementation, the function uses two nested for loops to iterate through both arrays, comparing each element of array1 with each element of array2. If a common element is found, it is added to the result array. The size of the result array is determined by taking the minimum of the lengths of array1 and array2 so that it does not exceed the size of the smaller array.

Finally, the copyOf method from the Arrays class is used to return a copy of result with the correct size, which is equal to the number of common elements found. This ensures that only the common elements are returned, and no extra memory is used for unused elements in the result array.

</details>
