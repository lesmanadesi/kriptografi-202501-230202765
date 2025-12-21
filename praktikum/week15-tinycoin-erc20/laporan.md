# Laporan Praktikum Kriptografi
Minggu ke-: 15
Topik: tinycoin 
Nama: Lesmana Desi
NIM: 230202765
Kelas: 5 IKRB

---

## 1. Tujuan
Setelah mengikuti praktikum ini, mahasiswa diharapkan mampu:

Mengembangkan proyek sederhana berbasis algoritma kriptografi.
Mendokumentasikan proses implementasi proyek ke dalam repository Git.
Menyusun laporan teknis hasil proyek akhir.

--

## 2. Dasar Teori
Tinycoin merupakan model cryptocurrency sederhana yang dirancang sebagai sarana pembelajaran untuk memahami konsep dasar mata uang kripto dan teknologi blockchain. Tinycoin tidak ditujukan sebagai sistem pembayaran nyata, melainkan sebagai simulasi untuk mempelajari bagaimana transaksi digital dicatat, divalidasi, dan diamankan secara terdesentralisasi.
Tinycoin bekerja di atas blockchain, yaitu struktur data berbentuk rantai blok yang saling terhubung melalui nilai hash. Setiap blok menyimpan informasi transaksi, hash blok sebelumnya, timestamp, serta nonce yang digunakan dalam proses Proof of Work (PoW). Hash kriptografi, seperti SHA-256, berperan menjaga integritas data sehingga setiap perubahan pada blok dapat langsung terdeteksi.
Dalam sistem Tinycoin, transaksi diverifikasi melalui mekanisme konsensus sederhana, umumnya menggunakan Proof of Work. Mekanisme ini mewajibkan penambang (miner) menyelesaikan perhitungan kriptografi tertentu sebelum sebuah blok dapat ditambahkan ke blockchain. Proses ini mencegah pemalsuan transaksi dan serangan double spending.
Sebagai alat pembelajaran, Tinycoin membantu memahami prinsip penting cryptocurrency, seperti desentralisasi, keamanan kriptografi, dan transparansi transaksi. Dengan mempelajari Tinycoin, pengguna memperoleh gambaran awal tentang cara kerja sistem cryptocurrency nyata seperti Bitcoin, sekaligus memahami tantangan yang ada, termasuk efisiensi energi dan skalabilitas.

---

## 3. Alat dan Bahan
(- Python 3.x  
- Visual Studio Code / editor lain  
- Git dan akun GitHub  
- Library tambahan (misalnya pycryptodome, jika diperlukan)  )

---

## 4. Langkah Percobaan
Pada akhir sesi ini mahasiswa menghasilkan:

Implementasi smart contract ERC20 (TinyCoin) menggunakan Solidity.
Dokumentasi proyek di repository Git (kode, README, laporan).
Laporan teknis berisi penjelasan implementasi, hasil pengujian, serta analisis keamanan dasar.
Commit Git dengan format week15-tinycoin-erc20.

---

## 5. Source Code
(Salin kode program utama yang dibuat atau dimodifikasi.  
Gunakan blok kode:

```python
# contoh potongan kode
def encrypt(text, key):
    return ...
```
)

---

## 6. Hasil dan Pembahasan
(- Lampirkan screenshot hasil eksekusi program (taruh di folder `screenshots/`).  
- Berikan tabel atau ringkasan hasil uji jika diperlukan.  
- Jelaskan apakah hasil sesuai ekspektasi.  
- Bahas error (jika ada) dan solusinya. 

Hasil eksekusi program Caesar Cipher:

![Hasil Eksekusi](screenshots/output.png)
![Hasil Input](screenshots/input.png)
![Hasil Output](screenshots/output.png)
)

---

## 7. Jawaban Pertanyaan
(Jawab pertanyaan diskusi yang diberikan pada modul.  
- Pertanyaan 1: …  
- Pertanyaan 2: …  
)
---

## 8. Kesimpulan
(Tuliskan kesimpulan singkat (2–3 kalimat) berdasarkan percobaan.  )

---

## 9. Daftar Pustaka
(Cantumkan referensi yang digunakan.  
Contoh:  
- Katz, J., & Lindell, Y. *Introduction to Modern Cryptography*.  
- Stallings, W. *Cryptography and Network Security*.  )

---

## 10. Commit Log
(Tuliskan bukti commit Git yang relevan.  
Contoh:
```
commit abc12345
Author: Nama Mahasiswa <email>
Date:   2025-09-20

    week2-cryptosystem: implementasi Caesar Cipher dan laporan )
```
