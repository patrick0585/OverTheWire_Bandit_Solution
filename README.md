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

## Bandit Level 7 -> 8

### Level Goal
The password for the next level is stored in the file data.txt next to the word millionth

### Solution
```
ssh bandit7@bandit.labs.overthewire.org -p 2220
```
```
bandit7@bandit:~$ ls -al
total 4108
drwxr-xr-x  2 root    root       4096 Oct 16  2018 .
drwxr-xr-x 41 root    root       4096 Oct 16  2018 ..
-rw-r--r--  1 root    root        220 May 15  2017 .bash_logout
-rw-r--r--  1 root    root       3526 May 15  2017 .bashrc
-rw-r-----  1 bandit8 bandit7 4184396 Oct 16  2018 data.txt
-rw-r--r--  1 root    root        675 May 15  2017 .profile
```
```
bandit7@bandit:~$ grep "millionth" data.txt 
millionth	cvX2JJa4CFALtqS87jk27qwqGhBM9plV
```
Password for the Level 8 **cvX2JJa4CFALtqS87jk27qwqGhBM9plV**

## Bandit Level 8 -> 9

### Level Goal
The password for the next level is stored in the file data.txt and is the only line of text that occurs only once

### Solution
```
ssh bandit8@bandit.labs.overthewire.org -p 2220
```
```
bandit8@bandit:~$ ls -al
total 56
drwxr-xr-x  2 root    root     4096 Oct 16  2018 .
drwxr-xr-x 41 root    root     4096 Oct 16  2018 ..
-rw-r--r--  1 root    root      220 May 15  2017 .bash_logout
-rw-r--r--  1 root    root     3526 May 15  2017 .bashrc
-rw-r-----  1 bandit9 bandit8 33033 Oct 16  2018 data.txt
-rw-r--r--  1 root    root      675 May 15  2017 .profile
```
```
bandit8@bandit:~$ sort data.txt | uniq -u
UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR
```

Password for the Level 9 **UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR**

## Bandit Level 9 -> 10

### Level Goal
The password for the next level is stored in the file data.txt in one of the few human-readable strings, beginning with several ‘=’ characters.

### Solution
```
ssh bandit9@bandit.labs.overthewire.org -p 2220
```
```
bandit9@bandit:~$ strings data.txt | grep "=="
2========== the
========== password
========== isa
========== truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk
```
Password for the Level 10 **truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk**

## Bandit Level 10 -> 11

### Level Goal
The password for the next level is stored in the file data.txt, which contains base64 encoded data

### Solution
```
ssh bandit10@bandit.labs.overthewire.org -p 2220
```
```
bandit10@bandit:~$ base64 --decode data.txt 
The password is IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR
```
Password for the Level 11 **IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR**

## Bandit Level 11 -> 12

### Level Goal
The password for the next level is stored in the file data.txt, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions

### Solution
```
ssh bandit11@bandit.labs.overthewire.org -p 2220
```
```
bandit11@bandit:~$ cat data.txt | tr '[a-zA-Z]' '[n-za-mN-ZA-M]'
The password is 5Te8Y4drgCRfCx8ugdwuEX8KFC6k2EUu
```
Password for the Level 12 **5Te8Y4drgCRfCx8ugdwuEX8KFC6k2EUu**

## Bandit Level 12 -> 13

### Level Goal
The password for the next level is stored in the file data.txt, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work using mkdir. For example: mkdir /tmp/myname123. Then copy the datafile using cp, and rename it using mv (read the manpages!)

