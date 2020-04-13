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
```

```
bandit13@bandit:~$ ssh -i sshkey.private bandit14@localhost

bandit14@bandit:~$ cat /etc/bandit_pass/bandit14
4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e
```

Password for the Level 14 **4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e**

## Bandit Level 14 -> 15

### Level Goal
The password for the next level can be retrieved by submitting the password of the current level to port 30000 on localhost.

### Solution
```
ssh bandit13@bandit.labs.overthewire.org -p 2220
```
```
bandit14@bandit:~$ echo 4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e | nc localhost 30000
Correct!
BfMYroe26WYalil77FoDi9qh59eK5xNr
```

Password for the Level 15 **BfMYroe26WYalil77FoDi9qh59eK5xNr**

## Bandit Level 15 -> 16

### Level Goal
The password for the next level can be retrieved by submitting the password of the current level to port 30001 on localhost using SSL encryption.

Helpful note: Getting “HEARTBEATING” and “Read R BLOCK”? Use -ign_eof and read the “CONNECTED COMMANDS” section in the manpage. Next to ‘R’ and ‘Q’, the ‘B’ command also works in this version of that command…

### Solution
```
ssh bandit15@bandit.labs.overthewire.org -p 2220
```
```
bandit15@bandit:~$ echo "BfMYroe26WYalil77FoDi9qh59eK5xNr" | openssl s_client -connect localhost:30001 -ign_eof
CONNECTED(00000003)
depth=0 CN = localhost
verify error:num=18:self signed certificate
verify return:1
depth=0 CN = localhost
verify return:1
---
Certificate chain
 0 s:/CN=localhost
   i:/CN=localhost
