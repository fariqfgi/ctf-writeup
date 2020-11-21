# Odading Mang Oleh

## Deskripsi
Odading mang oleh emm rasanya seperti anda menjadi ironman, belilah odading mang oleh di dieu karna lamun teu ngadahar odading mang oleh maneh teu gaul jeung aing, lain balad aing goblog, ikan hiu makan eu tomat, goblog mun teu kadieu, odading mang oleh rasanya anjing banget.

File: [odading.png](odading.png)

## Hint
kunci utama cari password zip untuk memudahkan anda. **no brute force**

## Proof of Concept
Karena hint menyatakan harus menemukan kunci terlebih dahulu, maka langkah pertama cek string pada file **odading.png**
```
$ strings odading.png 
```
Terdapat 3 clue didalamnya
```
key:ikanhiumakantomat
clue.txt
rasanyamenjadironman.jpg
```
Lalu pada hint terdapat kata **zip**, kita cek apakah ada file zip didalam file odading.png menggunakan tools **binwalk**
```
$ binwalk -e odading.png 

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             JPEG image data, JFIF standard 1.01
30            0x1E            TIFF image data, big-endian, offset of first image directory: 8
28846         0x70AE          Zip archive data, encrypted compressed size: 49, uncompressed size: 29, name: clue.txt
28944         0x7110          Zip archive data, encrypted compressed size: 25738, uncompressed size: 26114, name: rasanyamenjadironman.jpg
54965         0xD6B5          End of Zip archive, footer length: 22
```
Yap, Terdapat 3 file
```
70AE.zip  clue.txt  rasanyamenjadironman.jpg
```
Ekstrak file **70AE.zip** dengan password yang kita dapat pada langkah sebelumnya yaitu **ikanhiumakantomat**

Setelah itu saya mencoba membuka file **clue.txt** isinya sebagai berikut
```
jsteg mungkin membantu anda.
```
Gunakan tools jsteg untuk menemukan flag pada file **rasanyamenjadironman.jpg**
```
$ jsteg reveal rasanyamenjadironman.jpg 
PUCC{0D4!i9_m4n9_0l3h_r4saNy4_AJG_bgt}
```

## Flag
<details>
<summary>Tekan untuk melihat flag</summary>
    
    PUCC{0D4!i9_m4n9_0l3h_r4saNy4_AJG_bgt}
</details>