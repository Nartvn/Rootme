***PDF - Embedded***

![image](https://github.com/user-attachments/assets/3d20b1ea-dd13-448f-9d7b-8996c65aa6c3)

Khi tải về tôi được 1 file nén giải nén ra tôi được 1 file pdf. 
Làm qua 1 số nghiệp vụ cơ bản tôi không phát hiện được file nào... cho tới khi tôi binwalk nó.

```linux
nart@LAPTOP-4KTO77CJ:~$ binwalk epreuve_BAC_2004.pdf

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PDF document, version: "1.3"
73            0x49            Zlib compressed data, default compression
261           0x105           Zlib compressed data, default compression
451           0x1C3           Zlib compressed data, default compression
641           0x281           Zlib compressed data, default compression
831           0x33F           Zlib compressed data, default compression
1021          0x3FD           Zlib compressed data, default compression
1211          0x4BB           Zlib compressed data, default compression
1401          0x579           Zlib compressed data, default compression
1591          0x637           Zlib compressed data, default compression
1781          0x6F5           Zlib compressed data, default compression
1971          0x7B3           Zlib compressed data, default compression
2161          0x871           Zlib compressed data, default compression
5021          0x139D          Zlib compressed data, default compression
260496        0x3F990         Zlib compressed data, default compression
540256        0x83E60         Zlib compressed data, default compression
683550        0xA6E1E         Zlib compressed data, default compression
899938        0xDBB62         Zlib compressed data, default compression
1095225       0x10B639        Zlib compressed data, default compression
1205948       0x1266BC        Zlib compressed data, default compression
1334697       0x145DA9        Zlib compressed data, default compression
1528474       0x17529A        Zlib compressed data, default compression
1651840       0x193480        Zlib compressed data, default compression
1923915       0x1D5B4B        Zlib compressed data, default compression
2167502       0x2112CE        Zlib compressed data, default compression
2306578       0x233212        Zlib compressed data, default compression
```

Thêm 1 vài thao tác để kiểm tra ra file nên chọn để check

```linux
nart@LAPTOP-4KTO77CJ:~/_epreuve_BAC_2004.pdf.extracted$ du -sh *
4.0K    105
2.3M    105.zlib
25M     10B639
1.3M    10B639.zlib
25M     1266BC
1.2M    1266BC.zlib
25M     139D
2.3M    139D.zlib
25M     145DA9
1.1M    145DA9.zlib
25M     17529A
840K    17529A.zlib
25M     193480
720K    193480.zlib
4.0K    1C3
2.3M    1C3.zlib
25M     1D5B4B
456K    1D5B4B.zlib
25M     2112CE
216K    2112CE.zlib
108K    233212
80K     233212.zlib
4.0K    281
2.3M    281.zlib
4.0K    33F
2.3M    33F.zlib
25M     3F990
2.1M    3F990.zlib
4.0K    3FD
2.3M    3FD.zlib
4.0K    49
2.3M    49.zlib
4.0K    4BB
2.3M    4BB.zlib
4.0K    579
2.3M    579.zlib
4.0K    637
2.3M    637.zlib
4.0K    6F5
2.3M    6F5.zlib
4.0K    7B3
2.3M    7B3.zlib
25M     83E60
1.8M    83E60.zlib
4.0K    871
2.3M    871.zlib
25M     A6E1E
1.7M    A6E1E.zlib
25M     DBB62
1.5M    DBB62.zlib
```
qua bước kiểm tra tay tôi thấy file ```233212``` có vấn đề.

```linux
nart@LAPTOP-4KTO77CJ:~/_epreuve_BAC_2004.pdf.extracted$ xxd 233212 | head
00000000: 2f39 6a2f 3441 4151 536b 5a4a 5267 4142  /9j/4AAQSkZJRgAB
00000010: 4151 4541 5941 4267 4141 442f 2f67 4138  AQEAYABgAAD//gA8
00000020: 5131 4a46 5156 5250 556a 6f67 5a32 5174  Q1JFQVRPUjogZ2Qt
00000030: 616e 426c 5a79 4232 4d53 3477 4943 6831  anBlZyB2MS4wICh1
00000040: 6332 6c75 5a79 424a 536b 6367 0a53 6c42  c2luZyBJSkcg.SlB
00000050: 4652 7942 324e 6a49 704c 4342 7864 5746  FRyB2NjIpLCBxdWF
00000060: 7361 5852 3549 4430 674f 5455 4b41 502f  saXR5ID0gOTUKAP/
00000070: 6241 454d 4141 6745 4241 6745 4241 6749  bAEMAAgEBAgEBAgI
00000080: 4341 6749 4341 6749 4442 514d 4441 774d  CAgICAgIDBQMDAwM
00000090: 4442 6751 4541 7755 480a 4267 6348 4277  DBgQEAwUH.BgcHBw
```
Chúng ta decode base64 file ```233212``` được file JPEG

```linux
nart@LAPTOP-4KTO77CJ:~/_epreuve_BAC_2004.pdf.extracted$ base64 -d 233212 > f01
nart@LAPTOP-4KTO77CJ:~/_epreuve_BAC_2004.pdf.extracted$ file f01
f01: JPEG image data, JFIF standard 1.01, resolution (DPI), density 96x96, segment length 16, comment: "CREATOR: gd-jpeg v1.0 (using IJG JPEG v62), quality = 95", baseline, precision 8, 500x417, components 3
```

Đổi đuổi mở file và mở lên tôi dược flag

![image](https://github.com/user-attachments/assets/51061152-9b31-4c81-9069-4aa08bbc0f49)

flag : ```Hidden_embedded_Fil3```