---
Server certificate
-----BEGIN CERTIFICATE-----
MIICBjCCAW+gAwIBAgIEYo1NxTANBgkqhkiG9w0BAQUFADAUMRIwEAYDVQQDDAls
b2NhbGhvc3QwHhcNMjAwMTA1MTQzNTU4WhcNMjEwMTA0MTQzNTU4WjAUMRIwEAYD
VQQDDAlsb2NhbGhvc3QwgZ8wDQYJKoZIhvcNAQEBBQADgY0AMIGJAoGBAKF4u2eu
a8VipZPviX0hfNiCnaD2ojAffdBhKTy1bmZSNRuHPBDnU7z8rblNSknSjCITda1C
GEAI8ZktRbtLpBTbYeTgqPN/EiN5UIRMKbU6P2O93zNFPBsmyfQLrgt+DSLnsxlB
i/yYyT7WLdtNVBpgwRwkqi9K7dk9vf9waswLAgMBAAGjZTBjMBQGA1UdEQQNMAuC
CWxvY2FsaG9zdDBLBglghkgBhvhCAQ0EPhY8QXV0b21hdGljYWxseSBnZW5lcmF0
ZWQgYnkgTmNhdC4gU2VlIGh0dHBzOi8vbm1hcC5vcmcvbmNhdC8uMA0GCSqGSIb3
DQEBBQUAA4GBAJECW6IB3Ria4xG002BqD3zEbtmrDlK6nmJq+uQ4eJ6cT18o9REb
npy/lFzlv2LfcrYAnuAp6Fh89MKaYjNzJURjRQ9RkmcYgQJa1n+OBkATb7V+84/a
k9PDRkscxdNFMGBSvzFD33XZ5lbaGdrwCPyoxenoYghV/753wffN7J6H
-----END CERTIFICATE-----
subject=/CN=localhost
issuer=/CN=localhost
---
No client certificate CA names sent
Peer signing digest: SHA512
Server Temp Key: X25519, 253 bits
---
SSL handshake has read 1019 bytes and written 269 bytes
Verification error: self signed certificate
---
New, TLSv1.2, Cipher is ECDHE-RSA-AES256-GCM-SHA384
Server public key is 1024 bit
Secure Renegotiation IS supported
Compression: NONE
Expansion: NONE
No ALPN negotiated
SSL-Session:
    Protocol  : TLSv1.2
    Cipher    : ECDHE-RSA-AES256-GCM-SHA384
    Session-ID: 9815661C67CD4473F606EFDF941766AA5E2036296316731CA60E1CDD163B47BA
    Session-ID-ctx: 
    Master-Key: 4849027516B721FAFC40B8C45EB509AA2594CEC535320DCF3304D15907C75B72B77D34B3CE2D84F38CE2C7DBE18D3226
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 56 e9 4e 87 6a 28 48 d0-13 42 5f b9 61 b0 dd d0   V.N.j(H..B_.a...
    0010 - 1e ce 18 52 0d 96 e9 ba-c7 54 51 2a b5 5c c5 00   ...R.....TQ*.\..
    0020 - da 6f c5 12 b2 cd a0 b0-71 f8 3a 5e ac e4 3e 15   .o......q.:^..>.
    0030 - f2 57 62 7f 74 13 e4 57-70 07 8e 0b 1e 88 e9 06   .Wb.t..Wp.......
    0040 - 9b 62 1d 86 b5 1c 7c 21-38 df c9 82 fd 30 5c 9e   .b....|!8....0\.
    0050 - bd b8 4e 02 6c 41 68 78-4b 0a 4c c9 cb 45 6d ed   ..N.lAhxK.L..Em.
    0060 - 92 78 67 30 0e 17 25 c8-c8 79 78 80 f1 c7 24 67   .xg0..%..yx...$g
    0070 - 75 8c dc 3d 12 91 77 2b-74 a8 01 e6 4c ea 0f cd   u..=..w+t...L...
    0080 - fb 61 be 9e d5 34 0f 81-54 e7 73 94 6b 73 9d b7   .a...4..T.s.ks..
    0090 - 0a ae 4a f2 28 f8 36 bd-3a 9a 82 1a ab b3 88 22   ..J.(.6.:......"

    Start Time: 1586771088
    Timeout   : 7200 (sec)
    Verify return code: 18 (self signed certificate)
    Extended master secret: yes
---
Correct!
cluFn7wTiGryunymYOu4RcffSxQluehd

closed

```

Password for the Level 16 **cluFn7wTiGryunymYOu4RcffSxQluehd**

## Bandit Level 16 -> 17

### Level Goal
The credentials for the next level can be retrieved by submitting the password of the current level to a port on localhost in the range 31000 to 32000. First find out which of these ports have a server listening on them. Then find out which of those speak SSL and which don’t. There is only 1 server that will give the next credentials, the others will simply send back to you whatever you send to it.

### Solution
```
ssh bandit16@bandit.labs.overthewire.org -p 2220
```
```
bandit16@bandit:~$ nc -zv -w 1 localhost 31000-32000
localhost [127.0.0.1] 31790 (?) open
localhost [127.0.0.1] 31518 (?) : Connection timed out
```
```
bandit16@bandit:~$ echo "cluFn7wTiGryunymYOu4RcffSxQluehd" | openssl s_client -connect localhost:31790 -ign_eof
CONNECTED(00000003)
depth=0 CN = localhost
verify error:num=18:self signed certificate
verify return:1
depth=0 CN = localhost
verify return:1
---
Certificate chain
 0 s:/CN=localhost
   i:/CN=localhost
---
Server certificate
-----BEGIN CERTIFICATE-----
MIICBjCCAW+gAwIBAgIEBKMOoTANBgkqhkiG9w0BAQUFADAUMRIwEAYDVQQDDAls
b2NhbGhvc3QwHhcNMjAwNDA2MjIzMjQyWhcNMjEwNDA2MjIzMjQyWjAUMRIwEAYD
VQQDDAlsb2NhbGhvc3QwgZ8wDQYJKoZIhvcNAQEBBQADgY0AMIGJAoGBALags2qr
lWfnM53o914J6CWEJ/gm8EnVrIzBRKUvWzHfiviUw9pcRDPb4sisxcrwts23fzh4
LDGAuytnRxe5CeVmdJm+wNYK0tKR5FHwGgicDShmj+THsCiPRlF25jhgPZwKt2zs
m5IFth2KrMI1PmBYpV7Kdomw/6E61Z6qIj1zAgMBAAGjZTBjMBQGA1UdEQQNMAuC
CWxvY2FsaG9zdDBLBglghkgBhvhCAQ0EPhY8QXV0b21hdGljYWxseSBnZW5lcmF0
ZWQgYnkgTmNhdC4gU2VlIGh0dHBzOi8vbm1hcC5vcmcvbmNhdC8uMA0GCSqGSIb3
DQEBBQUAA4GBAJBZ5d4MkQZi3o1aQYdcoqF5skeRHBiurIKzIruuAxY0A+3BY46J
4HXHlslM0PAGnpSFVs0iEV3dgDtSW+pZECbycZpuZ5auOxkQ0on/2Zx0OXzQUbYP
j4xvM1i8c8NpUqmFMcSn4ND+5nLI53ka6DE4PVfsxfPHa3IIJoV4yE9a
-----END CERTIFICATE-----
subject=/CN=localhost
issuer=/CN=localhost
---
No client certificate CA names sent
Peer signing digest: SHA512
Server Temp Key: X25519, 253 bits
---
SSL handshake has read 1019 bytes and written 269 bytes
Verification error: self signed certificate
---
New, TLSv1.2, Cipher is ECDHE-RSA-AES256-GCM-SHA384
Server public key is 1024 bit
Secure Renegotiation IS supported
Compression: NONE
Expansion: NONE
No ALPN negotiated
SSL-Session:
    Protocol  : TLSv1.2
    Cipher    : ECDHE-RSA-AES256-GCM-SHA384
    Session-ID: 634A879E4873BCA1EDC7343C681A0B924AD0CE0B0E61BEF609D0FAA4093200D4
    Session-ID-ctx: 
    Master-Key: 8FD9E8631E55D3DBDAF60D8B5379DFF6986A41173E09B1AB6BDD5CB885F71B406482C9387618BFE6FB6B4FE4BA654EF9
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 8e 9a 4d ec 1c f4 6b 35-30 ba 86 7d cf 4c 4a 6d   ..M...k50..}.LJm
    0010 - dd 6b 4a 52 9d 32 67 52-51 d7 c4 71 4b d4 a0 84   .kJR.2gRQ..qK...
    0020 - 4f ef 31 48 c5 e1 33 09-ac 2e 9c 65 94 ed 7f dd   O.1H..3....e....
    0030 - 1c c2 8b 80 cd a9 62 1e-a7 f3 56 f5 5b a2 ba 1a   ......b...V.[...
    0040 - 72 56 42 39 7d 3d 6e 6e-50 a0 a3 ce ff 78 e8 08   rVB9}=nnP....x..
    0050 - de 33 3f c9 70 75 a3 60-f7 1b b8 3a ff 84 e6 a2   .3?.pu.`...:....
    0060 - 94 c6 f6 1a ba 34 f4 5e-8c 4d 23 a8 a7 25 96 d3   .....4.^.M#..%..
    0070 - f4 19 b3 bd b3 ea 2e 06-6f 5c 33 1c 02 ef ed 13   ........o\3.....
    0080 - ed f9 c3 b8 84 70 68 dc-1d ca f2 2f 62 e3 f1 bb   .....ph..../b...
    0090 - b1 af a1 5e 67 e4 44 f9-21 fc b1 5a 3a 4b 01 47   ...^g.D.!..Z:K.G

    Start Time: 1586771581
    Timeout   : 7200 (sec)
    Verify return code: 18 (self signed certificate)
    Extended master secret: yes
---
Correct!
-----BEGIN RSA PRIVATE KEY-----
MIIEogIBAAKCAQEAvmOkuifmMg6HL2YPIOjon6iWfbp7c3jx34YkYWqUH57SUdyJ
imZzeyGC0gtZPGujUSxiJSWI/oTqexh+cAMTSMlOJf7+BrJObArnxd9Y7YT2bRPQ
Ja6Lzb558YW3FZl87ORiO+rW4LCDCNd2lUvLE/GL2GWyuKN0K5iCd5TbtJzEkQTu
DSt2mcNn4rhAL+JFr56o4T6z8WWAW18BR6yGrMq7Q/kALHYW3OekePQAzL0VUYbW
JGTi65CxbCnzc/w4+mqQyvmzpWtMAzJTzAzQxNbkR2MBGySxDLrjg0LWN6sK7wNX
x0YVztz/zbIkPjfkU1jHS+9EbVNj+D1XFOJuaQIDAQABAoIBABagpxpM1aoLWfvD
KHcj10nqcoBc4oE11aFYQwik7xfW+24pRNuDE6SFthOar69jp5RlLwD1NhPx3iBl
J9nOM8OJ0VToum43UOS8YxF8WwhXriYGnc1sskbwpXOUDc9uX4+UESzH22P29ovd
d8WErY0gPxun8pbJLmxkAtWNhpMvfe0050vk9TL5wqbu9AlbssgTcCXkMQnPw9nC
YNN6DDP2lbcBrvgT9YCNL6C+ZKufD52yOQ9qOkwFTEQpjtF4uNtJom+asvlpmS8A
vLY9r60wYSvmZhNqBUrj7lyCtXMIu1kkd4w7F77k+DjHoAXyxcUp1DGL51sOmama
+TOWWgECgYEA8JtPxP0GRJ+IQkX262jM3dEIkza8ky5moIwUqYdsx0NxHgRRhORT
8c8hAuRBb2G82so8vUHk/fur85OEfc9TncnCY2crpoqsghifKLxrLgtT+qDpfZnx
SatLdt8GfQ85yA7hnWWJ2MxF3NaeSDm75Lsm+tBbAiyc9P2jGRNtMSkCgYEAypHd
HCctNi/FwjulhttFx/rHYKhLidZDFYeiE/v45bN4yFm8x7R/b0iE7KaszX+Exdvt
SghaTdcG0Knyw1bpJVyusavPzpaJMjdJ6tcFhVAbAjm7enCIvGCSx+X3l5SiWg0A
R57hJglezIiVjv3aGwHwvlZvtszK6zV6oXFAu0ECgYAbjo46T4hyP5tJi93V5HDi
Ttiek7xRVxUl+iU7rWkGAXFpMLFteQEsRr7PJ/lemmEY5eTDAFMLy9FL2m9oQWCg
R8VdwSk8r9FGLS+9aKcV5PI/WEKlwgXinB3OhYimtiG2Cg5JCqIZFHxD6MjEGOiu
L8ktHMPvodBwNsSBULpG0QKBgBAplTfC1HOnWiMGOU3KPwYWt0O6CdTkmJOmL8Ni
blh9elyZ9FsGxsgtRBXRsqXuz7wtsQAgLHxbdLq/ZJQ7YfzOKU4ZxEnabvXnvWkU
YOdjHdSOoKvDQNWu6ucyLRAWFuISeXw9a/9p7ftpxm0TSgyvmfLF2MIAEwyzRqaM
77pBAoGAMmjmIJdjp+Ez8duyn3ieo36yrttF5NSsJLAbxFpdlc1gvtGCWW+9Cq0b
dxviW8+TFVEBl1O4f7HVm6EpTscdDxU+bCXWkfjuRb7Dy9GOtt9JPsX8MBTakzh3
vBgsyi/sN3RqRBcGU40fOoZyfAMT8s1m/uYv52O6IgeuZ/ujbjY=
-----END RSA PRIVATE KEY-----

closed
```
```
Save the key as bandit17.key
```
## Bandit Level 17 -> 18

### Level Goal
There are 2 files in the homedirectory: passwords.old and passwords.new. The password for the next level is in passwords.new and is the only line that has been changed between passwords.old and passwords.new

NOTE: if you have solved this level and see ‘Byebye!’ when trying to log into bandit18, this is related to the next level, bandit19

### Solution
```
ssh -i bandit17.key bandit17@bandit.labs.overthewire.org -p 2220
```
```
bandit17@bandit:~$ diff passwords.old passwords.new 
42c42
< hlbSBPAWJmL6WFDb06gpTx1pPButblOA
---
> kfBf3eYk5BPBRzwjqutbbfE887SVc5Yd
```

Password for the Level 18 **kfBf3eYk5BPBRzwjqutbbfE887SVc5Yd**

## Bandit Level 18 -> 19

### Level Goal
The password for the next level is stored in a file readme in the homedirectory. Unfortunately, someone has modified .bashrc to log you out when you log in with SSH.

### Solution
```
ssh bandit18@bandit.labs.overthewire.org -p 2220

Linux bandit 4.18.12 x86_64 GNU/Linux
               
      ,----..            ,----,          .---. 
     /   /   \         ,/   .`|         /. ./|
    /   .     :      ,`   .'  :     .--'.  ' ;
   .   /   ;.  \   ;    ;     /    /__./ \ : |
  .   ;   /  ` ; .'___,/    ,' .--'.  '   \' .
  ;   |  ; \ ; | |    :     | /___/ \ |    ' ' 
  |   :  | ; | ' ;    |.';  ; ;   \  \;      : 
  .   |  ' ' ' : `----'  |  |  \   ;  `      |
  '   ;  \; /  |     '   :  ;   .   \    .\  ; 
   \   \  ',  /      |   |  '    \   \   ' \ |
    ;   :    /       '   :  |     :   '  |--"  
     \   \ .'        ;   |.'       \   \ ;     
  www. `---` ver     '---' he       '---" ire.org     
               
              
Welcome to OverTheWire!

If you find any problems, please report them to Steven or morla on
irc.overthewire.org.

--[ Playing the games ]--

  This machine might hold several wargames. 
  If you are playing "somegame", then:

    * USERNAMES are somegame0, somegame1, ...
    * Most LEVELS are stored in /somegame/.
    * PASSWORDS for each level are stored in /etc/somegame_pass/.

  Write-access to homedirectories is disabled. It is advised to create a
  working directory with a hard-to-guess name in /tmp/.  You can use the
  command "mktemp -d" in order to generate a random and hard to guess
  directory in /tmp/.  Read-access to both /tmp/ and /proc/ is disabled
  so that users can not snoop on eachother. Files and directories with 
  easily guessable or short names will be periodically deleted!
	
  Please play nice:
      
    * don't leave orphan processes running
    * don't leave exploit-files laying around
    * don't annoy other players
    * don't post passwords or spoilers
    * again, DONT POST SPOILERS! 
      This includes writeups of your solution on your blog or website!

--[ Tips ]--

  This machine has a 64bit processor and many security-features enabled
  by default, although ASLR has been switched off.  The following
  compiler flags might be interesting:

    -m32                    compile for 32bit
    -fno-stack-protector    disable ProPolice
    -Wl,-z,norelro          disable relro 

  In addition, the execstack tool can be used to flag the stack as
  executable on ELF binaries.

  Finally, network-access is limited for most levels by a local
  firewall.

--[ Tools ]--

 For your convenience we have installed a few usefull tools which you can find
 in the following locations:

    * pwndbg (https://github.com/pwndbg/pwndbg) in /usr/local/pwndbg/
    * peda (https://github.com/longld/peda.git) in /usr/local/peda/
    * gdbinit (https://github.com/gdbinit/Gdbinit) in /usr/local/gdbinit/
    * pwntools (https://github.com/Gallopsled/pwntools)
    * radare2 (http://www.radare.org/)
    * checksec.sh (http://www.trapkit.de/tools/checksec.html) in /usr/local/bin/checksec.sh

--[ More information ]--

  For more information regarding individual wargames, visit
  http://www.overthewire.org/wargames/

  For support, questions or comments, contact us through IRC on
  irc.overthewire.org #wargames.

  Enjoy your stay!

Byebye !
Connection to bandit.labs.overthewire.org closed.
```
```
ssh bandit18@bandit.labs.overthewire.org -p 2220 " cat ~/readme"
This is a OverTheWire game server. More information on http://www.overthewire.org/wargames

bandit18@bandit.labs.overthewire.org's password: 
IueksS7Ubh8G3DCwVzrTd8rAVOwq3M5x
```

Password for the Level 19 **IueksS7Ubh8G3DCwVzrTd8rAVOwq3M5x**

## Bandit Level 19 -> 20

### Level Goal
To gain access to the next level, you should use the setuid binary in the homedirectory. Execute it without arguments to find out how to use it. The password for this level can be found in the usual place (/etc/bandit_pass), after you have used the setuid binary.

### Solution
```
ssh bandit19@bandit.labs.overthewire.org -p 2220
```
```
bandit19@bandit:~$ ls -al
total 28
drwxr-xr-x  2 root     root     4096 Oct 16  2018 .
drwxr-xr-x 41 root     root     4096 Oct 16  2018 ..
-rwsr-x---  1 bandit20 bandit19 7296 Oct 16  2018 bandit20-do
-rw-r--r--  1 root     root      220 May 15  2017 .bash_logout
-rw-r--r--  1 root     root     3526 May 15  2017 .bashrc
-rw-r--r--  1 root     root      675 May 15  2017 .profile
```
```
bandit19@bandit:~$ ./bandit20-do 
Run a command as another user.
  Example: ./bandit20-do id
```
```
bandit19@bandit:~$ ./bandit20-do id
uid=11019(bandit19) gid=11019(bandit19) euid=11020(bandit20) groups=11019(bandit19)
```
```
bandit19@bandit:~$ ./bandit20-do cat /etc/bandit_pass/bandit20 
GbKksEFF4yrVs6il55v6gwY5aVje5f0j
```

Password for the Level 20 **GbKksEFF4yrVs6il55v6gwY5aVje5f0j**

## Bandit Level 20 -> 21

### Level Goal
There is a setuid binary in the homedirectory that does the following: it makes a connection to localhost on the port you specify as a commandline argument. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21).

