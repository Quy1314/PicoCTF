# [WhitePages](https://play.picoctf.org/practice/challenge/51?category=4&difficulty=2&page=3&solved=1)
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
## FLAG:**```picoCTF{not_all_spaces_are_created_equal_c54f27cd05c2189f8147cc6f5deb2e56}```**