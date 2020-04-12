# Solution for the wargame bandit from [OverTheWire](https://overthewire.org/wargames/bandit)

##### Table of Contents
[Bandit Level 0](#level0)  
[Bandit Level 0 -> 1](#level0_1)  
[Bandit Level 1 -> 2](#level0_1) 

<a name="level0"/>
## Bandit Level 0

### Level Goal
The goal of this level is for you to log into the game using SSH. The host to which you need to connect is bandit.labs.overthewire.org, on port 2220. The username is bandit0 and the password is bandit0. Once logged in, go to the Level 1 page to find out how to beat Level 1.

### Solution
```
ssh bandit0@bandit.labs.overthewire.org -p 2220
```
<a name="level0_1"/>
## Bandit Level 0 -> 1

### Level Goal
The password for the next level is stored in a file called readme located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.

### Solution
```
ssh bandit0@bandit.labs.overthewire.org -p 2220
```
```
bandit0@bandit:~$ cat readme 
boJ9jbbUNNfktd78OOpsqOltutMc3MY1
```
Password for the next level **boJ9jbbUNNfktd78OOpsqOltutMc3MY1**

<a name="level1_2"/>
## Bandit Level 1 -> 2

### Level Goal
The password for the next level is stored in a file called - located in the home directory

### Solution
```
ssh bandit1@bandit.labs.overthewire.org -p 2220
```
```
bandit1@bandit:~$ ls -al
total 24
-rw-r-----  1 bandit2 bandit1   33 Oct 16  2018 -
drwxr-xr-x  2 root    root    4096 Oct 16  2018 .
drwxr-xr-x 41 root    root    4096 Oct 16  2018 ..
-rw-r--r--  1 root    root     220 May 15  2017 .bash_logout
-rw-r--r--  1 root    root    3526 May 15  2017 .bashrc
-rw-r--r--  1 root    root     675 May 15  2017 .profile
```
```
bandit1@bandit:~$ cat ./-
CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9
```
Password for the next level **CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9**
