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



