# Week 4 Lab Report
---

This week, we covered making code changes on a forked repository.  We addressed a few modifications to correct errors found in our lab meetings.


## First Error:
<br>

### Here is our code change diff from Github
![Image](https://extraexabyte.github.io/cse15l-lab-reports/testCase3.png)

<br><br><br>
We were prompted to make there changes based on [this](https://extraexabyte.github.io/cse15l-lab-reports/break3.md) test file.


When this file was run, it resulted in an incorrect output:
![Image](https://extraexabyte.github.io/cse15l-lab-reports/imagePrint.png)


## Reason for the error
The markdown code for an image and a link are nearly indistiguishable to an untrained eye.  The key difference is that an image must have an exclamation mark before the sqare brackets.  So we implemented a test case that would not return the supposed link in the parenthesis if there is an exclamation mark leading the link format
<br><br><br><br>




## Second Error:
<br>

### Here is our code change diff from Github
![Image](https://extraexabyte.github.io/cse15l-lab-reports/error9.png)

<br><br><br>
We were prompted to make there changes based on [this](https://extraexabyte.github.io/cse15l-lab-reports/break9.md) test file.


When this file was run, it resulted in an out of bounds exception:
![Image](https://extraexabyte.github.io/cse15l-lab-reports/outOfBounds1.png)


## Reason for the error
When the loop begins, it tries to run the following block of code:
```
if(markdown.charAt(closeParen - 1) == '(') {
                closeParen = markdown.indexOf(")", closeParen + 1);
            }
```

The issue is, the index of closeParen is 0.  Subtracting 1 from that tries to access the char at -1, which throws an out of bounds error.  By adding a case to exit the loop when there is no next occurance of '(', we avoid the error entirely
<br><br><br><br>

## Third Error:

### Here is our code change diff from Github
![Image](https://extraexabyte.github.io/cse15l-lab-reports/testCase1.png)

<br><br><br>
We were prompted to make there changes based on [this](https://extraexabyte.github.io/cse15l-lab-reports/breakFile.md) test file.

When this file was run, it resulted in an infinite loop:
![Image](https://extraexabyte.github.io/cse15l-lab-reports/loop.png)

## Reason for the error

When the test file was run that included additional text after the link, it resulted in an infinite loop because the while loop condition was not satisfied, the current index wouldn't increase so it was always less than 
> markdown.length()
This error was solved by checking if there is another open bracket indicating a potential link following the first one, otherwise it will break the while loop.



