*__PART 1: BUGS__*

This junit test shows an example of an input that produces a failure:
```
@Test 
	public void testReverseInPlace2() {
    int[] input1 = {1,2,3,4,5};
    int[] output = {5,4,3,2,1};
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(output, input1);
	}
 ```
This is is output of running the test:
![image](https://github.com/Ayyuan1/cse15l-lab-reports/assets/156359241/1284cf89-fcc3-46b6-874f-4c79d57dfc07)

This junit test shows an example of an input that does not produce a failure:
```
@Test 
	public void testReverseInPlace3() {
    int[] input1 = {1,2,3,2,1};
    int[] output = {1,2,3,2,1};
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(output, input1);
	}
```
Since there are no errors, it indicates that the test passed:
![image](https://github.com/Ayyuan1/cse15l-lab-reports/assets/156359241/c01fce7d-3e9f-4887-a14e-95272cbb986e)

Fixing the Bug:
Before:
```
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```

After:
```
  static void reverseInPlace(int[] arr) {
    int[] clone = new int[arr.length];

    for(int i=0; i < arr.length; i++){
      clone[i] = arr[i];
    }

    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = clone[arr.length - 1 - i];
    }
    
  }
```

This new implementation fixes the issue which was that only the first half of the array was being cloned since once the halfway 
point of the array was crossed, we are just no longer referencing the original elements in the array, but the new values that we 
set to ovverwrite the previous ones. By using a clone of the original array, we can make sure we are getting the correct values to
be reversed.

*__PART 2: FIND COMMAND__*
*These suggestions were found by giving ChatGPT the prompt for this write up*

*__Option 1: -type__*

Description: Specifies the type of file to search for (e.g., regular file, directory, symbolic link).

Source: Linux find command tutorial with examples

![image](https://github.com/Ayyuan1/cse15l-lab-reports/assets/156359241/f684ab49-31d4-4754-a11e-6809a065b24e)

Output (The entirety is too long to capture in a single screenshot, this is just a few of the lines ): ![image](https://github.com/Ayyuan1/cse15l-lab-reports/assets/156359241/18268c51-eb6e-4c10-8d8e-9eede4ae8cbf)

![image](https://github.com/Ayyuan1/cse15l-lab-reports/assets/156359241/6ca94c00-55d9-42ae-b3c5-c8b4705af30d)

Output: ![image](https://github.com/Ayyuan1/cse15l-lab-reports/assets/156359241/e06cdb20-5c6e-4af1-863e-f792582a2943)

*__Option 2: -size__*

Description: Searches for files of a specific size.

Source: Linux find command tutorial with examples

![image](https://github.com/Ayyuan1/cse15l-lab-reports/assets/156359241/4522f4ec-fc99-47f7-8118-a6a72d205fb0)

Output (There are no files larger than 10M in ./technical): ![image](https://github.com/Ayyuan1/cse15l-lab-reports/assets/156359241/20b105de-1638-4936-8b75-9bff11f59136)


![image](https://github.com/Ayyuan1/cse15l-lab-reports/assets/156359241/8669ac74-a84e-4fec-aa1c-42ace80901fd)

Output (The entirety is too long to capture in a single screenshot, this is just a few of the lines ): ![image](https://github.com/Ayyuan1/cse15l-lab-reports/assets/156359241/80b1d02b-3fff-410c-bf15-a43c8ce5aa1a)

*__Option 3: -name__*

Description: Searches for files with a specific name pattern.

Source: Linux find command tutorial with examples

![image](https://github.com/Ayyuan1/cse15l-lab-reports/assets/156359241/0d493ef8-eb3e-4b3d-b31f-3b98ce11c510)


Output (The entirety is too long to capture in a single screenshot, this is just a few of the lines ): ![image](https://github.com/Ayyuan1/cse15l-lab-reports/assets/156359241/a6c61283-1a8d-4d2f-95dc-cd5e91c2d521)

![image](https://github.com/Ayyuan1/cse15l-lab-reports/assets/156359241/c4e426b5-41a0-41b9-9bab-794ef1c2eb24)

Output (There are no files named "file.txt") : ![image](https://github.com/Ayyuan1/cse15l-lab-reports/assets/156359241/a0543d41-9980-4105-8658-c2ac243473e3)

We can change the input to something else to see that the command does work if a file exists with that name : ![image](https://github.com/Ayyuan1/cse15l-lab-reports/assets/156359241/28b8832b-02bd-4680-90ea-d7dd56e960cc)

*__Option 4: -exec__*

Description: Executes a command for each matched file.

Source: Linux find command tutorial with examples

![image](https://github.com/Ayyuan1/cse15l-lab-reports/assets/156359241/ad498a20-adcd-4ca0-8c6b-c593755348b8)

Output (The entirety is too long to capture in a single screenshot, this is just a few of the lines ) : ![image](https://github.com/Ayyuan1/cse15l-lab-reports/assets/156359241/825a0598-6cc5-440c-8bc4-176025481998)

![image](https://github.com/Ayyuan1/cse15l-lab-reports/assets/156359241/f1861123-cbe0-46be-b072-a4a3d0f53daf)

Output (Nothing is outputted for this command since only permissions are modified) : ![image](https://github.com/Ayyuan1/cse15l-lab-reports/assets/156359241/82c2e9d1-1061-4868-931f-107aac227f1e)