NOTE: Try connecting to your own network daemon to see if it works as you think

### Solution
```
ssh bandit20@bandit.labs.overthewire.org -p 2220
```
```
bandit20@bandit:~$ echo "GbKksEFF4yrVs6il55v6gwY5aVje5f0j" | nc -l localhost -p 3333 &
```
```
bandit20@bandit:~$ ps aux | grep "3333"
bandit20 16152  0.0  0.0  12784   960 pts/26   S+   12:48   0:00 grep 3333
[1]+  Done                    echo "GbKksEFF4yrVs6il55v6gwY5aVje5f0j" | nc -l localhost -p 3333
```
```
bandit20@bandit:~$ ./suconnect 3333
Read: GbKksEFF4yrVs6il55v6gwY5aVje5f0j
Password matches, sending next password
gE269g2h3mw3pwgrj0Ha9Uoqen1c9DGr
```

Password for the Level 21 **gE269g2h3mw3pwgrj0Ha9Uoqen1c9DGr**

## Bandit Level 21 -> 22

### Level Goal
A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ for the configuration and see what command is being executed.

### Solution
```
ssh bandit21@bandit.labs.overthewire.org -p 2220
```
```
bandit21@bandit:~$ ls -al /etc/cron.d/
total 28
drwxr-xr-x  2 root root 4096 Dec  4 01:58 .
drwxr-xr-x 88 root root 4096 Aug  3  2019 ..
-rw-r--r--  1 root root  189 Jan 25  2017 atop
-rw-r--r--  1 root root  120 Oct 16  2018 cronjob_bandit22
-rw-r--r--  1 root root  122 Oct 16  2018 cronjob_bandit23
-rw-r--r--  1 root root  120 Oct 16  2018 cronjob_bandit24
-rw-r--r--  1 root root  102 Oct  7  2017 .placeholder
```
```
bandit21@bandit:~$ cat /usr/bin/cronjob_bandit22.sh 
#!/bin/bash
chmod 644 /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
cat /etc/bandit_pass/bandit22 > /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
```
```
bandit21@bandit:~$ cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
Yk7owGAcWjwMVRwrTesJEwB7WVOiILLI
```

