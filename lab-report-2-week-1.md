## installing vscode

<img width="1512" alt="Screen Shot 2022-09-30 at 10 40 08 PM" src="https://user-images.githubusercontent.com/68624067/193394509-eb8d8438-6bc2-4c96-8de3-33f63f0d29e4.png">
1. navigate to this [url][1]
[1]: https://code.visualstudio.com/

2. click download

## remotely connecting

<img width="538" alt="Screen Shot 2022-09-30 at 10 59 10 PM" src="https://user-images.githubusercontent.com/68624067/193395066-fa395335-b5c3-459d-b3da-28352cec15d6.png">
enter the following commands on the terminal:
```
ssh cs15lfa22zz@ieng6.ucsd.edu (zz replaced by the letters in your course-specific account)

# first time login message
The authenticity of host 'ieng6.ucsd.edu (128.54.70.227)' can't be established.
RSA key fingerprint is SHA256:ksruYwhnYH+sySHnHAtLUHngrPEyZTDl/1x99wUQcec.
Are you sure you want to continue connecting (yes/no/[fingerprint])? 
(type yes)

Password: 
(type your password)

# login was successful
Last login: Sun Jan  2 14:03:05 2022 from 107-217-10-235.lightspeed.sndgca.sbcglobal.net
quota: No filesystem specified.
Hello cs15lfa22zz, you are currently logged into ieng6-203.ucsd.edu

You are using 0% CPU on this system

Cluster Status 
Hostname     Time    #Users  Load  Averages  
ieng6-201   23:25:01   0  0.08,  0.17,  0.11
ieng6-202   23:25:01   1  0.09,  0.15,  0.11
ieng6-203   23:25:01   1  0.08,  0.15,  0.11

Sun Jan 02, 2022 11:28pm - Prepping cs15lfa22
```

## trying some commands


here are some commands to try:
1. ls
- displays all files

2. cd 'path/to/directory/'
- navigate files and folders

<img width="431" alt="Screen Shot 2022-09-30 at 11 01 36 PM" src="https://user-images.githubusercontent.com/68624067/193395179-e9134523-1784-4cb2-bfab-0b7661219416.png">
3. ls -lat
- displays all recently edited files

<img width="576" alt="Screen Shot 2022-09-30 at 11 03 13 PM" src="https://user-images.githubusercontent.com/68624067/193395220-4b6f2e82-0285-40cb-975b-0d9792ca0ca2.png">
4. ls -a
- displays all hidden files


## moving files with scp

```
# example code, name the file WhereAmI.java
class WhereAmI {
  public static void main(String[] args) {
    System.out.println(System.getProperty("os.name"));
    System.out.println(System.getProperty("user.name"));
    System.out.println(System.getProperty("user.home"));
    System.out.println(System.getProperty("user.dir"));
  }
}
```

<img width="564" alt="Screen Shot 2022-09-30 at 11 13 43 PM" src="https://user-images.githubusercontent.com/68624067/193395546-31384cba-8343-4aea-ab8f-0c43479a6158.png">
enter the following commands on the terminal:
```
scp WhereAmI.java cs15lfa22zz@ieng6.ucsd.edu:~/ (zz replaced by the letters in your course-specific account)
javac WhereAmI.java (compiles code)
java WhereAmI (runs code)
```

## setting an ssh key

enter the following commands on the terminal:
```
ssh-keygen

# generates rsa public and private keys
Generating public/private rsa key pair.
Enter file in which to save the key (/Users/kennyzhang/.ssh/id_rsa): 
(press enter)
Enter passphrase (empty for no passphrase): 
(press enter)
Enter same passphrase again: 
(press enter)

# rsa public and private keys generated
Your identification has been saved in /Users/kennyzhang/.ssh/id_rsa.
Your public key has been saved in /Users/kennyzhang/.ssh/id_rsa.pub. (remember where this file is stored)
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

ssh cs15lfa22zz@ieng6.ucsd.edu (zz replaced by the letters in your course-specific account)

Password: 
(type your password)
mkdir .ssh
exit
scp /Users/kennyzhang/.ssh/id_rsa.pub cs15lfa22zz@ieng6.ucsd.edu:~/.ssh/authorized_keys (zz replaced by the letters in your course-specific account)

Password:
(type your password)
```
<img width="1512" alt="Screen Shot 2022-09-30 at 10 40 08 PM" src="https://user-images.githubusercontent.com/68624067/193395734-781288a0-f4c4-46ac-b3fe-39799c5e1e82.png">


## optimizing remote running
use the up and down arrows to quickly run previously run commands

for example:
```
ssh cs15lfa22zz@ieng6.ucsd.edu
exit
(if you need to log in again, press the up arrow twice to retrieve the ssh login command you previously entered)
```
