# Lab Report 3
## Part 1 - Bugs
---
### The bug I chose was of `static void reverseInPlace(int[] arr)` method in the `ArrayExamples` class. 
1. Failure-Inducing Input:
  - `@Test 
	  public void testReverseInPlace() {
      int[] input1 = {3, 5, 2, 4, 1};
      ArrayExamples.reverseInPlace(input1);
      assertArrayEquals(new int[]{1, 4, 2, 5, 3}, input1);
	  }`
2. Non Failure-Inducing Input: 
  - `@Test 
	  public void testReverseInPlace() {
      int[] input1 = {3};
      ArrayExamples.reverseInPlace(input1);
      assertArrayEquals(new int[]{3}, input1);
	  }`
3. The Symptom: 
![Image](Lab3_P1.png)
4. The Bug: 
	Before => `static void reverseInPlace(int[] arr) {
    			for (int i = 0; i < arr.length / 2; i += 1) {
      				int temp = arr[i];
      				arr[i] = arr[arr.length - i - 1];
    			}
  		  }`
	After => `static void reverseInPlace(int[] arr) {
    			for (int i = 0; i < arr.length / 2; i += 1) {
      				int temp = arr[i];
      				arr[i] = arr[arr.length - i - 1];
      				arr[arr.length - i - 1] = temp;
    			}
  		  }`
Explanation: So the bug was that in the before code, the variable `temp` was not being used at all as it was temporarily storing the integer values of the ith element of the array. In the After code it was used to switch the ith element with its `arr.length-i-1` counterpart in the array. 

## Part 2 - Researching Commands

