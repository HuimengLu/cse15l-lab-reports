# Lab Report Week 3-4

1. Show a screenshot of the code change diff from Github (a page like this)
2. Link to the test file for a failure-inducing input that prompted you to make that change
3. Show the symptom of that failure-inducing input by showing the output of running the file at the command line for the version where it was failing (this should also be in the commit message history)
4. Write 2-3 sentences describing the relationship between the bug, the symptom, and the failure-inducing input.

### Code Change 1
1. The screenshot of the code change diff from Github

![2022-01-28 (2)](https://user-images.githubusercontent.com/97484123/151601227-cd83db38-9c39-4e77-9df9-7d3b41e36439.png)

2. Link to the test file for a failure-inducing input that prompted you to make that change

    [https://github.com/HuimengLu/markdown-parse/blob/main/another-file.md](https://github.com/HuimengLu/markdown-parse/blob/main/another-file.md)
    
3. The symptom of that failure-inducing input

![2022-01-28 (6)](https://user-images.githubusercontent.com/97484123/151607729-246ba4eb-6b8d-40e5-a538-ff14bbbfc4d9.png)

4. the relationship between the bug, the symptom, and the failure-inducing input

Before the change, the bug is that as long as there is no bracket, the program will produce an error and stop functioning (which is symptom here). So I added a no-bracket detector here. When no bracket is detected, the loop breaks, but the program will still function normally.

### Code Change 2
1. The screenshot of the code change diff from Github

![2022-01-28 (3)](https://user-images.githubusercontent.com/97484123/151603517-81c21949-b7d3-4130-ae98-102812b0b1fc.png)

2. Link to the test file for a failure-inducing input that prompted you to make that change

    [https://github.com/HuimengLu/markdown-parse/blob/main/new-markdown.md](https://github.com/HuimengLu/markdown-parse/blob/main/new-markdown.md)
    
3. The symptom of that failure-inducing input

![2022-01-28 (7)](https://user-images.githubusercontent.com/97484123/151608826-d9472213-6c8b-46fc-9986-e3d3d958aa2f.png)

4. the relationship between the bug, the symptom, and the failure-inducing input

Before the change, the bug is that as long as there is no parenthese, the program will produce an error and stop functioning (which is symptom here). So I added a no-parenthese detector here. When no parenthese is detected, the loop breaks, but the program will still function normally.

### Code Change 3
1. The screenshot of the code change diff from Github

![2022-01-28 (4)](https://user-images.githubusercontent.com/97484123/151603935-b3298d0e-5a51-4bff-b068-58abe6240496.png)

2. Link to the test file for a failure-inducing input that prompted you to make that change

    [https://github.com/HuimengLu/markdown-parse/blob/main/one-more.md](https://github.com/HuimengLu/markdown-parse/blob/main/one-more.md)
    
3. The symptom of that failure-inducing input

![2022-01-28 (8)](https://user-images.githubusercontent.com/97484123/151609212-50940bdc-5d9e-48c0-8df6-3e1094f407af.png)

4. the relationship between the bug, the symptom, and the failure-inducing input

The symptom here is that "[This is not a link]random words(httplink! some-page)" is not a valid URL, but the program printed it out. The bug is that even if the brackets and the parentheses are seperated by words, the program still views it as an URL. We fixed the bug by adding a space-detector between the brackets and the parentheses.
