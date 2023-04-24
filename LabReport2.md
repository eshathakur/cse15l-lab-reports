
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
<br> ![Image](reverseTestErrors)
<br> Test using input1 (passed test)
<br> ![Image](passedTest)

* The bug: 
<br> Code Before

<br> Code After
