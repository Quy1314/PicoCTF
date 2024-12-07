# [File types](https://play.picoctf.org/practice/challenge/268?category=4&difficulty=2&page=1&search=&solved=1)
The challenge gave me a pdf file which is corrupted. So i using ```file``` to inspect it file format and realized it is a sh file.  
```linux
user@LAPTOP-TL39B5OL:/mnt/c/Users/Hoang Quy/Downloads$ file Flag.pdf
Flag.pdf: shell archive text
```
I decided to changed it file extension to sh and binwalk it.  
```linux
user@LAPTOP-TL39B5OL:/mnt/c/Users/Hoang Quy/Downloads$ mv Flag.pdf FLag.sh
user@LAPTOP-TL39B5OL:/mnt/c/Users/Hoang Quy/Downloads$ binwalk Flag.sh

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             Executable script, shebang: "/bin/sh"
168           0xA8            Executable script, shebang: "/bin/sh' line above, then type 'sh FILE'."
3029          0xBD5           uuencoded data, file name: "flag", file permissions: "600"

user@LAPTOP-TL39B5OL:/mnt/c/Users/Hoang Quy/Downloads$ binwalk -e Flag.sh

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             Executable script, shebang: "/bin/sh"
168           0xA8            Executable script, shebang: "/bin/sh' line above, then type 'sh FILE'."
3029          0xBD5           uuencoded data, file name: "flag", file permissions: "600"
```
This created a new file named flag which contains bzip2 compressed data so i continue binwalk it and obtained extracted direction.  
```linux
user@LAPTOP-TL39B5OL:/mnt/c/Users/Hoang Quy/Downloads$ file flag
flag: current ar archive
user@LAPTOP-TL39B5OL:/mnt/c/Users/Hoang Quy/Downloads$ binwalk flag

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
100           0x64            bzip2 compressed data, block size = 900k

user@LAPTOP-TL39B5OL:/mnt/c/Users/Hoang Quy/Downloads$ binwalk -e flag

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
100           0x64            bzip2 compressed data, block size = 900k
```
Then i continue binwak a file named ```64``` and obtained 2 compressed file.  
```linux
user@LAPTOP-TL39B5OL:/mnt/c/Users/Hoang Quy/Downloads/_flag.extracted$ file 64
64: gzip compressed data, was "flag", last modified: Thu Mar 16 01:40:15 2023, from Unix, original size modulo 2^32 328
user@LAPTOP-TL39B5OL:/mnt/c/Users/Hoang Quy/Downloads/_flag.extracted$ binwalk -e 64

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             gzip compressed data, has original file name: "flag", from Unix, last modified: 2023-03-16 01:40:15
20            0x14            lzip compressed data, version: 1

user@LAPTOP-TL39B5OL:/mnt/c/Users/Hoang Quy/Downloads/_flag.extracted$ ls
64  _64.extracted
```
After i extracted a ```flag``` file using ```lzip```, it created a new file named ```flag.out``` which is lz4 file.  
```linux
user@LAPTOP-TL39B5OL:/mnt/c/Users/Hoang Quy/Downloads/_flag.extracted/_64.extracted$ file flag
flag: lzip compressed data, version: 1
user@LAPTOP-TL39B5OL:/mnt/c/Users/Hoang Quy/Downloads/_flag.extracted/_64.extracted$ lzip -d -k flag
user@LAPTOP-TL39B5OL:/mnt/c/Users/Hoang Quy/Downloads/_flag.extracted/_64.extracted$ ls
flag  flag.gz  flag.out
user@LAPTOP-TL39B5OL:/mnt/c/Users/Hoang Quy/Downloads/_flag.extracted/_64.extracted$ file flag.out
flag.out: LZ4 compressed data (v1.4+)
```
I redo it untill i find out a ASCII text file which is conntains the flag after decoded it.
```linux
user@LAPTOP-TL39B5OL:/mnt/c/Users/Hoang Quy/Downloads/_flag.extracted/_64.extracted$ file flag4
flag4: ASCII text
user@LAPTOP-TL39B5OL:/mnt/c/Users/Hoang Quy/Downloads/_flag.extracted/_64.extracted$ strings flag4
7069636f4354467b66316c656e406d335f6d406e3170756c407431306e5f
6630725f3062326375723137795f33633739633562617d0a
```
![image](https://github.com/user-attachments/assets/a882fb65-f2e0-4f66-8a12-64a3e34835ca)  
## FLAG: ***```picoCTF{f1len@m3_m@n1pul@t10n_f0r_0b2cur17y_3c79c5ba}```***


