# Lab Report 5-Markdown Differences
Alex Andrade-A16488469  
CSE15L  
Spring 2022

---

The way I found the tests with different results was by running 
`bash script.sh > results.txt` in each repository in order to create a `.txt` file 
containing the results of running `getLinks` on each test file. Then I was able 
to use `vimdiff` to compare the two `.txt` files and find where differences in 
implementation occurred. 

## Markdown Test Difference 1-Test 201

[Here](https://github.com/nidhidhamnani/markdown-parser/blob/main/test-files/201.md?plain=1) is
a link to the test-file that produced different results between my implementation and the
provided implementation.

By using [the CommonMark demo site](https://spec.commonmark.org/dingus/), I decided that `201.md` should produce this ![code](Screenshots/Right201.png) which means that there should not be any links produced when 
running `getLinks` and thus the output should be an empty ArrayList and so should be `[]`

Thus, by using CommonMark, we can see that the implementation on the left, which is my implementation, is correct
for this test and so the provided implementation is wrong for this test.

My implementation outputted an empty ArrayList correctly like `[]` while the provided implementation outputted `[baz]` as shown ![here](Screenshots/Diff1.png)

The expected links in the output are no links and so the output should be an empty list like `[]` and so we can see that my implementation on the left is correct.

For the provided implementation, the bug that causes this incorrect output is 

## Markdown Test Difference 2-Test 432

[Here](https://github.com/nidhidhamnani/markdown-parser/blob/main/test-files/432.md?plain=1) is
a link to the test-file that produced different results between my implementation and the
provided implementation.

By using [the CommonMark demo site](https://spec.commonmark.org/dingus/), I decided that `432.md` should produce this ![code](Screenshots/Right432.png) which means that there should be a link to `/url` and so the output should be 
`[/url]`

Thus, by using CommonMark, we can see that the implementation on the right, which is the provided implementation, 
is correct for this test and so my implementation is wrong for this test.

My implementation outputted an empty ArrayList like `[]` 
while the provided implementation outputted the correct list like `[/url]` as shown ![here](Screenshots/Diff2.png)

The expected link in the output is simply `/url` and so the output should be `[/url]` and so we can see that the 
provided implementation on the right is correct. 