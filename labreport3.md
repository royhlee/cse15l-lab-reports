# **Lab Report 3 Roy Lee**

##Bugs
### Failure-inducing input
``` 
@Test
  public void testReversed() {
    int[] input1 = {1,2,3};
    assertArrayEquals(new int[]{3,2,1}, ArrayExamples.reversed(input1));
  }
```

### Non-failure-inducing input
```
@Test
  public void testReversed0() {
    int[] input1 = {0};
    assertArrayEquals(new int[]{0}, ArrayExamples.reversed(input1));
  }
```
### Symptom

### Bug
```
for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
```

```
for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1];
    }
    return newArray;
```
In the for loop we were inputting values into the same array as the parameter array with values in newArray which there were none, which is also why the non-failure input needs to output a 0 because there is nothing in the newArray. To fix this bug we have to make newArray store the reversed values in arr so switching arr and newArray in the for loop will make it so that the values of arr, which will be inputted in reverse order, will be stored into a new array. Lastly, we need to return the new array with the reversed elements instead of the original array. 


