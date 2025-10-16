# Laporan Praktikum Kriptografi
Minggu ke-: 2
Topik: cryptosystem
Nama: Lesmana Desi 
NIM:  230202765
Kelas: 5IKRB

## 1. Tujuan
1. Mengidentifikasi komponen dasar kriptosistem (plaintext, ciphertext, kunci, algoritma).
2. Menggambarkan proses enkripsi dan dekripsi sederhana.
3. Mengklasifikasikan jenis kriptosistem (simetris dan asimetris).

## 2. Dasar Teori
Membuat skema kriptosistem

Diagram Kriptosistem

Implementasi program sederhana

Simulasi enkripsi & dekripsi menggunakan substitusi sederhana (misalnya Caesar Cipher).

# file: praktikum/week2-cryptosystem/src/simple_crypto.py

def encrypt(plaintext, key):
    result = ""
    for char in plaintext:
        if char.isalpha():
            shift = 65 if char.isupper() else 97
            result += chr((ord(char) - shift + key) % 26 + shift)
        else:
            result += char
    return result

def decrypt(ciphertext, key):
    result = ""
    for char in ciphertext:
        if char.isalpha():
            shift = 65 if char.isupper() else 97
            result += chr((ord(char) - shift - key) % 26 + shift)
        else:
            result += char
    return result

if __name__ == "__main__":
    message = "<230202765><Lesmana desi>"
    key = 5

    enc = encrypt(message, key)
    dec = decrypt(enc, key)

    print("Plaintext :", message)
    print("Ciphertext:", enc)
    print("Decrypted :", dec)
Ekspektasi Keluaran

Plaintext : <230202765><Lesmana Desi>
Ciphertext: <230202765><Pmzxsfyzs Qnsf Knywn>
Decrypted : <230202765><Lesmana Desi>

## Klasifikasi Simetris & Asimetris

1. Kriptografi Simetris

Kriptografi simetris menggunakan satu kunci yang sama untuk proses enkripsi dan dekripsi.
Prosesnya lebih cepat karena operasi matematikanya sederhana, namun keamanannya bergantung sepenuhnya pada satu kunci tunggal namun jika kunci tersebut bocor, maka seluruh sistem bisa terbuka.
Algoritma jenis ini cocok digunakan untuk enkripsi data dalam jumlah besar karena mudah diterapkan dan efisien.
Contoh Algoritma:
a. AES (Advanced Encryption Standard)
Sistem penyandian blok dengan panjang 128 bit, digunakan secara luas karena efisien dan aman.
Contoh penggunaan: keamanan internet melalui TLS/SSL/HTTPS serta jaringan nirkabel (WPA2/WPA3).
b. DES (Data Encryption Standard)
Sistem penyandian blok 64 bit, dengan 56 bit sebagai kunci dan 8 bit untuk paritas.
Saat ini dianggap kurang aman karena panjang kuncinya terlalu pendek.
Contoh penggunaan: sistem pembayaran dan ATM untuk enkripsi PIN, serta keamanan jaringan pribadi (VPN).
2. Kriptografi Asimetris
Kriptografi asimetris menggunakan dua kunci berbeda, yaitu kunci publik untuk enkripsi dan kunci privat untuk dekripsi.
Prosesnya lebih lambat karena perhitungan matematikanya lebih kompleks, namun lebih aman karena pesan hanya bisa didekripsi oleh pemilik kunci privat, meskipun kunci publik diketahui umum.
Contoh Algoritma:
a. RSA (Rivest–Shamir–Adleman)
Menggunakan dua kunci, publik untuk enkripsi dan privat untuk dekripsi.
Contoh penggunaan: tanda tangan digital dan distribusi kunci.
b. ECC (Elliptic Curve Cryptography)
Menggunakan kunci dengan panjang 256 bit berbasis operasi titik kurva elips yang sulit dibalik dan sangat aman.
Contoh penggunaan: mata uang kripto (blockchain) dan otoritas sertifikat digital.
## 3. Alat dan Bahan
Python 3.x
Visual Studio Code
akun GitHub
Google chrome
Google schollar.
## 4. Langkah percobaan 
1.Membuat file simple_crypto.py di folder praktikum/week2-cryptosystem/src/.
2.Menyalin kode program dari panduan praktikum.
3.Menjalankan program dengan perintah python simple_crypto.py.
4.Membuat ringkasan perbedaan antara kriptosistem simetris dan asimetris.
5.Mengaploud hasil eksekusi di folder praktikum/week2-cryptosistem/screenshots/
6.Menjawab pertanyaan diskusi.

## 5. Source Code

file: praktikum/week2-cryptosystem/src/simple_crypto.py

