# Laporan Praktikum Kriptografi
Minggu ke-: 3
Topik: modmath-gcd
Nama: Lesmana Desi 
NIM: 230202765
Kelas:5 IKRB

---

## 1. Tujuan
Setelah mengikuti praktikum ini, mahasiswa diharapkan mampu:

Menyelesaikan operasi aritmetika modular.
Menentukan bilangan prima dan menghitung GCD (Greatest Common Divisor).
Menerapkan logaritma diskrit sederhana dalam simulasi kriptografi.

---

## 2. Dasar Teori
Cipher klasik merupakan dasar dari perkembangan kriptografi modern yang berfungsi untuk menjaga kerahasiaan pesan melalui proses enkripsi dan dekripsi. Dengan memanfaatkan konsep aritmetika modular, proses perubahan huruf atau simbol dapat dilakukan secara sistematis dan berulang. Meskipun metode ini tergolong sederhana dan mudah dipecahkan dengan teknologi saat ini, cipher klasik tetap penting sebagai fondasi dalam memahami prinsip dasar keamanan data dan sistem kriptografi modern.

---

## 3. Alat dan Bahan
(- Python 3.x  
- Visual Studio Code / editor lain  
- Git dan akun GitHub  

---

## 4. Langkah Percobaan
1.Program Python (src/) berisi implementasi:
Modular arithmetic (add, sub, mul, exp).
GCD & Euclidean Algorithm.
Extended Euclidean & modular inverse.
Discrete log sederhana.
2.Screenshot hasil eksekusi program.
3.Laporan laporan.md berisi:
Ringkasan teori modular arithmetic & GCD.
Hasil pengujian dengan contoh kasus.
Jawaban pertanyaan diskusi.
---

## 5. Source Code
## 1.Langkah 1 — Aritmetika Modular
def mod_add(a, b, n): return (a + b) % n
def mod_sub(a, b, n): return (a - b) % n
def mod_mul(a, b, n): return (a * b) % n
def mod_exp(base, exp, n): return pow(base, exp, n)  # eksponensiasi modular

print("7 + 5 mod 12 =", mod_add(7, 5, 12))
print("7 * 5 mod 12 =", mod_mul(7, 5, 12))
print("7^128 mod 13 =", mod_exp(7, 128, 13))

## 2.Langkah 2 — GCD & Algoritma Euclidean
def gcd(a, b):
    while b != 0:
        a, b = b, a % b
    return a

print("gcd(54, 24) =", gcd(54, 24))

## 3.Langkah 3 — Extended Euclidean Algorithm
def egcd(a, b):
    if a == 0:
        return b, 0, 1
    g, x1, y1 = egcd(b % a, a)
    return g, y1 - (b // a) * x1, x1

def modinv(a, n):
    g, x, _ = egcd(a, n)
    if g != 1:
        return None
    return x % n

print("Invers 3 mod 11 =", modinv(3, 11))  # hasil: 4
## 4.Langkah 4 — Logaritma Diskrit (Discrete Log)
def discrete_log(a, b, n):
    for x in range(n):
        if pow(a, x, n) == b:
            return x
    return None

print("3^x ≡ 4 (mod 7), x =", discrete_log(3, 4, 7))  # hasil: 4
---

## 6. Hasil dan Pembahasan
1.Pengujian dilakukan terhadap empat fungsi utama yaitu discrete_log, modinv, gcd, dan operasi aritmetika modular (mod_add, mod_mul, mod_exp). Semua fungsi berhasil dijalankan tanpa error dan menghasilkan output sesuai dengan teori yang diharapkan.
•	Fungsi discrete_log menghasilkan nilai x = 4, sesuai dengan persamaan 3x≡4 (mod 7)3^x ≡ 4 \ (mod\ 7)3x≡4 (mod 7).
•	Fungsi modinv memberikan hasil 4, yang merupakan invers dari 3 dalam modulo 11.
•	Fungsi gcd menghasilkan nilai 6, sesuai dengan pembagi terbesar dari 54 dan 24.
•	Fungsi operasi modular memberikan hasil 0, 11, dan 3 masing-masing untuk penjumlahan, perkalian, dan eksponensiasi.
2.Analisis Hasil
Semua fungsi berjalan sesuai ekspektasi dan menghasilkan output yang benar berdasarkan konsep aritmetika modular dan teori kriptografi dasar:
•	Fungsi discrete_log berhasil mencari nilai x yang memenuhi persamaan ax≡b(modn)a^x ≡ b (mod n)ax≡b(modn).
•	Fungsi modinv menghitung invers modular dengan benar menggunakan algoritma Euclidean diperluas.
•	Fungsi gcd menunjukkan hasil pembagi terbesar dari dua bilangan secara tepat.
•	Fungsi operasi modular (penjumlahan, perkalian, dan eksponensiasi) memberikan hasil sesuai aturan matematika modular.
3.Pembahasan Error (Jika Ada)
Selama pengujian:
•	Tidak ditemukan error sintaks maupun runtime.
•	Semua kode berhasil dijalankan di VS Code menggunakan Python 3.14.
•	Namun, jika terjadi error “pow() takes no keyword arguments” pada Python versi lama, solusinya adalah mengganti pemanggilan pow(base, exp, n) (tanpa mod) agar kompatibel.

Hasil eksekusi program Caesar Cipher:
<img width="1366" height="728" alt="hasil Logaritma Diskrit " src="https://github.com/user-attachments/assets/07744da7-6993-4abd-8cc1-07aa09a34cc2" />
<img width="1366" height="728" alt="hasil GCD   algoritma euclidean " src="https://github.com/user-attachments/assets/6439f67f-d02a-4e53-b932-e71f815414ae" />
<img width="1366" height="728" alt="hasil extended euclidean algoritma" src="https://github.com/user-attachments/assets/ec8e4f7d-1877-48f0-a25c-fe7dfd4624bc" />
<img width="1366" height="728" alt="hasil aritmatika modular" src="https://github.com/user-attachments/assets/e642ec0e-b044-44c8-acc8-f1638628d4b6" />

---

## 7. Jawaban Pertanyaan
1. Peran Aritmetika Modular dalam Kriptografi Modern
Aritmetika modular berperan sebagai dasar utama operasi matematika dalam berbagai algoritma kriptografi modern, seperti RSA, Diffie-Hellman, dan ElGamal. Sistem ini memungkinkan perhitungan dilakukan dalam ruang bilangan terbatas (modulus tertentu), sehingga hasil operasi tetap aman, terprediksi, dan efisien untuk komputasi digital. Dengan menggunakan modulus, pesan atau kunci dapat diubah menjadi bentuk yang sulit dibalik tanpa informasi khusus (seperti kunci privat), sehingga menjaga kerahasiaan dan integritas data.
2. Pentingnya Invers Modular dalam Algoritma Kunci Publik (RSA)
Invers modular sangat penting dalam algoritma RSA, karena digunakan dalam proses dekripsi dan penandatanganan digital.
Pada RSA, kunci privat ddd merupakan invers modular dari kunci publik eee terhadap φ(n)\varphi(n)φ(n) (fungsi totient Euler), atau ditulis sebagai:
e×d≡1 (mod φ(n))e \times d \equiv 1 \ (\text{mod } \varphi(n))e×d≡1 (mod φ(n)) 
Tanpa kemampuan menghitung invers modular ini, pesan yang telah dienkripsi tidak dapat dikembalikan ke bentuk aslinya. Jadi, invers modular adalah komponen kunci yang memastikan enkripsi dan dekripsi saling membalikkan secara matematis.
3. Tantangan Utama dalam Menyelesaikan Logaritma Diskrit untuk Modulus Besar
Tantangan utama terletak pada tingginya kompleksitas komputasi.
Untuk modulus besar (misalnya ratusan atau ribuan bit), mencari xxx yang memenuhi ax≡b (mod n)a^x \equiv b \ (\text{mod } n)ax≡b (mod n) memerlukan waktu yang sangat lama karena tidak ada algoritma efisien yang dapat menghitung logaritma diskrit dengan cepat. Kesulitan inilah yang menjadi dasar keamanan dari algoritma seperti Diffie-Hellman dan ElGamal, karena bahkan komputer modern membutuhkan waktu sangat lama untuk memecahkannya tanpa kunci yang tepat.

---

## 8. Kesimpulan
Dari hasil praktikum ini dapat disimpulkan bahwa aritmetika modular merupakan konsep fundamental dalam kriptografi yang berperan penting dalam berbagai algoritma keamanan data modern seperti RSA, Diffie-Hellman, dan ElGamal. Melalui implementasi fungsi modular arithmetic, GCD, extended Euclidean, dan logaritma diskrit, mahasiswa dapat memahami bagaimana operasi matematika sederhana dapat membentuk dasar sistem enkripsi yang kompleks.
Seluruh program berhasil dijalankan tanpa error dan memberikan hasil sesuai teori, menunjukkan bahwa perhitungan modular bekerja dengan konsisten dalam proses enkripsi dan dekripsi. Selain itu, pentingnya invers modular dan kesulitan logaritma diskrit menegaskan bahwa keamanan kriptografi modern bergantung pada kompleksitas matematika yang sulit dipecahkan. Dengan demikian, praktikum ini berhasil mencapai tujuan pembelajaran, yaitu memahami dan menerapkan operasi dasar aritmetika modular dalam konteks kriptografi.
---
## 9. Daftar Pustaka
 Stallings, W. (2017). Cryptography and Network Security: Principles and Practice (7th Edition). Pearson Education.
Schneier, B. (1996). Applied Cryptography: Protocols, Algorithms, and Source Code in C (2nd Edition). John Wiley & Sons.
Paar, C., & Pelzl, J. (2010). Understanding Cryptography: A Textbook for Students and Practitioners. Springer.
---
## 10. Commit Log

commit abc12345
Author: lesmana desi <lesmanadesi1919@gmail.com>
Date:   2025-09-20

    week2-cryptosystem: implementasi Caesar Cipher dan laporan )
```
