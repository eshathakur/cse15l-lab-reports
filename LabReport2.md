
# Part 2
I chose the reversed method from lab3 as my bug for this report.
<br>
* Failure inducing input: 
 ```
 int[] input2 = {1,2,3,4};
 assertArrayEquals(new int[]{4,3,2,1}, ArrayExamples.reversed(input2));
```
* An input that doesn't induce a failure:
```
int[] input1 = { };
assertArrayEquals(new int[]{ }, ArrayExamples.reversed(input1));
```
* The Symptom as the output of running the tests:
<br> Test using input2 (failed test)
<br> ![Image](failedTest.png)
<br> Test using input1 (passed test)
<br> ![Image](passedTest.png)

* The bug:
<br> Code Before
```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];

    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }

```
<br> Code After
```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];

    //create a deep copy of arr
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[i];
    }

    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
```
 <br> Needed to create a deep copy of arr. 
 <br>This fixes the issue because before implementing the deep copy, in the for loop, arr was getting assigned the incorrect values as newArray was initialized with the correct length but no values, each element was then getting stored with the default value of 0 for an empty array. 
 <br>That is why the error shows it was expecting the value for 4 but was getting 0.
