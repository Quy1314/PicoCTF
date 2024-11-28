# [Scan Surprise](https://play.picoctf.org/practice/challenge/444?assigned=0&category=4&difficulty=1&page=1&search=&solved=0)
After connected to the challenge sever, they gave me a file named ```flag.png``` which is a picture of the QR-code:  
![image](https://github.com/user-attachments/assets/3b5e2cc2-b892-43dd-8f31-f7c86a7aa765)  
So, i used a QR-reader tool name ```zbar-tools``` and it returned me a flag.  
```linux
ctf-player@challenge:~/drop-in$ zbarimg flag.png
QR-Code:picoCTF{p33k_@_b00_a81f0a35}
```
## FLag: **```picoCTF{p33k_@_b00_a81f0a35}```**
