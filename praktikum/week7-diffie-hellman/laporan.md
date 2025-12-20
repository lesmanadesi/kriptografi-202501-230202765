# Laporan Praktikum Kriptografi
Minggu ke-: 7
Topik: Diffie-hellman
Nama: Lesmana Desi
NIM: 230202765
Kelas: 5Ikrb

---

## 1. Tujuan
1. Melakukan simulasi protokol Diffie-Hellman untuk pertukaran kunci publik.
2. Menjelaskan mekanisme pertukaran kunci rahasia menggunakan bilangan prima dan logaritma diskrit.
3. Menganalisis potensi serangan pada protokol Diffie-Hellman (termasuk serangan Man-in-the-Middle / MITM).


## 2. Dasar Teori
Diffie–Hellman adalah metode pertukaran kunci dalam kriptografi yang memungkinkan dua pihak untuk menghasilkan kunci rahasia bersama melalui saluran komunikasi yang tidak aman. Metode ini diperkenalkan oleh Whitfield Diffie dan Martin Hellman pada tahun 1976 sebagai solusi atas masalah distribusi kunci pada sistem kriptografi simetris. Diffie–Hellman bekerja dengan memanfaatkan konsep matematika seperti bilangan prima, aritmetika modulo, dan masalah logaritma diskret yang sulit dipecahkan. Kedua pihak menyepakati parameter publik berupa bilangan prima dan generator, lalu masing-masing memilih bilangan rahasia pribadi untuk menghasilkan nilai publik yang dipertukarkan. Dari nilai tersebut, kedua pihak dapat menghitung kunci rahasia yang sama tanpa pernah mengirimkan kunci tersebut secara langsung. Keamanan algoritma Diffie–Hellman bergantung pada kesulitan menyelesaikan masalah logaritma diskret serta pemilihan parameter yang tepat, namun metode ini tidak menyediakan mekanisme autentikasi sehingga perlu dikombinasikan dengan sistem keamanan lain untuk mencegah serangan pihak ketiga.

## 3. Alat dan Bahan
- Python  
- Visual Studio Code  
- Git dan akun GitHub  


---

## 4. Langkah Percobaan
(Tuliskan langkah yang dilakukan sesuai instruksi.  
Contoh format:
1. Membuat file `diffie- hellman.py` di folder `praktikum/week7-diffie-hellman/src/`.
2. Menyalin kode program dari panduan praktikum.
3. Menjalankan program dengan perintah `python diffie-hellman.py`.)

---

## 5. Source Code
import random

# parameter umum (disepakati publik)
p = 23  # bilangan prima
g = 5   # generator

# private key masing-masing pihak
a = random.randint(1, p-1)  # secret Alice
b = random.randint(1, p-1)  # secret Bob

# public key
A = pow(g, a, p)
B = pow(g, b, p)

# exchange public key
shared_secret_A = pow(B, a, p)
shared_secret_B = pow(A, b, p)

print("Kunci bersama Alice :", shared_secret_A)
print("Kunci bersama Bob   :", shared_secret_B)  


## 6. Hasil dan Pembahasan



## 7. Jawaban Pertanyaan
1. Mengapa Diffie–Hellman memungkinkan pertukaran kunci di saluran publik?
Diffie–Hellman memungkinkan pertukaran kunci di saluran publik karena kunci rahasia tidak pernah dikirimkan secara langsung. Kedua pihak hanya menukar nilai publik yang dihasilkan dari perhitungan matematika menggunakan bilangan rahasia masing-masing. Keamanan proses ini bergantung pada sulitnya memecahkan masalah logaritma diskret, sehingga meskipun pihak lain menyadap komunikasi dan mengetahui nilai publik yang dipertukarkan, ia tetap tidak dapat menghitung kunci rahasia bersama.

2. Apa kelemahan utama protokol Diffie–Hellman murni?
Kelemahan utama protokol Diffie–Hellman murni adalah tidak adanya mekanisme autentikasi. Protokol ini tidak dapat memastikan identitas pihak yang berkomunikasi, sehingga penyerang dapat menyamar sebagai pihak lain dan melakukan serangan man-in-the-middle (MITM) tanpa terdeteksi.

3. Bagaimana cara mencegah serangan MITM pada protokol ini?
Serangan MITM pada Diffie–Hellman dapat dicegah dengan menambahkan mekanisme autentikasi, seperti penggunaan sertifikat digital, tanda tangan digital, atau protokol keamanan yang menggabungkan Diffie–Hellman dengan sistem autentikasi, misalnya pada TLS/SSL. Dengan autentikasi, setiap pihak dapat memverifikasi identitas lawan komunikasi sebelum menyepakati kunci rahasia bersama.
## 8. Kesimpulan
Diffie–Hellman merupakan salah satu algoritma fundamental dalam kriptografi modern yang berperan penting dalam proses pertukaran kunci rahasia secara aman melalui saluran komunikasi publik. Algoritma ini mampu mengatasi permasalahan distribusi kunci yang sering muncul pada sistem kriptografi simetris dengan memungkinkan dua pihak menghasilkan kunci bersama tanpa harus mengirimkan kunci tersebut secara langsung. Keamanan Diffie–Hellman didasarkan pada konsep matematika yang kuat, khususnya masalah logaritma diskret yang sulit dipecahkan, sehingga pihak yang tidak berwenang tidak dapat dengan mudah memperoleh kunci rahasia meskipun dapat mengamati proses pertukaran data. Namun demikian, Diffie–Hellman murni memiliki kelemahan karena tidak menyediakan mekanisme autentikasi, yang membuatnya rentan terhadap serangan man-in-the-middle. Oleh sebab itu, dalam penerapannya, algoritma ini biasanya dikombinasikan dengan metode autentikasi seperti sertifikat digital atau tanda tangan digital. Dengan penerapan yang tepat dan parameter keamanan yang memadai, Diffie–Hellman tetap menjadi fondasi utama dalam berbagai protokol keamanan jaringan dan berkontribusi besar dalam menjaga kerahasiaan serta keamanan komunikasi digital.

---

## 9. Daftar Pustaka
1.Stallings, W. (2017). Cryptography and Network Security: Principles and Practice. Pearson Education.
2.Schneier, B. (2015). Applied Cryptography: Protocols, Algorithms, and Source Code in C. John Wiley & Sons.

---

## 10. Commit Log
(Tuliskan bukti commit Git yang relevan.  
Contoh:
```
commit abc12345
Author: Lesmana Desi <lesmanadesi1919@gmail.com>
Date:   2025-12-20

    week7-diffie-hellman: implementasi diffie-hellman dan laporan )
```
