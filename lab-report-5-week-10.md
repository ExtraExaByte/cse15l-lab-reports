# Week 10 Lab Report

<br>

In Lab 9, we experimented with a bunch of markdown files to test two implementations of Markdown parse.  We compared our version of markdownparse to the professors and used a bash script to output all the results to a .txt file.

We will be comparing two files that resulted in different outputs;

 [File 22](https://extraexabyte.github.io/cse15l-lab-reports/Lab5/break22.md) & [File 32](https://extraexabyte.github.io/cse15l-lab-reports/Lab5/break32.md).

To compare these files after running the bash script in each of their respective directories, we executed the command:
``` 
vimdiff Lab9/markdown-parse/results.txt markdown-parse/results.txt
```

The command may look like we are comparing the file agianst itself but this is because both the reposities share a common name, so ours is stored in the Lab9 folder.

We manually seached through the results and found a few conflicts that were highlighted in different colors/

<br><br><br>
### Let's start with File 22:

Here is the vimdiff output for file22.md:
![File22](https://extraexabyte.github.io/cse15l-lab-reports/Lab5/File22Error.png)

On the left is my implementation, and the professors is on the right.  
According to commonmark, this is suppose to be a valid link, meaning the professors implementation is correct.
The reason my code is not working for this link is because it recognizes the quotation marks as a string, which exits the loop.  A way to fix this is to remove the condition that exists the loop if there is a quotation mark in the link, which is a contradition to a prior understand of what did and didn't count as a link.

We would want to remove the code in our program that looks like this:
```java
if(markdown.indexOf("\"") != -1){
    break;
}
```

### Moving on to File 32:

Here is the vimdiff output for file22.md:
![File32](https://extraexabyte.github.io/cse15l-lab-reports/Lab5/File32Error.png)

As before, the left is my implementation and the right is the professors.  In this case, the professors implementation is correct according to VSCode preview and CommonMark preview.
This bug required some investigation to fix.  
It may be disceeving that this is another case of having quotation marks in the link, but that is not the only case.  Our implementation reached the space character in the link which caused it to break. To fix this, we had to implement some interesting logic-ed code:

```java
if(markdown.indexOf(" ") != -1){
    try{
        endIndex = closeparen + 1;
    }
    catch
    {
        continue;
    }
}
```

Essentially, we had a part in our program that would track an endIndex value where we expected the link to end.  If we detect a space, then we are going to move our end index to closeparen + 1 to tell the program that it needs to reach at least the close parenthesis before checking if it has reached the end of the link.

After this fix, the code used in our lab finally had the same result for both file 22 and 32.

<br><br>
## On that note, we have reached the end of the quarter.  Thank you for a great 10 weeks and cheers to the next time we meet, whomever is reviewing this.