# Solution for the wargame bandit from [OverTheWire](https://overthewire.org/wargames/bandit)

##### Table of Contents
...

## Bandit Level 0

### Level Goal
The goal of this level is for you to log into the game using SSH. The host to which you need to connect is bandit.labs.overthewire.org, on port 2220. The username is bandit0 and the password is bandit0. Once logged in, go to the Level 1 page to find out how to beat Level 1.

### Solution
```
ssh bandit0@bandit.labs.overthewire.org -p 2220
```

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
Password for the Level 1 **boJ9jbbUNNfktd78OOpsqOltutMc3MY1**

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
Password for the Level 2 **CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9**

## Bandit Level 2 -> 3

### Level Goal
The password for the next level is stored in a file called spaces in this filename located in the home directory

### Solution
```
ssh bandit2@bandit.labs.overthewire.org -p 2220
```
```
bandit2@bandit:~$ ls -al
total 24
drwxr-xr-x  2 root    root    4096 Oct 16  2018 .
drwxr-xr-x 41 root    root    4096 Oct 16  2018 ..
-rw-r--r--  1 root    root     220 May 15  2017 .bash_logout
-rw-r--r--  1 root    root    3526 May 15  2017 .bashrc
-rw-r--r--  1 root    root     675 May 15  2017 .profile
-rw-r-----  1 bandit3 bandit2   33 Oct 16  2018 spaces in this filename
```
```
bandit2@bandit:~$ cat "spaces in this filename" 
UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK
```
Password for the Level 3 **UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK**

## Bandit Level 3 -> 4

### Level Goal
The password for the next level is stored in a hidden file in the inhere directory.

### Solution
```
ssh bandit3@bandit.labs.overthewire.org -p 2220
```
```
bandit3@bandit:~$ ls -al
total 24
drwxr-xr-x  3 root root 4096 Oct 16  2018 .
drwxr-xr-x 41 root root 4096 Oct 16  2018 ..
-rw-r--r--  1 root root  220 May 15  2017 .bash_logout
-rw-r--r--  1 root root 3526 May 15  2017 .bashrc
drwxr-xr-x  2 root root 4096 Oct 16  2018 inhere
-rw-r--r--  1 root root  675 May 15  2017 .profile
```
```
bandit3@bandit:~$ cat inhere/.hidden 
pIwrPrtPN36QITSp3EQaw936yaFoFgAB
```
Password for the Level 4 **pIwrPrtPN36QITSp3EQaw936yaFoFgAB**

## Bandit Level 4 -> 5

### Level Goal
The password for the next level is stored in the only human-readable file in the inhere directory. Tip: if your terminal is messed up, try the “reset” command.

### Solution
```
ssh bandit4@bandit.labs.overthewire.org -p 2220
```
```
bandit4@bandit:~$ find inhere/ -type f | xargs file
inhere/-file09: data
inhere/-file06: data
inhere/-file01: data
inhere/-file02: data
inhere/-file05: data
inhere/-file03: data
inhere/-file08: data
inhere/-file07: ASCII text
inhere/-file04: data
inhere/-file00: data
```
```
bandit4@bandit:~$ cat inhere/-file07
koReBOKuIDDepwhWk7jZC0RTdopnAYKh
```

Password for the Level 5 **koReBOKuIDDepwhWk7jZC0RTdopnAYKh**

## Bandit Level 5 -> 6

### Level Goal
The password for the next level is stored in a file somewhere under the inhere directory and has all of the following properties:  
- human-readable  
- 1033 bytes in size  
- not executable

### Solution
```
ssh bandit5@bandit.labs.overthewire.org -p 2220
```
```
bandit5@bandit:~$ find inhere/ -type f -size 1033c ! -executable
inhere/maybehere07/.file2
```
```
bandit5@bandit:~$ cat inhere/maybehere07/.file2
DXjZPULLxYr17uwoI01bNLQbtFemEgo7
```

Password for the Level 6 **DXjZPULLxYr17uwoI01bNLQbtFemEgo7**

## Bandit Level 6 -> 7

### Level Goal
The password for the next level is stored somewhere on the server and has all of the following properties:  
- owned by user bandit7  
- owned by group bandit6  
- 33 bytes in size

### Solution
```
ssh bandit6@bandit.labs.overthewire.org -p 2220
```
```
bandit6@bandit:~$ find / -type f -size 33c -user bandit7 -group bandit6 -print 2>/dev/null
/var/lib/dpkg/info/bandit7.password
```
```
bandit6@bandit:~$ cat /var/lib/dpkg/info/bandit7.password
HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs
```
Password for the Level 7 **HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs**
