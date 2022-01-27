# **CSE 15L Lab Reports**

### 1. Installing VScode

Download VScode from the website: [https://code.visualstudio.com](https://code.visualstudio.com/) 

Remember to download the right version, like OSX (for Macs) and Windows (for PCs).\
After you successfully install VScode, it should look like this:

<img src="https://user-images.githubusercontent.com/97484123/149446111-913ba1ec-bca7-4146-9ce8-0ecc71448a00.png" width = "750"/>

### 2. Remotely Connecting

First, install the program called OpenSSH from this link: [https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse)

Secondly, look up your CSE 15L SSH account from here: [https://sdacs.ucsd.edu/~icc/index.php](https://sdacs.ucsd.edu/~icc/index.php)

Then, open a a terminal in VSCode by using "'Ctrl'  + 'shift' + '`'" or the Terminal → New Terminal menu option. Type the following command:

`$ ssh cs15lwi22zz@ieng6.ucsd.edu`

After you see a window like this:

`⤇ ssh cs15lwi22zz@ieng6.ucsd.edu
The authenticity of host 'ieng6.ucsd.edu (128.54.70.227)' can't be established.
RSA key fingerprint is SHA256:ksruYwhnYH+sySHnHAtLUHngrPEyZTDl/1x99wUQcec.
Are you sure you want to continue connecting (yes/no/[fingerprint])? `

Type `yes` and press enter. You will see a window like following:

<img src="https://user-images.githubusercontent.com/97484123/149449053-ab7dec7a-641c-40b0-9d0c-d7680403486e.png" width = "750"/>

### 3. Trying Some Commands
There are many commands you can try in the terminal, here are some examples:\
`cd` This takes you back home.\
`ls -lat` This lists all files (including hidden ones) and permissions of these files. The files are sort by time and date.\
`ls -a` This shows the hidden files.\
`mkdir` This makes a new directory.

If you want to log out of the remote server in your terminal, you can use:\
`Ctrl-D`\
The command `exit`

Below is an example terminal command:
<img src="https://user-images.githubusercontent.com/97484123/149447882-d0a1aac0-a268-44f6-8c7a-8afaaaef6451.png" width = "750"/>

### 4. Moving Files with scp

To move files from the *client* over to SSH (the *server*), you can use the command `scp`. Create a file on your computer called `WhereAmI.java` and put the following contents into it:

```
class WhereAmI {
  public static void main(String[] args) {
    System.out.println(System.getProperty("os.name"));
    System.out.println(System.getProperty("user.name"));
    System.out.println(System.getProperty("user.home"));
    System.out.println(System.getProperty("user.dir"));
  }
}
```

Then, go to the terminal from the directory where you made this file and run this command (replace *zz* with your username):

`scp WhereAmI.java cs15lwi22zz@ieng6.ucsd.edu:~/`

Your file is now moved to SSH! After entering `ls`, you should be able to see:

<img src="https://user-images.githubusercontent.com/97484123/149450159-36649086-a505-4c75-ae39-90eb072b1883.png" width = "750"/>

### 5. Setting an SSH Key

In order to not enter your password to log in every time, you can use an SSH key, and here is how it works:

On your computer (*client*), type the command:
`$ ssh-keygen`

Then this will show up:

```
Generating public/private rsa key pair.
Enter file in which to save the key (/Users/joe/.ssh/id_rsa): /Users/joe/.ssh/id_rsa
Enter passphrase (empty for no passphrase): 
Enter same passphrase again: 
Your identification has been saved in /Users/joe/.ssh/id_rsa.
Your public key has been saved in /Users/joe/.ssh/id_rsa.pub.
The key fingerprint is:
SHA256:jZaZH6fI8E2I1D35hnvGeBePQ4ELOf2Ge+G0XknoXp0 joe@Joes-Mac-mini.local
The key's randomart image is:
+---[RSA 3072]----+
|                 |
|       . . + .   |
|      . . B o .  |
|     . . B * +.. |
|      o S = *.B. |
|       = = O.*.*+|
|        + * *.BE+|
|           +.+.o |
|             ..  |
+----[SHA256]-----+
```

If you are using Windows, there are a few more `ssh-add` steps, follow the instructions here: [https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_keymanagement#user-key-generation](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_keymanagement#user-key-generation)

Now we need to copy the public key to the `.ssh` directory of your user account on the server. After logging into your account, on the server, enter `mkdir .ssh`. Then, log out and follow the steps:

```
$ ssh cs15lwi22zz@ieng6.ucsd.edu
<Enter Password>
# now on server
$ mkdir .ssh
$ <logout>
# back on client
$ scp /Users/joe/.ssh/id_rsa.pub cs15lwi22@ieng6.ucsd.edu:~/.ssh/authorized_keys
# You use your username and the path you saw in the command above
```

After this step you should be able to log in withour entering your password:

<img src="https://user-images.githubusercontent.com/97484123/149450678-f6b22728-50fc-4a1d-b64e-b0b2ce118a31.png" width = "750"/>

### 6. Optimizing Remote Running

You can write a command at the end an ssh command to directly run it on the remote server, then immediately exit.
`$ ssh cs15lwi22@ieng6.ucsd.edu "ls"`

You can also run multiple commands on the same line.
`$ cp WhereAmI.java OtherMain.java; javac OtherMain.java; java WhereAmI`

The example is shown below.
![2022-01-06 (6)](https://user-images.githubusercontent.com/97484123/151295351-0bb443f0-6edd-4c54-88c3-60cb98acab4e.png)


