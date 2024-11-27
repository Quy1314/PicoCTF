# [FindAndOpen](https://play.picoctf.org/practice/challenge/348?assigned=0&category=4&difficulty=2&page=1&search=&solved=0)  
This challenge contains a ```flag.zip``` and ```dump.pcap```, my missiom is checking ```dump.pcap``` file to get a key to open flag file.  
I opend dump file using [Wireshark](https://www.wireshark.org/), after reviewing the protocols i noticed that the hint: "The secret is on Ethernet".So, i focused on Ethernet II inforamtion.  
Afterthat , i discovered that one of the entries contains the data which looks like base64 code, then i encrypted it using [Cyperchef](https://gchq.github.io/CyberChef/#recipe=From_Hex('None')From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=NTY0NzY4NzA2Mzc5NDI3MDYzNzk0MjMwNjE0NzU1Njc2MzMyNTY2YTYzNmQ1NjMwNGY2OTQyNzc2MTU3NGU3NjUxMzE1MjQ3NjUzMTQ5N2E0ZTQ1NTI0YTU0NmI2NDY2NTQ0NTM5NGM1YTQ2MzgzZA) and obtain a password for the flag.  
![image](https://github.com/user-attachments/assets/8afa27e9-5b5c-4734-94d5-a0901f99d581)  
![image](https://github.com/user-attachments/assets/f0a077ad-ab44-4d16-871f-7ea1fd7de457)  
Finally, i used this decoded text as the key for the flag file and i recieve a flag.  
## Flag: **```picoCTF{R34DING_LOKd_fil56_succ3ss_c2e6d949}```**
