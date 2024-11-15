***APNG - Just A PNG***

![image](https://github.com/user-attachments/assets/58733cfd-e6ac-4e69-8ef2-464595f235ff)

Tải file về tôi được 1 file .apng, tôi liền research xem nó là gì và thấy được nó là 1 chuỗi png.
Bây giờ tôi dùng công cụ để tách nó ra như sau.

```linux
nart@LAPTOP-4KTO77CJ:~$ apngdis ch21.apng

APNG Disassembler 2.9

Reading 'ch21.apng'...
extracting frame 1 of 13
extracting frame 2 of 13
extracting frame 3 of 13
extracting frame 4 of 13
extracting frame 5 of 13
extracting frame 6 of 13
extracting frame 7 of 13
extracting frame 8 of 13
extracting frame 9 of 13
extracting frame 10 of 13
extracting frame 11 of 13
extracting frame 12 of 13
extracting frame 13 of 13
all done
```
Chúng ta sẽ được 1 đống file như sau:

![image](https://github.com/user-attachments/assets/99e09fa8-66b4-42b8-846a-9a8471120de2)

Khi thai khác các file chúng ta nhận ra các file apngframexx.txt đều có điểm chung khác nhau số ở giữa và nó chính là decode của ascii.
Tôi dùng wed decode nó theo thứ tự và ra được key.

![image](https://github.com/user-attachments/assets/9eedc98a-72ef-4a7f-a6bc-227cc97cff49)

flag : ```P3PoFRoG```