def encrypt(plaintext, key):
    result = ""
    for char in plaintext:
        if char.isalpha():
            shift = 65 if char.isupper() else 97
            result += chr((ord(char) - shift + key) % 26 + shift)
        else:
            result += char
    return result

def decrypt(ciphertext, key):
    result = ""
    for char in ciphertext:
        if char.isalpha():
            shift = 65 if char.isupper() else 97
            result += chr((ord(char) - shift - key) % 26 + shift)
        else:
            result += char
    return result

if __name__ == "__main__":
    message = "<230202765><Lesmana Desi>"
    key = 5

    enc = encrypt(message, key)
    dec = decrypt(enc, key)

    print("Plaintext :", message)
    print("Ciphertext:", enc)
    print("Decrypted :", dec)

## 6. Hasil dan Pembahasan
 Hasil dari program yang diberikan dari github menunjukan bahwa enkripsi yang digunakan adalah caesar chiper dengan hasil enkripsi hanya teks berupa huruf saja yang terenkripsi sedangkan angka tidak terenkripsi, lalu saya modifikasi programnya dengan menambahkan baris : elif char.isdigit(): # Enkripsi Angka (menggeser dalam rentang 0-9) # 48 adalah nilai ASCII untuk '0' shift = 48 # (ord(char) - shift) menghasilkan nilai 0-9 dari digit. # Kemudian geser (shift) dengan key, mod 10, dan tambahkan kembali shift. result += chr((ord(char) - shift + key) % 10 + shift) dengan menambahkan baris tersebut maka sekarang karakter angka pun menjadi ikut terenkripsi juga. untuk perbandingan
hasilnya bisa dilihat pada tangkapan layar berikut 
![diagram](https://github.com/user-attachments/assets/1649df8b-a815-4d5e-a3e5-cd1d139773b3)
![program](https://github.com/user-attachments/assets/3105b490-aaf5-4cc4-b888-d1bbabea93f5)

## 7. Jawaban Pertanyaan
1. Sebutkan komponen utama dalam sebuah kriptosistem.
Apa kelebihan dan kelemahan sistem simetris dibandingkan asimetris?
Mengapa distribusi kunci menjadi masalah utama dalam kriptografi simetris?
Jawaban :
Komponen Utama dalam Sebuah Kriptosistem
- Plaintext (Teks Asli), Pesan atau data asli yang ingin dikirim.
- Ciphertext (Teks Terenkripsi), Hasil dari proses enkripsi yang tidak dapat dibaca tanpa kunci dekripsi.
- Key (Kunci), Informasi rahasia yang digunakan dalam proses enkripsi dan dekripsi.
- Algoritma Enkripsi/Dekripsi, Metode atau aturan yang digunakan untuk menyandikan dan membuka pesan.
2. Kelebihan dan Kelemahan Sistem Simetris dan Asimetris
  Sistem Kriptografi Simetris
Kelebihan:
Prosesnya lebih cepat karena algoritmanya sederhana.
Efisien dalam penggunaan sumber daya.
Mudah diimplementasikan.
Kelemahan:
Risiko kebocoran data tinggi.
Distribusi kunci sulit dan tidak aman.
Kurang cocok untuk sistem berskala besar.
Sistem Kriptografi Asimetris
Kelebihan:
Distribusi kunci lebih aman karena menggunakan dua kunci berbeda (publik dan privat).
Cocok untuk sistem komunikasi terbuka seperti internet.
Mendukung tanda tangan digital.
Kelemahan:
Prosesnya lebih lambat karena operasi matematikanya kompleks.
Membutuhkan daya komputasi besar.
Implementasinya lebih kompleks.
3.Karena kriptografi simetris hanya menggunakan kunci tunggal untuk enkripsi dan dekripsi sehingga dalam proses distribusi sangat berisiko terhadapp penyadapan atau pencurian.

## 8. Kesimpulan
Penggunaan kriptografi sangat penting untuk menjaga kerahasiaan data melalui proses enkripsi dan dekripsi. Selain itu kriptografi dibagi menjadi 2 yaitu simetris dan asimetris, dimana kriptografi simetris menggunakan satu kunci untuk enkripsi dan dekripsi sedangkan kriptografi asimetris menggunakan dua kunci yang berbeda.

## 9. Daftar Pustaka
Stallings, William. Cryptography and Network Security: Principles and Practice. 7th Edition. Pearson, 2017.

Paar, Christof, and Jan Pelzl. Understanding Cryptography: A Textbook for Students and Practitioners. Springer, 2010.

Menezes, Alfred J., Paul C. van Oorschot, and Scott A. Vanstone. Handbook of Applied Cryptography. CRC Press, 1996.
## 10. Commit Log
commit abc12345
Author: Lesmana Desi <lesmanadesi19191@gmail.com>
Date:   2025-10-16

    week2-cryptosystem: implementasi Caesar Cipher dan laporan )
```
