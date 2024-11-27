# [hideme](https://play.picoctf.org/practice/challenge/350?category=4&difficulty=2&page=1&search=)
The challenge file contains a png file name ```flag.png```
![image](https://github.com/user-attachments/assets/94dcd572-96b5-4853-ada4-8c6d45fc7eed)  
To start, i checked it by Binwalk a file and i noticed there're a lots of file in there.  
```linux
user@LAPTOP-TL39B5OL:/mnt/c/Users/Hoang Quy/Downloads$ binwalk flag.png

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 512 x 504, 8-bit/color RGBA, non-interlaced
41            0x29            Zlib compressed data, compressed
39739         0x9B3B          Zip archive data, at least v1.0 to extract, name: secret/
39804         0x9B7C          Zip archive data, at least v2.0 to extract, compressed size: 2959, uncompressed size: 3108, name: secret/flag.png
42998         0xA7F6          End of Zip archive, footer length: 22  
```
So i extract all of them into a file name ```_flag.png.extracted``` :  
```linux
user@LAPTOP-TL39B5OL:/mnt/c/Users/Hoang Quy/Downloads$ binwalk -e flag.png

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 512 x 504, 8-bit/color RGBA, non-interlaced
41            0x29            Zlib compressed data, compressed
39739         0x9B3B          Zip archive data, at least v1.0 to extract, name: secret/
39804         0x9B7C          Zip archive data, at least v2.0 to extract, compressed size: 2959, uncompressed size: 3108, name: secret/flag.png
42998         0xA7F6          End of Zip archive, footer length: 22
```
These file include a file named ```secret``` which contains PNG file with the flag named ```flag.png```  
![image](https://github.com/user-attachments/assets/b176584a-fe71-49c3-826e-bc419ed5f140)
Flag: **```picoCTF{Hiddinng_An_imag3_within_@n_ima9e_dc2ab58f}```**
