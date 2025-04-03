---
title: Pico Forensic

---

# Pico Forensic
## Easy challenge
### [Canyousee](https://play.picoctf.org/practice?category=4&page=1&search=s)
This challenge provide me a jpg file, the first one is check it with exiftool to get more information and i noticed to it 'Attribution URL' which look like a base64 code format.  
![image](https://github.com/user-attachments/assets/1af58baa-cc50-4c9f-bf72-f25a477a4c0d)  
Luckily after decode it by base64 decoder, i get flag.
![image](https://github.com/user-attachments/assets/3a2fb16a-5503-47ba-b4f1-fd634b1e524b)  
Flag: ```picoCTF{ME74D47A_HIDD3N_6a9f5ac4}```
### [Glory of the Garden](https://play.picoctf.org/practice/challenge/44?assigned=0&category=4&difficulty=1&page=1&search=&solved=0)
This challenge give a JPG file and the hint mentions using hex editor. Therefore, i decided to inspect the file using ```xxd``` command.  
```linux
user@LAPTOP-TL39B5OL:/mnt/c/Users/Hoang Quy/Downloads$ xxd garden.jpg | tail
00230500: d9f9 9f63 4b2b c1e5 daf2 7b59 db49 4ba3  ...cK+....{Y.IK.
00230510: f43e b881 5e30 1060 8030 47d6 bacb 58cb  .>..^0.`.0G...X.
00230520: 1046 07b5 7216 df7e 5ff7 c576 363f ebab  .F..r..~_..v6?..
00230530: b70d 18ce 3ccd 6a7e 6b8d af56 b579 39ca  ....<.j~k..V.y9.
00230540: eeef 53ae 8620 31b8 751f 9514 f7fb cff5  ..S.. 1.u.......
00230550: a2bb bdac 9687 98e4 d3b2 e87f ffd9 4865  ..............He
00230560: 7265 2069 7320 6120 666c 6167 2022 7069  re is a flag "pi
00230570: 636f 4354 467b 6d6f 7265 5f74 6861 6e5f  coCTF{more_than_
00230580: 6d33 3374 735f 7468 655f 3379 3336 3537  m33ts_the_3y3657
00230590: 4261 4232 437d 220a                      BaB2C}".
```
 **```FLAG:picoCTF{more_than_m33ts_the_3y3657BaB2C}```**
### [Scan Surprise](https://play.picoctf.org/practice/challenge/444?assigned=0&category=4&difficulty=1&page=1&search=&solved=0)
After connected to the challenge sever, they gave me a file named ```flag.png``` which is a picture of the QR-code:  
![image](https://github.com/user-attachments/assets/3b5e2cc2-b892-43dd-8f31-f7c86a7aa765)  
So, i used a QR-reader tool name ```zbar-tools``` and it returned me a flag.  
```linux
ctf-player@challenge:~/drop-in$ zbarimg flag.png
QR-Code:picoCTF{p33k_@_b00_a81f0a35}
```
**```FLAG:picoCTF{p33k_@_b00_a81f0a35}```**
### Secret of Polygon
![image](https://github.com/user-attachments/assets/18766586-6dd8-48e6-b1f9-4e22d37597c5)  
The challenge give a pdf file which have a part of flag in there!!  
![image](https://github.com/user-attachments/assets/4773fd61-dd92-4beb-94bd-a0b6510e50a7)  
After check this file in HXD, i noticed that is a PNG file format(PNG, IHDR, IDAT, ..).  
![image](https://github.com/user-attachments/assets/28388d3d-8801-4939-bda6-e2637a0fd942)   

So i convert it into a png file by change it file extension from .pdf --> .png, after i recieved another parr of the flag.  

![image](https://github.com/user-attachments/assets/af92696d-3bb5-42cc-a982-8d98269fed03)  
Flag: ```picoCTF{f1u3n7_1n_pn9_&_pdf_1f991f77}```
### [information](https://play.picoctf.org/practice/challenge/186?assigned=0&category=4&difficulty=1&page=1&search=&solved=0)
This challenge gave me a JPG file named ```cat.jpg```. To start, i decided to inspect the file using ```exiftool``` which is metadata reader tool.  
```linux
user@LAPTOP-TL39B5OL:/mnt/c/Users/Hoang Quy/Downloads$ exiftool cat.jpg
ExifTool Version Number         : 12.76
File Name                       : cat.jpg
Directory                       : .
File Size                       : 878 kB
File Modification Date/Time     : 2024:11:28 04:40:51+00:00
File Access Date/Time           : 2024:11:28 04:42:56+00:00
File Inode Change Date/Time     : 2024:11:28 04:40:51+00:00
File Permissions                : -rwxrwxrwx
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
JFIF Version                    : 1.02
Resolution Unit                 : None
X Resolution                    : 1
Y Resolution                    : 1
Current IPTC Digest             : 7a78f3d9cfb1ce42ab5a3aa30573d617
Copyright Notice                : PicoCTF
Application Record Version      : 4
XMP Toolkit                     : Image::ExifTool 10.80
License                         : cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9
Rights                          : PicoCTF
Image Width                     : 2560
Image Height                    : 1598
Encoding Process                : Baseline DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
Image Size                      : 2560x1598
Megapixels                      : 4.1
```
I noticed that the line named ```License``` looks like a base-64 code, so i decoded it and obtained a flag.  
```linux
user@LAPTOP-TL39B5OL:/mnt/c/Users/Hoang Quy/Downloads$ echo 'cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9' | base64 -d
picoCTF{the_m3tadata_1s_modified}
```
Flag: **```picoCTF{the_m3tadata_1s_modified}```**
## Medium challenge
### [Enhance!]()
```linux
user@LAPTOP-TL39B5OL:/mnt/c/Users/Hoang Quy/Downloads$ strings drawing.flag.svg
<?xml version="1.0" encoding="UTF-8" standalone="no"?>
<!-- Created with Inkscape (http://www.inkscape.org/) -->
<svg
   xmlns:dc="http://purl.org/dc/elements/1.1/"
   xmlns:cc="http://creativecommons.org/ns#"
   xmlns:rdf="http://www.w3.org/1999/02/22-rdf-syntax-ns#"
   xmlns:svg="http://www.w3.org/2000/svg"
   xmlns="http://www.w3.org/2000/svg"
   xmlns:sodipodi="http://sodipodi.sourceforge.net/DTD/sodipodi-0.dtd"
   xmlns:inkscape="http://www.inkscape.org/namespaces/inkscape"
   width="210mm"
   height="297mm"
   viewBox="0 0 210 297"
   version="1.1"
   id="svg8"
   inkscape:version="0.92.5 (2060ec1f9f, 2020-04-08)"
   sodipodi:docname="drawing.svg">
  <defs
     id="defs2" />
  <sodipodi:namedview
     id="base"
     pagecolor="#ffffff"
     bordercolor="#666666"
     borderopacity="1.0"
     inkscape:pageopacity="0.0"
     inkscape:pageshadow="2"
     inkscape:zoom="0.69833333"
     inkscape:cx="400"
     inkscape:cy="538.41159"
     inkscape:document-units="mm"
     inkscape:current-layer="layer1"
     showgrid="false"
     inkscape:window-width="1872"
     inkscape:window-height="1016"
     inkscape:window-x="48"
     inkscape:window-y="27"
     inkscape:window-maximized="1" />
  <metadata
     id="metadata5">
    <rdf:RDF>
      <cc:Work
         rdf:about="">
        <dc:format>image/svg+xml</dc:format>
        <dc:type
           rdf:resource="http://purl.org/dc/dcmitype/StillImage" />
        <dc:title></dc:title>
      </cc:Work>
    </rdf:RDF>
  </metadata>
  <g
     inkscape:label="Layer 1"
     inkscape:groupmode="layer"
     id="layer1">
    <ellipse
       id="path3713"
       cx="106.2122"
       cy="134.47203"
       rx="102.05357"
       ry="99.029755"
       style="stroke-width:0.26458332" />
    <circle
       style="fill:#ffffff;stroke-width:0.26458332"
       id="path3717"
       cx="107.59055"
       cy="132.30211"
       r="3.3341289" />
    <ellipse
       style="fill:#000000;stroke-width:0.26458332"
       id="path3719"
       cx="107.45217"
       cy="132.10078"
       rx="0.027842503"
       ry="0.031820003" />
    <text
       xml:space="preserve"
       style="font-style:normal;font-weight:normal;font-size:0.00352781px;line-height:1.25;font-family:sans-serif;letter-spacing:0px;word-spacing:0px;fill:#ffffff;fill-opacity:1;stroke:none;stroke-width:0.26458332;"
       x="107.43014"
       y="132.08501"
       id="text3723"><tspan
         sodipodi:role="line"
         x="107.43014"
         y="132.08501"
         style="font-size:0.00352781px;line-height:1.25;fill:#ffffff;stroke-width:0.26458332;"
         id="tspan3748">p </tspan><tspan
         sodipodi:role="line"
         x="107.43014"
         y="132.08942"
         style="font-size:0.00352781px;line-height:1.25;fill:#ffffff;stroke-width:0.26458332;"
         id="tspan3754">i </tspan><tspan
         sodipodi:role="line"
         x="107.43014"
         y="132.09383"
         style="font-size:0.00352781px;line-height:1.25;fill:#ffffff;stroke-width:0.26458332;"
         id="tspan3756">c </tspan><tspan
         sodipodi:role="line"
         x="107.43014"
         y="132.09824"
         style="font-size:0.00352781px;line-height:1.25;fill:#ffffff;stroke-width:0.26458332;"
         id="tspan3758">o </tspan><tspan
         sodipodi:role="line"
         x="107.43014"
         y="132.10265"
         style="font-size:0.00352781px;line-height:1.25;fill:#ffffff;stroke-width:0.26458332;"
         id="tspan3760">C </tspan><tspan
         sodipodi:role="line"
         x="107.43014"
         y="132.10706"
         style="font-size:0.00352781px;line-height:1.25;fill:#ffffff;stroke-width:0.26458332;"
         id="tspan3762">T </tspan><tspan
         sodipodi:role="line"
         x="107.43014"
         y="132.11147"
         style="font-size:0.00352781px;line-height:1.25;fill:#ffffff;stroke-width:0.26458332;"
         id="tspan3764">F { 3 n h 4 n </tspan><tspan
         sodipodi:role="line"
         x="107.43014"
         y="132.11588"
         style="font-size:0.00352781px;line-height:1.25;fill:#ffffff;stroke-width:0.26458332;"
         id="tspan3752">c 3 d _ 2 4 3 7 4 6 7 5 }</tspan></text>
  </g>
</svg>
```
You can see at the few last row is some part of flag ``` { 3 n h 4 n``` and ```c 3 d _ 2 4 3 7 4 6 7 5 }```, matched it and obtained a flag. 
FLAG: ***```picoCTF{3nh4nc3d_24374675}```***
### [File types](https://play.picoctf.org/practice/challenge/268?category=4&difficulty=2&page=1&search=&solved=1)
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
FLAG: ***```picoCTF{f1len@m3_m@n1pul@t10n_f0r_0b2cur17y_3c79c5ba}```***
### [FindAndOpen](https://play.picoctf.org/practice/challenge/348?assigned=0&category=4&difficulty=2&page=1&search=&solved=0)  
This challenge contains a ```flag.zip``` and ```dump.pcap```, my missiom is checking ```dump.pcap``` file to get a key to open flag file.  
I opend dump file using [Wireshark](https://www.wireshark.org/), after reviewing the protocols i noticed that the hint: "The secret is on Ethernet".So, i focused on Ethernet II inforamtion.  
Afterthat , i discovered that one of the entries contains the data which looks like base64 code, then i encrypted it using [Cyperchef](https://gchq.github.io/CyberChef/#recipe=From_Hex('None')From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=NTY0NzY4NzA2Mzc5NDI3MDYzNzk0MjMwNjE0NzU1Njc2MzMyNTY2YTYzNmQ1NjMwNGY2OTQyNzc2MTU3NGU3NjUxMzE1MjQ3NjUzMTQ5N2E0ZTQ1NTI0YTU0NmI2NDY2NTQ0NTM5NGM1YTQ2MzgzZA) and obtain a password for the flag.  
![image](https://github.com/user-attachments/assets/8afa27e9-5b5c-4734-94d5-a0901f99d581)  
![image](https://github.com/user-attachments/assets/f0a077ad-ab44-4d16-871f-7ea1fd7de457)  
Finally, i used this decoded text as the key for the flag file and i recieve a flag.  
Flag: **```picoCTF{R34DING_LOKd_fil56_succ3ss_c2e6d949}```**
### [Lookey here](https://play.picoctf.org/practice/challenge/279?category=4&page=2&search=)
This challenge just need you open and search for flag in txt file.
![image](https://github.com/user-attachments/assets/d8e7b383-3835-47d3-b927-0194aefff696)  
FLAG: **```picoCTF{gr3p_15_@w3s0m3_4c479940}```**
### [Packets Primer]()
This challenge gave me pcap file and just need open it and obtained flag in the info of packets.
![image](https://github.com/user-attachments/assets/04a9f869-9525-469d-b262-bef7de1d1b2c)
FLAG: **```picoCTF{p4ck37_5h4rk_b9d53765}```**
### [PcapPoisoning](https://play.picoctf.org/practice/challenge/362?category=4&difficulty=2&page=1&search=&solved=1)
The challenge gave me a pcap file. The first i opened it using ```Wireshark``` and obtained a flag in the info of TCP packets.  
![image](https://github.com/user-attachments/assets/b07afe31-27cf-48ac-bd88-840e580f94dc)  
***```picoCTF{P64P_4N4L7S1S_SU55355FUL_f621fa37}```***
### [Redaction gone wrong](https://play.picoctf.org/practice/challenge/290?category=4&difficulty=2&page=1&search=&solved=1)
After downloading the PDF file, I discovered that some words were highlighted in MS Word. By opening the file in MS Word and changing the color of those words, I was able to reveal a flag.
![image](https://github.com/user-attachments/assets/380c17e4-b1bd-4337-87e5-7824de5e80b3)  
FLAG: ***```picoCTF{C4n_Y0u_S33_m3_fully} ```***
### [So Meta](https://play.picoctf.org/practice/challenge/19?assigned=0&category=4&difficulty=2&page=4&search=&solved=0)
This challenge require me to read a PNG file metadata, so i inspect the file using ```exiftool``` and obtained a flag.  
```linux
user@LAPTOP-TL39B5OL:/mnt/c/Users/Hoang Quy/Downloads$ exiftool pico_img.png
ExifTool Version Number         : 12.76
File Name                       : pico_img.png
Directory                       : .
File Size                       : 109 kB
File Modification Date/Time     : 2024:11:28 05:57:38+00:00
File Access Date/Time           : 2024:11:28 05:58:26+00:00
File Inode Change Date/Time     : 2024:11:28 05:57:38+00:00
File Permissions                : -rwxrwxrwx
File Type                       : PNG
File Type Extension             : png
MIME Type                       : image/png
Image Width                     : 600
Image Height                    : 600
Bit Depth                       : 8
Color Type                      : RGB
Compression                     : Deflate/Inflate
Filter                          : Adaptive
Interlace                       : Noninterlaced
Software                        : Adobe ImageReady
XMP Toolkit                     : Adobe XMP Core 5.3-c011 66.145661, 2012/02/06-14:56:27
Creator Tool                    : Adobe Photoshop CS6 (Windows)
Instance ID                     : xmp.iid:A5566E73B2B811E8BC7F9A4303DF1F9B
Document ID                     : xmp.did:A5566E74B2B811E8BC7F9A4303DF1F9B
Derived From Instance ID        : xmp.iid:A5566E71B2B811E8BC7F9A4303DF1F9B
Derived From Document ID        : xmp.did:A5566E72B2B811E8BC7F9A4303DF1F9B
Warning                         : [minor] Text/EXIF chunk(s) found after PNG IDAT (may be ignored by some readers)
Artist                          : picoCTF{s0_m3ta_eb36bf44}
Image Size                      : 600x600
Megapixels                      : 0.360
```
FLAG: **```picoCTF{s0_m3ta_eb36bf44}```**
### [St3g0](https://play.picoctf.org/practice/challenge/305?category=4&difficulty=2&page=1&search=st)   
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
### [WhitePages](https://play.picoctf.org/practice/challenge/51?category=4&difficulty=2&page=3&solved=1)
Thử thách đưa ra 1 file txt chỉ bao gồm các kí tự trằng nên tôi đã thử giải nó bằng ngôn ngữ ```Whitespace``` nhưng không thu được gì.  
![image](https://github.com/user-attachments/assets/b60b17f5-b5c9-474b-b952-e8908d160a97)  
Nên tôi đã thử mở nó bằng ```Subline text``` và nhận ra nó bao gồm cả ```khoảng trắng``` và ```khoảng trắng rộng```.  
![image](https://github.com/user-attachments/assets/8fc76911-834c-455d-96e7-4cb446976eb1)   
Nên tôi đã thử chuyển nó thành mã nhị phân bằng python và sau đó tôi thu được 1 dãy nhị phân:  
```python
text='                                                                                                                 >
firstType = ' '
secondType =  ' '
binaryString = ''

for char in text: #Foreach char
        if char == firstType: #Check if it is the first type
                binaryString += '0' #Mark it as 0
        else:
                binaryString += '1' #Mark it as 1

print(binaryString)
```
```linux
user@LAPTOP-TL39B5OL:/mnt/c/Users/Hoang Quy/Downloads/CTF$ python3 decoder.py
0000101000001001000010010111000001101001011000110110111101000011010101000100011000001010000010100000100100001001010100110100010101000101001000000101000001010101010000100100110001001001010000110010000001010010010001010100001101001111010100100100010001010011001000000010011000100000010000100100000101000011010010110100011101010010010011110101010101001110010001000010000001010010010001010101000001001111010100100101010000001010000010010000100100110101001100000011000000110000001000000100011001101111011100100110001001100101011100110010000001000001011101100110010100101100001000000101000001101001011101000111010001110011011000100111010101110010011001110110100000101100001000000101000001000001001000000011000100110101001100100011000100110011000010100000100100001001011100000110100101100011011011110100001101010100010001100111101101101110011011110111010001011111011000010110110001101100010111110111001101110000011000010110001101100101011100110101111101100001011100100110010101011111011000110111001001100101011000010111010001100101011001000101111101100101011100010111010101100001011011000101111101100011001101010011010001100110001100100011011101100011011001000011000000110101011000110011001000110001001110000011100101100110001110000011000100110100001101110110001101100011001101100110011000110101011001000110010101100010001100100110010100110101001101100111110100001010000010010000100
```
Sau khi dịch đoạn nhị phân nó ra thì tôi thu được một đoạn kí tự gồm cả flag.  
![image](https://github.com/user-attachments/assets/eee68e85-9aff-4d89-aef9-b50c0813c1b4)  
FLAG:**```picoCTF{not_all_spaces_are_created_equal_c54f27cd05c2189f8147cc6f5deb2e56}```**
### Corrupt
Xin chào mn hôm nay chúng ta cùng nhau giải bài c0rrupt trên picoCTF nhé!!
![image](https://github.com/user-attachments/assets/004d9f46-4fa9-4b83-8f21-1d7cab4776c4)
đầu tiên chúng ta cùng nhau tải file về máy thì chúng ta nhận được 1 file không rõ tên mystery 
![image](https://github.com/user-attachments/assets/d4be3765-b058-41ed-80a4-a2483eeda2fa)
sau khi kiểm tra bằng bvi thì mình nhận ra sRGB, gAMA, pHYs khá giống định dạng của 1 file png do đó mình đã lên wiki và tìm hiểu về format của PNG
![image](https://github.com/user-attachments/assets/6246f420-9a0e-42fa-8c38-8d01df8d9b32)
sau khi tham khảo về format thì mình đã chỉnh sửa file bị hỏng bằng HxD thì ta được như này
![image](https://github.com/user-attachments/assets/49026e80-d5bb-440b-ae4d-2d67b85adb93)
sau đó thì chúng ta chuyển nó về định dạng png thôi và tada chúng ta có được 1 hình ảnh chứa flag
![image](https://github.com/user-attachments/assets/9935834f-47f5-4a0b-b922-0e47b15c1eb6)
![image](https://github.com/user-attachments/assets/5c4b64c6-e148-423b-bd14-324fccdbb042)
FLAG: picoCTF{c0rrupt10n_1847995}
### [hideme](https://play.picoctf.org/practice/challenge/350?category=4&difficulty=2&page=1&search=)
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

### tunn3l v1s10n
Chào các bạn hôm nay cùng mình giải bài trên picoCTF nhé =)) . Bài hôm nay là tunn3l v1s10n.
![image](https://github.com/user-attachments/assets/63d1d8b0-20c2-4b2e-88f8-a9562877725a)
Sau khi tải file thì mình nhận được 1 file bị lỗi cùng tên là tunn3l v1s10n và mình bắt đầu kiểm tra file đó thì nhận ra nó khá giống BMP format
![image](https://github.com/user-attachments/assets/ea8722a5-1cfe-4956-900d-5f497ce3418a)
sau khi tra về BMP format thì mình đã chỉnh sửa file thành như sau 
![image](https://github.com/user-attachments/assets/06d3be50-0cad-4ace-82ed-4ea235d8f333)
sau khi chỉnh sửa lại thành định dạng BMP thì mình được 1 ảnh như sau 
![image](https://github.com/user-attachments/assets/05780ba1-6728-475f-acd2-b7162374bd23)
cảm giác ảnh chưa hoàn chỉnh nên mình cố điều chỉnh lại kích thước của ảnh

![image](https://github.com/user-attachments/assets/47ffac39-7d57-43ed-aa8d-8ff3c22252f9)


flag : picoCTF{qu1t3_a_v13W_2020}

## Hard challenge
### [Invisible WORDs](https://play.picoctf.org/practice/challenge/354?category=4&difficulty=3&page=1&search=)  
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
**```picoCTF{w0rd_d4wg_y0u_f0und_5h3113ys_m4573rp13c3_a23dfbd4}```**
