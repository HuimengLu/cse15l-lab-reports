# Lab Report 5 Week 10 #

### (1) Find the tests with different results ###

After getting both directories prepared, I used the command `bash script.sh > results.txt` to save the results in two different `results.txt` files.

Then, I ran the command `diff lab9/markdown-parse/results.txt CSE15L-Platypus/results.txt` to compare the two different results. The output is shown below. I can see the differences line by line.

![2022-03-09](https://user-images.githubusercontent.com/97484123/157565777-36920025-d2f6-4e09-8abc-a591e7a42dce.png)

For example:

```
212c212
< [url]
---
> []
```

These lines mean that on line 212, the results in the `markdown-parse` directory contained `[url]`, while the results in the `CSE15L-Platypus` directory contained `[]`.


### (2) Choose files and explain the bugs

(1) The first set of files I chose was 201.md, which caused the difference in line 230. The result from the provided directory is `[baz]`, but the result from `CSE15L-Platypus` is `[]`.

![2022-03-09 (3)](https://user-images.githubusercontent.com/97484123/157566855-9169e8ef-23d6-4c83-8574-1eef98e6ab65.png)

The actual code is:

![2022-03-09 (5)](https://user-images.githubusercontent.com/97484123/157567988-f308513d-0547-4524-b17b-136d6f93d964.png)

I think the `CSE15L-Platypus` implementation is correct, because the excepted output should be `[]` for this file. The bug in `markdown-parse` file is that when there's contents between the brackets and the parentheses, it still takes the code as a valid URL. As a result, before detecting the parentheses, the program should detect if there are contents between the brackets and the parentheses. If so, the line should not be regarded as a valid URL.

![2022-03-09 (6)](https://user-images.githubusercontent.com/97484123/157568551-45d9b238-124c-46b1-a4b5-1ecffc15afd3.png)

(2) The second set of files I chose was 342.md, which caused the difference in line 230. The result from the provided directory is [/foo`], but the result from CSE15L-Platypus is [].

![2022-03-09 (2)](https://user-images.githubusercontent.com/97484123/157568631-06866ab7-ff09-426d-9541-30f9ff6cea37.png)

The actual code is: 

![2022-03-09 (7)](https://user-images.githubusercontent.com/97484123/157568966-024ef529-ed7b-4d9d-bada-732b94ba3a59.png)

I think the `CSE15L-Platypus` implementation is correct, because the excepted output should be `[]` for this file. The bug in `markdown-parse` file is that when there's a set of grave accent (`) symbols inside the link, it should no longer be considered as a valid URL. As a result, a possible solution can be detecting if there's grave accent symbols between the brackets and the parentheses. The detection could be added while we detect the brackets.

![2022-03-09 (8)](https://user-images.githubusercontent.com/97484123/157569700-eafa237c-796f-4b75-bf83-66b54d0a69d0.png)