### Solution
```
ssh bandit12@bandit.labs.overthewire.org -p 2220
```
```
bandit12@bandit:~$ mkdir /tmp/maxmustermann123
bandit12@bandit:~$ cd /tmp/maxmustermann123
bandit12@bandit:/tmp/maxmustermann123$ cp ~/data.txt  .
```
```
bandit12@bandit:/tmp/maxmustermann123$ xxd -r data.txt > first
bandit12@bandit:/tmp/maxmustermann123$ file first 
first: gzip compressed data, was "data2.bin", last modified: Tue Oct 16 12:00:23 2018, max compression, from Unix
```
```
bandit12@bandit:/tmp/maxmustermann123$ mv first first.gz
bandit12@bandit:/tmp/maxmustermann123$ gzip -d first.gz 
bandit12@bandit:/tmp/maxmustermann123$ ls -al
total 305932
drwxr-sr-x 2 bandit12 root      4096 Apr 13 09:43 .
drwxrws-wt 1 root     root 313204736 Apr 13 09:44 ..
-rw-r----- 1 bandit12 root      2581 Apr 13 09:40 data.txt
-rw-r--r-- 1 bandit12 root       572 Apr 13 09:42 first
bandit12@bandit:/tmp/maxmustermann123$ file first 
first: bzip2 compressed data, block size = 900k
```
```
bandit12@bandit:/tmp/maxmustermann123$ mv first first.bz2
bandit12@bandit:/tmp/maxmustermann123$ bzip2 -d first.bz2 
bandit12@bandit:/tmp/maxmustermann123$ file first 
first: gzip compressed data, was "data4.bin", last modified: Tue Oct 16 12:00:23 2018, max compression, from Unix
```
```
bandit12@bandit:/tmp/maxmustermann123$ mv first first.gz
bandit12@bandit:/tmp/maxmustermann123$ gzip -d first.gz 
bandit12@bandit:/tmp/maxmustermann123$ file first 
first: POSIX tar archive (GNU)
```
```
bandit12@bandit:/tmp/maxmustermann123$ mv first first.tar
bandit12@bandit:/tmp/maxmustermann123$ tar xvf first.tar 
data5.bin
bandit12@bandit:/tmp/maxmustermann123$ file first.tar 
first.tar: POSIX tar archive (GNU)
bandit12@bandit:/tmp/maxmustermann123$ file data5.bin 
data5.bin: POSIX tar archive (GNU)
```
```
bandit12@bandit:/tmp/maxmustermann123$ mv data5.bin data5.tar
bandit12@bandit:/tmp/maxmustermann123$ tar xvf data5.tar 
data6.bin
bandit12@bandit:/tmp/maxmustermann123$ file data6.bin 
data6.bin: bzip2 compressed data, block size = 900k
```
```
bandit12@bandit:/tmp/maxmustermann123$ mv data6.bin data6.bz2
bandit12@bandit:/tmp/maxmustermann123$ bzip2 -d data6.bz2 
bandit12@bandit:/tmp/maxmustermann123$ file data6 
data6: POSIX tar archive (GNU)
```
```
bandit12@bandit:/tmp/maxmustermann123$ mv data6 data6.tar
bandit12@bandit:/tmp/maxmustermann123$ tar xvf data6.tar 
data8.bin
bandit12@bandit:/tmp/maxmustermann123$ file data8.bin 
data8.bin: gzip compressed data, was "data9.bin", last modified: Tue Oct 16 12:00:23 2018, max compression, from Unix
```
```
bandit12@bandit:/tmp/maxmustermann123$ mv data8.bin data8.gz
bandit12@bandit:/tmp/maxmustermann123$ gzip -d data8.gz 
bandit12@bandit:/tmp/maxmustermann123$ file data8
data8: ASCII text
bandit12@bandit:/tmp/maxmustermann123$ cat data8
The password is 8ZjyCRiBWFYkneahHwxCv3wb2a1ORpYL
```

Password for the Level 13 **8ZjyCRiBWFYkneahHwxCv3wb2a1ORpYL**

## Bandit Level 13 -> 14

### Level Goal
The password for the next level is stored in /etc/bandit_pass/bandit14 and can only be read by user bandit14. For this level, you don’t get the next password, but you get a private SSH key that can be used to log into the next level. Note: localhost is a hostname that refers to the machine you are working on

### Solution
```
ssh bandit13@bandit.labs.overthewire.org -p 2220
```
```
bandit13@bandit:~$ ls -la
total 24
drwxr-xr-x  2 root     root     4096 Oct 16  2018 .
drwxr-xr-x 41 root     root     4096 Oct 16  2018 ..
-rw-r--r--  1 root     root      220 May 15  2017 .bash_logout
-rw-r--r--  1 root     root     3526 May 15  2017 .bashrc
-rw-r--r--  1 root     root      675 May 15  2017 .profile
-rw-r-----  1 bandit14 bandit13 1679 Oct 16  2018 sshkey.private

bandit13@bandit:~$ ssh -i sshkey.private bandit14@localhost

bandit14@bandit:~$ cat /etc/bandit_pass/bandit14
4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e
```

Password for the Level 14 **4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e**
