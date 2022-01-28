# Week 4 Lab Report
---

This week, we covered making code changes on a forked repository.  We addressed a few modifications to correct errors found in our lab meetings.

### Here is our code change diff from Github
![Image](https://extraexabyte.github.io/cse15l-lab-reports/codeChange.png)

<br><br><br>
We were prompted to make there changes based on [this](https://extraexabyte.github.io/cse15l-lab-reports/breakFile.md) test file.


When this file was run, it resulted in an infinite loop:
![Image](https://extraexabyte.github.io/cse15l-lab-reports/loop.png)

## Reason for the error
When running the program, we discovered that the program created an infinite loop when there was any text after the link.  This is because the while loop doesn't exit until the current index is larger than or equal to the length of the line.  What we did to fix this is we added an if statement in the while loop that would break the  loop if the index of the next ')' character is not valid.  If the index is not valid, then we have reached the end of the link.