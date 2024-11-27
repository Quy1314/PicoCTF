# [St3g0](https://play.picoctf.org/practice/challenge/305?category=4&difficulty=2&page=1&search=st)   
The challange file contains a png file named ```pico.flag.png```.To start, i tried checking it by imagemagick:  
```linux
user@LAPTOP-TL39B5OL:/mnt/c/Users/Hoang Quy/Downloads$ display pico.flag.png
```
![image](https://github.com/user-attachments/assets/987bacb6-b5cf-41d7-bd37-fab009601992)  
It seems there's nothing in the file so i used Binwalk to analize it for more information.  
![image](https://github.com/user-attachments/assets/cead83e5-b859-4038-8426-60a948de2fac)  
Nope!! After searched google, i find out a tools name zsteg which help me encrypte hide information in png file:  
```linux
user@LAPTOP-TL39B5OL:/mnt/c/Users/Hoang Quy/Downloads$ zsteg pico.flag.png
b1,r,lsb,xy         .. text: "~__B>VG?G@"
b1,rgb,lsb,xy       .. text: "picoCTF{7h3r3_15_n0_5p00n_a9a181eb}$t3g0"  
b1,abgr,lsb,xy      .. text: "E2A5q4E%uSA"
b2,b,lsb,xy         .. text: "AAPAAQTAAA"
b2,b,msb,xy         .. text: "HWUUUUUU"
b3,r,lsb,xy         .. file: gfxboot compiled html help file
b4,r,lsb,xy         .. file: Targa image data (16-273) 65536 x 4097 x 1 +4352 +4369 - 1-bit alpha - right "\021\020\001\001\021\021\001\001\021\021\001"
b4,g,lsb,xy         .. file: 0420 Alliant virtual executable not stripped
b4,b,lsb,xy         .. file: Targa image data - Map 272 x 17 x 16 +257 +272 - 1-bit alpha "\020\001\021\001\021\020\020\001\020\001\020\001"
b4,bgr,lsb,xy       .. file: Targa image data - Map 273 x 272 x 16 +1 +4113 - 1-bit alpha "\020\001\001\001"
b4,rgba,msb,xy      .. file: Applesoft BASIC program data, first line number 8
```
The flag is : **```picoCTF{7h3r3_15_n0_5p00n_a9a181eb}$t3g0```**

