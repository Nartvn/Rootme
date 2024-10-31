***Crypt-art***

![image](https://github.com/user-attachments/assets/c652195b-da07-4ec3-9e2f-95e612a14e45)

Bài này là 1 trong những bài tôi đánh gia cao về kiến thức..
Tải file về ta được 1 file như sau:

![image](https://github.com/user-attachments/assets/b4440c2e-4212-4b74-87e0-65edcfabbccd)

Làm vài thao tác kiểm tra cơ bản thì ta được thông tin như sau:

```linux
nart@LAPTOP-4KTO77CJ:~$ strings ch8.ppm
70 50
  Hi! Welcome to
esoteric programming!
The encrypted pass is:
EPCQFBXKWURQCTXOIPMNV
 Bienvenue a la program
mation esoterique!
Le pass encrypte est
EPCQFBXKWURQCTXOIPMNV
```
Sau khi research những dữ liêu ấy thì tôi ra được đây là ngôn ngữ [piet](https://esolangs.org/wiki/Piet)

![image](https://github.com/user-attachments/assets/7cb9ffc7-030a-40bb-a370-dbe849456fd0)

bây giờ tôi sẽ đi decode để xem được những gì?

![image](https://github.com/user-attachments/assets/fa6a082e-1d0d-4932-b419-3e2463afede5)

Đây không phải là flag vì tôi đã thử vì thế tôi nghĩ đây là mật mã của 1 dạng nào đó. 
Sau một khoảng thì tôi nghĩ nó là dang [Mật mã Vigenère](https://vi.wikipedia.org/wiki/M%E1%BA%ADt_m%C3%A3_Vigen%C3%A8re), với công cụ decode tôi tìm được là [đây](https://www.dcode.fr/vigenere-cipher)

![image](https://github.com/user-attachments/assets/930044c4-85f2-4f91-91cb-fb73eb3752e0)

flag : ```ARTLOVERSWILLNEVERDIE```