Password for the Level 22 **Yk7owGAcWjwMVRwrTesJEwB7WVOiILLI**

## Bandit Level 22 -> 23

### Level Goal
A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ for the configuration and see what command is being executed.

NOTE: Looking at shell scripts written by other people is a very useful skill. The script for this level is intentionally made easy to read. If you are having problems understanding what it does, try executing it to see the debug information it prints.

### Solution
```
ssh bandit22@bandit.labs.overthewire.org -p 2220
```
```
bandit22@bandit:~$ ls -al /etc/cron.d
total 28
drwxr-xr-x  2 root root 4096 Dec  4 01:58 .
drwxr-xr-x 88 root root 4096 Aug  3  2019 ..
-rw-r--r--  1 root root  189 Jan 25  2017 atop
-rw-r--r--  1 root root  120 Oct 16  2018 cronjob_bandit22
-rw-r--r--  1 root root  122 Oct 16  2018 cronjob_bandit23
-rw-r--r--  1 root root  120 Oct 16  2018 cronjob_bandit24
-rw-r--r--  1 root root  102 Oct  7  2017 .placeholder
```
```
bandit22@bandit:~$ cat /etc/cron.d/cronjob_bandit23
@reboot bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
* * * * * bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
```
```
bandit22@bandit:~$ cat /usr/bin/cronjob_bandit23.sh 
#!/bin/bash

myname=$(whoami)
mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)

echo "Copying passwordfile /etc/bandit_pass/$myname to /tmp/$mytarget"

cat /etc/bandit_pass/$myname > /tmp/$mytarget
```
```
bandit22@bandit:~$ echo I am user bandit23 | md5sum | cut -d ' ' -f 1
8ca319486bfbbc3663ea0fbe81326349
```
```
bandit22@bandit:~$ cat /tmp/8ca319486bfbbc3663ea0fbe81326349
jc1udXuA1tiHqjIsL8yaapX5XIAI6i0n
```

