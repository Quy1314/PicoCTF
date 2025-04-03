---
title: PICOCTF WEB

---

# PICOCTF WEB
## Easy
### Insp3ct0r
![image](https://hackmd.io/_uploads/SJDIbocpJl.png)
Đề bài hints là dùng inspector nên mình sử dụng dev tool trên các browser bằng cách ấn F12, trong đó thì mình tìm thấy các part của flag trong các file: HTML, CSS và JS.
```linux=
part1: picoCTF{tru3_d3
part2: t3ct1ve_0r_ju5t
part3: _lucky?832b0699}
```
```FLAG: picoCTF{tru3_d3t3ct1ve_0r_ju5t_lucky?832b0699}```
### Scavenger Hunt
![image](https://hackmd.io/_uploads/H1xmQo9Tkx.png)
Mình tiếp tục inspect trang web bằng F12, thì mình phát hiện ra 2 part và 1 hints về robots.txt
```linux=
part1: picoCTF{t
part2: h4ts_4_l0
```
vì có hints về file robots.txt nên mình chèn nó vào URL
![image](https://hackmd.io/_uploads/Hkb6XjcT1x.png)
```linux=
part3: t_0f_pl4c
```
dựa vào hint về apache sever, sau khi search thì mình đoán nó sẽ dùng ```.htaccess```là 1 tệp cấu hình của apache.
![image](https://hackmd.io/_uploads/HJ5IHsq6yg.png)
```linux
part4: 3s_2_lO0k
```
hint tiếp theo là về Mac và Store, sau khi research thì mình phát hiện có 1 file lưu thông tin về các attribute trên MAC là ```.DS_Store```
![image](https://hackmd.io/_uploads/SkWmLsc61l.png)
thế là mình đã tìm đủ các part của flag, bây giờ chỉ việc ghép nó lại thôi.
```FLAG: picoCTF{th4ts_4_l0t_0f_pl4c3s_2_lO0k_7a46d25d}```

### Webdecode
![image](https://hackmd.io/_uploads/HkBKUj5a1l.png)
Sau khi bấm qua các phần của trang web thì mình tìm thấy 1 trang bảo mình nên inspect ở đây.
![image](https://hackmd.io/_uploads/B15ywscpyl.png)

Mình inspect web này và mình thấy 1 đoạn chữ khá giống mã code của base64 nên mình thử decode nó ra.
```latex=
cGljb0NURnt3ZWJfc3VjYzNzc2Z1bGx5X2QzYzBkZWRfMjgzZTYyZmV9
```
sau khi dùng cyberchef dịch nó bằng base64 thì mình có flag.
```FLAG: picoCTF{web_succ3ssfully_d3c0ded_283e62fe}```
### Cookie Monster Secret Recipe
![image](https://hackmd.io/_uploads/HkgoDjcp1e.png)
* Hints: Cookies
![image](https://hackmd.io/_uploads/rk_RDscT1x.png)
Đây là một trang login nên mình thử đăng nhập thông tin ngẫu nhiên vào.
![image](https://hackmd.io/_uploads/HyNzOs5pkg.png)
Tới đây thì có hints là kiểm tra cookies của trang web nên mình dùng burpsuite để đọc cookie có trang web cho tiện.
![image](https://hackmd.io/_uploads/H1t9di5Tye.png)
sau khi select cookie thì mình đã có flag lun rồi nhé.
```FLAG: picoCTF{c00k1e_m0nster_l0ves_c00kies_AC8FCD75}```

### Unminify
![image](https://hackmd.io/_uploads/SkQrFs5TJx.png)
![image](https://hackmd.io/_uploads/H16fto5pJx.png)
Vì trang web đã bảo là đã gửi flag rồi nên mình nghĩ nó có thể trong HTTP Respone packet.
![image](https://hackmd.io/_uploads/SkKFts9pJl.png)
đúng như dự đoán mình đã tìm thấy flag trong file HTTP Respone.
```FLAG: picoCTF{pr3tty_c0d3_dbe259ce}```
### IntroToBurp
![image](https://hackmd.io/_uploads/BJzxjo9a1e.png)
Bài này mình sẽ dụng burpsuite nhé.
![image](https://hackmd.io/_uploads/BJta9s5Tkx.png)
Ở trang web này thì là 1 trang đăng kí nên mình nhập ngẫu nhiên thì sau đó được chuyển sang trang xác nhận otp.
![image](https://hackmd.io/_uploads/H1tyji9T1e.png)
Mình cũng thử nhập như vậy nhưng lại bỏ đi phần ```otp``` trong request thì mình đã có flag.
Mình nghĩ là do sever sẽ mặc định sẽ cho phép truy cập kể cả khi không có otp.
![image](https://hackmd.io/_uploads/rytm3oq6Jl.png)
```FLAG: picoCTF{#0TP_Bypvss_SuCc3$S_e1eb16ed}```
### Inspect HTML
![image](https://hackmd.io/_uploads/SJ3h6jq6yg.png)
Bài này chỉ cần inspect ra là thấy flag rồi nhé.
![image](https://hackmd.io/_uploads/SJbApo96kx.png)
```FLAG: picoCTF{1n5p3t0r_0f_h7ml_8113f7e2}```
### Bookmarklet
Đề bài hướng chúng ta đến việc dùng đoạn mã cho sẵn để lấy flag. Sau khi chạy thì chúng ta thu được flag.
![image](https://hackmd.io/_uploads/SkVSJhqp1g.png)
```FLAG: picoCTF{p@g3_turn3r_1d1ba7e0}```
### Cookies
![image](https://hackmd.io/_uploads/rJ7aB29Tyx.png)
![image](https://hackmd.io/_uploads/Hkcpt29Tyg.png)
Theo mình nghĩ thì trang web đang yêu cầu mình đoán xem cookie nào chứa thông tin về flag vì khi mình nhập snickerdoodle thì ```Cookie: name=0```. Do đó mình tăng thử lên 1 thì phát hiện trang web có thay đổi.
![image](https://hackmd.io/_uploads/Sycwc3qpyl.png)
Do đó mình tiếp tục tăng cho đến khi name=18 thì nhận được flag.
```FLAG: picoCTF{3v3ry1_l0v3s_c00k135_a1f5bdb7}```
### where are the robots
![image](https://hackmd.io/_uploads/BkZqsh5pJe.png)
![image](https://hackmd.io/_uploads/HJc9j25Tkg.png)
Sau khi đọc dòng đầu tiên thì mình liên tưởng ngay đến file robots.txt. Nên mình đã gán vào url của trang web thì mình thấy có 1 trang html bị disalowed khiến cho khi mình truy cập trang web không thấy được.
```htmlmixed=
Disallow: /1bb4c.html
```
Mình thử gán nó vào url thì nhận được flag.
![image](https://hackmd.io/_uploads/B1Sz33qpJg.png)
```FLAG: picoCTF{ca1cu1at1ng_Mach1n3s_1bb4c}```
### logon
![image](https://hackmd.io/_uploads/SJZmA2qakg.png)
![image](https://hackmd.io/_uploads/B1vo6h561l.png)
Mờ đầu với 1 trang login, sau khi bấm đăng nhập thì nhận được là không có flag do đó mình thử kiểm tra cookie thì thấy có thể thay đổi quyền admin từ ```false``` thành ```true``` và nhận được flag.
![image](https://hackmd.io/_uploads/BJ7JA2cTJl.png)
![image](https://hackmd.io/_uploads/HyygA3qpyl.png)
Sau khi sửa thì refresh trang web và nhận flag.
![image](https://hackmd.io/_uploads/rJ4MCn96yg.png)
``` FLAG: picoCTF{th3_c0nsp1r4cy_l1v3s_d1c24fef}```
### Includes
![image](https://hackmd.io/_uploads/By2gfxsakx.png)
Trong bài này thì flag giấu trong 2 file js và css sau khi inspect nó bằng dev tool F12.
```FLAG:picoCTF{1nclu51v17y_1of2_f7w_2of2_df589022}```

### Local Authority
Bài cho 1 trang login web sau khi đăng nhập thử và inspect thì mình thấy có 1 file tên là ```secure.js``` chứa thông tin của tài khoản admin.
![image](https://hackmd.io/_uploads/ByqCfeja1g.png)
sau khi đăng nhập thì mình nhận được flag.
```FLAG:picoCTF{j5_15_7r4n5p4r3n7_b0c2c9cb}```

### dont-use-client-side
![image](https://hackmd.io/_uploads/HyDdNxjpJx.png)
Sau khi mình inspect thì thấy flag được chia ra thành nhiều phần
![image](https://hackmd.io/_uploads/Byuz4esa1e.png)
```FLAG: picoCTF{no_clients_plz_7723ce}```

### head-dump
![image](https://hackmd.io/_uploads/ryiIzZipye.png)
![image](https://hackmd.io/_uploads/B1XPGbs61l.png)
Sau khi được dẫn tới trang picoCTF news thì mình thử bấm vào các hastag thì chỉ có ```#API Documentation``` có thể chuyển hướng được
![image](https://hackmd.io/_uploads/H1ccfbiaye.png)
dựa vào hint là head-dump nên mình excute file trong phần headdump và tải file về.
Trong file headdump mình search tìm flag bằng Ctrl+F.
![image](https://hackmd.io/_uploads/rJUJXWj6yx.png)
```FLAG: picoCTF{Pat!3nt_15_Th3_K3y_46022a05}```.
## Medium
### picobrowser
![image](https://hackmd.io/_uploads/BksrIZi6Jx.png)
![image](https://hackmd.io/_uploads/SymIUZoaye.png)
Chúng ta không thể nhận flag vì không sử dụng pico browser. Mình chú ý đến dòng:
```linux=
Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/134.0.0.0 Safari/537.36 
```
dòng này cho ta biết ta đang dùng trình duyệt của chrome, nên mình suy nghĩ có thể thay nó thành ```picobrowser``` trong phần request bằng burpsuite.
![image](https://hackmd.io/_uploads/rJnQvWj6Je.png)

![image](https://hackmd.io/_uploads/Bk-hw-s61e.png)
Mình thành công thu được flag.
```FLAG: picoCTF{p1c0_s3cr3t_ag3nt_51414fa7}```
Sau khi research thì mình biết dev tool của trình duyệt có tính năng ```Network conditions``` có thể trực tiếp thay đổi ```user agent``` của browser.
![image](https://hackmd.io/_uploads/rJYQ_Wipkx.png)
![image](https://hackmd.io/_uploads/HJ35ubsa1g.png)
Chú ý đây là dùng default browser. Bây giờ mình sẽ thay nó thành picobrowser và refresh lại.
![image](https://hackmd.io/_uploads/HyvkYbsTJl.png)
Mình cũng nhận được flag tương tự.
## Sqlilite
![image](https://hackmd.io/_uploads/ByQ2iZo6Jl.png)
Theo như gợi ý đây có thể là dạng payload bằng cách sử dụng sqli. Nên mình đã thử nhập username= admin'-- để website bỏ qua phần kiểm tra mật khẩu nếu username đúng
![image](https://hackmd.io/_uploads/SJCGhWop1x.png)
Như mình đoán! Mình đã log in thành công và nhận được thông báo đã có flag nhưng lại không thấy đâu nên mình thử inspect để xem source code.
![image](https://hackmd.io/_uploads/HkiDhbiaye.png)
Mình đã tìm thấy flag được giấu trong source code.
```FLAG: picoCTF{L00k5_l1k3_y0u_solv3d_it_ec8a64c7}```
### More SQLi
![image](https://hackmd.io/_uploads/ByPFdsi6yx.png)
Dựa theo tên challenge mình đoán đây có thể là một bài sử dụng SQL injection.
![image](https://hackmd.io/_uploads/H1dBRsipyg.png)
 ta có 1 trang login mình thử chèn thử ``` ' or 1=1--``` để đăng nhập.
![image](https://hackmd.io/_uploads/Hk_t0os6yx.png)
theo truy vấn thì có vẻ là họ sẽ xác minh password trước nên mình sẽ đổi câu lệnh chèn xuống password nhé.
![image](https://hackmd.io/_uploads/r12Q1hjTkg.png)
Mình đã đăng nhập thành công, theo hình thì mình có 3 cột của 1 table. Trước tiên mình sẽ kiểm tra thử xem db này là db nào.
![image](https://hackmd.io/_uploads/Skollno6Jx.png)
Theo kết quả thì đây là một db sqlite. Tiếp theo mình sẽ thử kiểm tra thông tin của các bảng bằng sqlite_master ( bảng chứa tất cả thông tin về các bảng khác ).
![image](https://hackmd.io/_uploads/BkCiN2op1l.png)
![image](https://hackmd.io/_uploads/H19xr3opke.png)
theo đó thì flag nằm trong bảng more_table.
``` FLAG: picoCTF{G3tting_5QL_1nJ3c7I0N_l1k3_y0u_sh0ulD_c8b7cc2a}```

### Secrets
![image](https://hackmd.io/_uploads/HJ2jVx2aJg.png)
![image](https://hackmd.io/_uploads/rkwlHxhp1g.png)
Sau khi truy cập trang web và inspect thử bằng dev tool thì mình nhận thấy trong file html có đường dẫn lạ tên secret. 
![image](https://hackmd.io/_uploads/rkuVrg2p1g.png)
Có vẻ như mình đã đi đúng hướng, trong file secret cũng có 1 đường dẫn như vậy nên mình truy cập vào nó.
![image](https://hackmd.io/_uploads/BkYjBg3Tkg.png)
Cứ tưởng là 1 trang login bình thường nhưng khi inspect thì mình lại thấy 1 đường dẫn có tên là superhidden. Sau khi truy cập thì mình nhận được flag được ẩn đi.
![image](https://hackmd.io/_uploads/ByNBIen61e.png)
```Flag: picoCTF{succ3ss_@h3n1c@10n_790d2615}```