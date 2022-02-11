# Lab Report 3 #
### Copy whole directories with scp -r
#### 1. Copying the whole markdown-parse directory to your ieng6 account.
Check the directory on my local computer using `ls`.

![2022-02-09](https://user-images.githubusercontent.com/97484123/153463515-fa872c9c-6609-4fdc-adc7-427bcdc81427.png)

Copy the directory over to the server using the `scp` command.

![2022-02-09 (1)](https://user-images.githubusercontent.com/97484123/153463111-6d66903c-d28c-43e3-a5ad-b00bda998d38.png)

#### 2. Logging into ieng6 account after this and compiling and running the tests for your repository.
Log into the ieng6 account and use the command `ls` to make sure that the directory was successfully copied.

![2022-02-09 (2)](https://user-images.githubusercontent.com/97484123/153463382-aca560cc-a378-4943-aa2a-5caeb04803be.png)

![2022-02-09 (3)](https://user-images.githubusercontent.com/97484123/153463394-720be6c6-ce5c-4666-91a0-9ede0554b0e2.png)

#### 3. Show combining scp, ;, and ssh to copy the whole directory and run the tests in one line.
Combine the codes into one line using `scp`, `;`, and `ssh`.
###### Reminder 1: Compile MarkdownParse.java before compiling MarkdownParseTest.java.
###### Reminder 2: Since my local computer has a different java version, replace `javac` and `java` with `/software/CSE/oracle-java-se-14/jdk-14.0.2/bin/javac`. 

![2022-02-11](https://user-images.githubusercontent.com/97484123/153645901-adcf5c1d-34a2-4364-a94f-bc3f7a3a1e31.png)

![2022-02-11 (1)](https://user-images.githubusercontent.com/97484123/153645984-72833339-7e15-4962-8ab4-c5704d6af057.png)
