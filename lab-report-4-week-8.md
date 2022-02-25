# Week 8 Lab Report



This week we will be returning to MarkdownParse with three new snippits to test against our implementation of MarkdownParse in addition to the implementation we reviewed's.

<br><br>

### Links to Github Repositories:

[My Implementation](https://github.com/ExtraExaByte/markdown-parse)

[Implementation we Reviewed](https://github.com/nakulnandhakumar/markdown-parse)


<br><br><br><br>
## Snippet 1:
```
`[a link`](url.com)

[another link](`google.com)`

[`cod[e`](google.com)

[`code]`](ucsd.edu)

```

Using VSCode's preview feature, we can determine that the expected output should be [``` `google.com, google.com, ucsd.edu```]

We will now create a JUnit Test for each of our implementations of MarkDownParse:

First, I modified the make file for the simplicity of further testing:
![Image](https://extraexabyte.github.io/cse15l-lab-reports/Lab4/make.png)

I implemented the junit tests as shown below:
![Image](https://extraexabyte.github.io/cse15l-lab-reports/Lab4/snip1run.png)

The tests failed, resulting in the following output:
![Image](https://extraexabyte.github.io/cse15l-lab-reports/Lab4/snip1test.png)



<br><br><br><br>
## Snippet 2:
```
[a [nested link](a.com)](b.com)

[a nested parenthesized url](a.com(()))

[some escaped \[ brackets \]](example.com)

```

Using VSCode's preview feature, we can determine that the expected output should be [```a.com, a.com(()), example.com```]

We will now create a JUnit Test for each of our implementations of MarkDownParse:


I implemented the junit tests as shown below:
![Image](https://extraexabyte.github.io/cse15l-lab-reports/Lab4/snip2run.png)

The tests failed, resulting in the following output:
![Image](https://extraexabyte.github.io/cse15l-lab-reports/Lab4/snip2test.png)



<br><br><br><br>
## Snippet 3:
```
[this title text is really long and takes up more than 
one line

and has some line breaks](
    https://www.twitter.com
)

[this title text is really long and takes up more than 
one line](
    https://ucsd-cse15l-w22.github.io/
)


[this link doesn't have a closing parenthesis](github.com

And there's still some more text after that.

[this link doesn't have a closing parenthesis for a while](https://cse.ucsd.edu/



)

And then there's more text

```

Using VSCode's preview feature, we can determine that the expected output should be [```https://ucsd-cse15l-w22.github.io/```]

We will now create a JUnit Test for each of our implementations of MarkDownParse:


I implemented the junit tests as shown below:
![Image](https://extraexabyte.github.io/cse15l-lab-reports/Lab4/snip3run.png)

The tests failed, resulting in the following output:
![Image](https://extraexabyte.github.io/cse15l-lab-reports/Lab4/snip3test.png)

<br><br><br><br><br>
# Questions and Answers:


### Snippet 1
I believe that a small code change could be made to not add the link to the return list if there is a back tick before the brackets of the link.  This can be done with a simple if statement near the top of the while loop, returning nothing with the previously mentioned case.

<br><br><br>
### Snippet 2
I believe that a simple fix can be made to correct similar cases by checking if any bracket or parenthesis is escaped before updating the index.  This would be a simple fix that will address many potential issues.

<br><br><br>
### Snippet 3
I believe this will be a much more involved update for similar cases to work.  Since it is spanning over multiple lines, line breaks, and graps between parenthesis, there is a lot of changes that will need to account for different cases of the links spanning over multiple lines.
