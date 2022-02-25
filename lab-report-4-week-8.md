# Lab Report 4 Week 8 #

### Links to repository

My markdown-parse repository: [https://github.com/HuimengLu/CSE15L-Platypus](https://github.com/HuimengLu/CSE15L-Platypus)\
Repository I reviewed: [https://github.com/ezhou413/markdown-parse](https://github.com/ezhou413/markdown-parse)

### Test preview

I chose the CommonMark demo site to preview the snippets.

### New tests

In `MarkdownParseTest.java`, I created new tests basing on the given snippets.\
My repository:\
![2022-02-24 (8)](https://user-images.githubusercontent.com/97484123/155672988-440b6743-acc0-4a83-b74c-1a570d759ee4.png)

The repository I reviewed:\
![2022-02-25](https://user-images.githubusercontent.com/97484123/155763353-3774e71e-5777-40e6-a1a9-9d5856a5bebf.png)


### Test results

My repository:\
Test 1 and Test 2 passed. Test 3 failed.\
![2022-02-24 (4)](https://user-images.githubusercontent.com/97484123/155671443-8056afa6-5a84-445f-a03c-169738bd8c03.png)
![2022-02-24 (5)](https://user-images.githubusercontent.com/97484123/155671447-550d602c-6c53-48f8-83bf-f286ca53afab.png)

The repository I reviewed:\
Test 1 passed. Test 2 and Test 3 failed.\
![2022-02-25 (1)](https://user-images.githubusercontent.com/97484123/155763520-7e0de25e-0013-4fd6-b171-ee680337e00d.png)
![2022-02-25 (2)](https://user-images.githubusercontent.com/97484123/155763525-fc614745-c025-422c-a5a9-5bfa49dc0b4a.png)

### Answer the following questions with 2-3 sentences each:
(1) Do you think there is a small (<10 lines) code change that will make your program work for snippet 1 and all related cases that use inline code with backticks? If yes, describe the code change. If not, describe why it would be a more involved change.

Snippet 1 passed my test, so there's no need to change the code in my program.

(2) Do you think there is a small (<10 lines) code change that will make your program work for snippet 2 and all related cases that nest parentheses, brackets, and escaped brackets? If yes, describe the code change. If not, describe why it would be a more involved change.

Snippet 2 passed my test, so there's no need to change the code in my program.

(3) Do you think there is a small (<10 lines) code change that will make your program work for snippet 3 and all related cases that have newlines in brackets and parentheses? If yes, describe the code change. If not, describe why it would be a more involved change.

I think there is a small code change that can potentially make my program work. What I need to make sure is that right after 1 line break, it is not allowed to have another line break. (Meaning that empty lines between parentheses and brackets are not allowed.)

The allowed situation:
```
[this title text is really long and takes up more than 
one line](
    https://ucsd-cse15l-w22.github.io/
)
```
