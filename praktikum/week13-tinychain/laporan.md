# Laporan Praktikum Kriptografi
Minggu ke-: 13
Topik: tinychain
Nama: Lesmana Desi
NIM: 230202765
Kelas: 5ikrb

---

## 1. Tujuan
Setelah mengikuti praktikum ini, mahasiswa diharapkan mampu:

Menjelaskan peran hash function dalam blockchain.
Melakukan simulasi sederhana Proof of Work (PoW).
Menganalisis keamanan cryptocurrency berbasis kriptografi.

---

## 2. Dasar Teori
Tinychain merupakan konsep implementasi blockchain sederhana yang digunakan untuk memahami prinsip dasar teknologi blockchain tanpa kompleksitas sistem besar seperti Bitcoin atau Ethereum. Tinychain dirancang sebagai model pembelajaran yang menekankan pada struktur blok, mekanisme hash, serta keterkaitan antar blok dalam sebuah rantai data yang aman dan terdistribusi.
Pada Tinychain, setiap blok umumnya berisi data transaksi, hash blok sebelumnya, timestamp, dan hash blok saat ini. Hash berfungsi sebagai sidik jari digital yang menjamin integritas data, karena perubahan sekecil apa pun pada isi blok akan menghasilkan nilai hash yang berbeda. Keterkaitan hash antar blok inilah yang membentuk rantai (chain) dan membuat data sulit untuk dimanipulasi.
Tinychain juga mengadopsi konsep dasar kriptografi hash seperti SHA-256 untuk memastikan keamanan dan keutuhan data. Meskipun biasanya tidak menggunakan mekanisme konsensus kompleks seperti Proof of Work atau Proof of Stake, Tinychain tetap mencerminkan prinsip utama blockchain, yaitu immutability, transparansi, dan kepercayaan tanpa pihak ketiga.
Sebagai alat pembelajaran, Tinychain banyak digunakan untuk memahami cara kerja blockchain dalam skala kecil, seperti pencatatan data, simulasi transaksi, dan verifikasi integritas informasi. Dengan memahami Tinychain, pengguna dapat memperoleh gambaran awal tentang bagaimana teknologi blockchain diterapkan pada sistem yang lebih besar, seperti cryptocurrency, smart contract, dan sistem pencatatan digital terdesentralisasi.

---

## 3. Alat dan Bahan
(- Python 3.x  
- Visual Studio Code / editor lain  
- Git dan akun GitHub  
- Library tambahan (misalnya pycryptodome, jika diperlukan)  )

---

## 4. Langkah Percobaan
Pada akhir sesi ini mahasiswa menghasilkan:

Program Python mini blockchain sederhana dengan hash function & Proof of Work.
Screenshot hasil mining blok.
Laporan singkat analisis keamanan blockchain dan PoW.
Commit Git dengan format week13-tinychain.

---

## 5. Source Code
<img width="1214" height="583" alt="Screenshot 2025-12-21 092743" src="https://github.com/user-attachments/assets/4e6f4e81-aa31-4fb4-99f0-5fcc39b7bad4" />
<img width="1126" height="602" alt="Screenshot 2025-12-21 092809" src="https://github.com/user-attachments/assets/a6fc85a8-3cf6-4c2b-934c-865ed25f750f" />

---

## 6. Hasil dan Pembahasan
<img width="1009" height="503" alt="Screenshot 2025-12-21 093005" src="https://github.com/user-attachments/assets/c3f8133c-4762-4cde-858c-3ae39d0d940c" />
Mekanisme ini menjamin keamanan blockchain karena membuat upaya manipulasi data menjadi sangat mahal dan tidak efisien. Jika seseorang ingin mengubah isi satu blok, maka hash blok tersebut akan berubah dan mengharuskan penyerang untuk melakukan mining ulang pada blok tersebut serta seluruh blok setelahnya. Dengan demikian, Proof of Work melindungi blockchain dari pemalsuan data dan memastikan keutuhan (integrity) serta kepercayaan dalam sistem terdistribusi.

---

## 7. Jawaban Pertanyaan
1.Fungsi hash sangat penting dalam blockchain karena berperan menjaga integritas dan keamanan data. Hash menghasilkan nilai unik untuk setiap blok berdasarkan isi data di dalamnya, sehingga perubahan sekecil apa pun pada data akan mengubah hash secara signifikan. Selain itu, hash menghubungkan setiap blok dengan blok sebelumnya, membentuk rantai yang sulit dimanipulasi tanpa terdeteksi.

2.Proof of Work (PoW) mencegah double spending dengan mewajibkan setiap transaksi divalidasi dan dicatat dalam blok yang telah melalui proses mining. Untuk mengubah atau menggandakan transaksi, penyerang harus mengulang proses mining pada blok tersebut dan seluruh blok setelahnya, yang membutuhkan sumber daya komputasi sangat besar. Hal ini membuat upaya double spending menjadi tidak praktis dan tidak efisien.

3.Kelemahan PoW dalam efisiensi energi terletak pada tingginya konsumsi daya komputasi yang dibutuhkan untuk proses mining. Banyak percobaan hash harus dilakukan untuk menemukan nonce yang sesuai, sehingga memerlukan listrik dalam jumlah besar. Akibatnya, PoW dianggap kurang ramah lingkungan dan mendorong pengembangan mekanisme konsensus alternatif yang lebih hemat energi.

---

## 8. Kesimpulan
blockchain memanfaatkan fungsi hash dan mekanisme Proof of Work untuk menjaga integritas data serta mencegah kecurangan seperti double spending. Meskipun efektif dalam meningkatkan keamanan dan kepercayaan sistem, Proof of Work memiliki kelemahan dari sisi efisiensi energi, sehingga diperlukan pertimbangan dan pengembangan mekanisme alternatif yang lebih ramah lingkungan.

---

## 9. Daftar Pustaka
-

## 10. Commit Log
(Tuliskan bukti commit Git yang relevan.  
Contoh:
```
commit abc12345
Author: Lesmana Desi <lesmanadesi1919@gmail.com>
Date:   2025-12-21

    week2-cryptosystem: implementasi Caesar Cipher dan laporan )
```
