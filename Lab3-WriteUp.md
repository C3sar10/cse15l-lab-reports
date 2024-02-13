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
---
### `Find` Command
The `find` command is a terminal command you type to execute a certain task, in this case it will start in the working directory and iteratively search through the directory and its' subdirectories for the file passed as a parameter to be found. 
1. `- delete` option:
   	- What this command does is it deletes the file that is searched for by the find command.
   	- Example: `Before: cd winter2024: wavelet Plain.txt
   		    Input: find /User/winter2024/Plain.txt -delete
   	  	    Output: cd winter2024: wavelet`
   	- Example: `Before: cd winter2024: wavelet Plain.txt Humor.txt Surface.txt test.sh
   		    Input: find /User/winter2024 -name "*.txt" -delete
   	  	    Output: cd winter2024: wavelet test.sh`
	- In the first example the path name is given to `find /Path/to/file -delete` to search for `Plain.txt` in the winter2024 		direcotry and its subdirectories. Then the file is deleted which is what is shown when ouputing with the cd command of 			winter2024.
 	- In the second example the path name is given to `find /Path/to/directory -name "*.txt" -delete` to search for all files in the 	given direcotry and its subdictoreiss with `.txt` in the name and delete them. This is why the output is now just `wavelet` and 	`test.sh` as the other text files were deleted.  
  	