Password for the Level 23 **jc1udXuA1tiHqjIsL8yaapX5XIAI6i0n**

## Bandit Level 23 -> 24

### Level Goal
A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ for the configuration and see what command is being executed.

NOTE: This level requires you to create your own first shell-script. This is a very big step and you should be proud of yourself when you beat this level!

NOTE 2: Keep in mind that your shell script is removed once executed, so you may want to keep a copy around…

### Solution
```
ssh bandit23@bandit.labs.overthewire.org -p 2220
```
```
bandit23@bandit:~$ ls -al /etc/cron.d
total 28
drwxr-xr-x  2 root root 4096 Dec  4 01:58 .
drwxr-xr-x 88 root root 4096 Aug  3  2019 ..
-rw-r--r--  1 root root  189 Jan 25  2017 atop
-rw-r--r--  1 root root  120 Oct 16  2018 cronjob_bandit22
-rw-r--r--  1 root root  122 Oct 16  2018 cronjob_bandit23
-rw-r--r--  1 root root  120 Oct 16  2018 cronjob_bandit24
-rw-r--r--  1 root root  102 Oct  7  2017 .placeholder
```
```
bandit23@bandit:~$ cat /etc/cron.d/cronjob_bandit24
@reboot bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
* * * * * bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
```
```
bandit23@bandit:~$ cat /usr/bin/cronjob_bandit24.sh 
#!/bin/bash

myname=$(whoami)

cd /var/spool/$myname
echo "Executing and deleting all scripts in /var/spool/$myname:"
for i in * .*;
do
    if [ "$i" != "." -a "$i" != ".." ];
    then
	echo "Handling $i"
	timeout -s 9 60 ./$i
	rm -f ./$i
    fi
done
```
```
bandit23@bandit:~$ mkdir /tmp/maxmustermann
bandit23@bandit:~$ cd /tmp/maxmustermann
```
```
bandit23@bandit:/tmp/maxmustermann$ touch getBandit24Pass.sh
bandit23@bandit:/tmp/maxmustermann$ chmod 777 getBandit24Pass.sh
bandit23@bandit:/tmp/maxmustermann$ cat getBandit24Pass.sh 
#!/bin/bash
cat /etc/bandit_pass/bandit24 > /tmp/maxmustermann/password
```
```
bandit23@bandit:/tmp/maxmustermann$ touch password
bandit23@bandit:/tmp/maxmustermann$ chmod 666 password 
bandit23@bandit:/tmp/maxmustermann$ ls -al
total 305928
drwxr-sr-x 2 bandit23 root      4096 Apr 13 13:11 .
drwxrws-wt 1 root     root 313204736 Apr 13 13:11 ..
-rwxrwxrwx 1 bandit23 root        65 Apr 13 13:10 getBandit24Pass.sh
-rw-rw-rw- 1 bandit23 root         0 Apr 13 13:11 password
bandit23@bandit:/tmp/maxmustermann$ 
```
```
bandit23@bandit:/tmp/maxmustermann$ cp getBandit24Pass.sh /var/spool/bandit24/
```
```
bandit23@bandit:/tmp/maxmustermann$ cat password 
UoMYTrfrBFHyQXmg6gzctqAwOmw1IohZ
```
Password for the Level 24 **UoMYTrfrBFHyQXmg6gzctqAwOmw1IohZ**
