# [Invisible WORDs](https://play.picoctf.org/practice/challenge/354?category=4&difficulty=3&page=1&search=)  
The challenge file is BMP file named ```output.bmp```, after some tools to inspect as ```exiftool, zsteg, ..``` , there's nothing special at there. Then, i decided to use ```xxd``` to read a file header and i noticed that **```PK```** is ZIP file header.   
Depend on it, i searched from [File signatures](https://www.garykessler.net/library/file_sigs.html) to recover it format.  
Hex Signature of ZIP is : ```50 4B 03 04 14 00 00 00 08 00```.  
Trailer: filename ```50 4B 17 characters 00 00 00```.  
And i noticed that after 2 byte of header is 2 trash byte so i deleted these trash byte by ```cut.py``` python file.  
```python
fi = open(r"/mnt/c/Users/Hoang Quy/Downloads/output.bmp",'rb')
fo = open('output1.bmp','wb')
offset4=fi.read(4)
while (len(offset4)==4):
    fo.write(offset4[:2])
    offset4 = fi.read(4)
fi.close()
fo.close()
```
Finnaly, i deleted bytes before header and after trailer and changed it file entensions to zip and open it.  
![image](https://github.com/user-attachments/assets/78b397b5-2a42-492a-b930-3b4377b345a1)  
![image](https://github.com/user-attachments/assets/aa2d27fa-1181-4bec-ae99-ca7ce535ea1f)  
Then i have this file which have flag and i only need to open it and find flag.  
```linux
user@LAPTOP-TL39B5OL:/mnt/c/Users/Hoang Quy/Downloads$ cat ZnJhbmtlbnN0ZWluLXRlc3QudHh0 | grep 'picoCTF*'
At that age I became acquainted with the celebrated picoCTF{w0rd_d4wg_y0u_f0und_5h3113ys_m4573rp13c3_a23dfbd4}
```

## FLAG: **```picoCTF{w0rd_d4wg_y0u_f0und_5h3113ys_m4573rp13c3_a23dfbd4}```**



