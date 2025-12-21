# Laporan Praktikum Kriptografi
Minggu ke-: 14
Topik: analisis serangan
Nama: Lesmana Desi
NIM: 230202765
Kelas: 5IKRB

---

## 1. Tujuan
Setelah mengikuti praktikum ini, mahasiswa diharapkan mampu:

Mengidentifikasi jenis serangan pada sistem informasi nyata.
Mengevaluasi kelemahan algoritma kriptografi yang digunakan.
Memberikan rekomendasi algoritma kriptografi yang sesuai untuk perbaikan keamanan.

---

## 2. Dasar Teori
Analisis serangan merupakan proses sistematis untuk mengidentifikasi, memahami, dan mengevaluasi berbagai jenis serangan yang dapat mengancam keamanan sistem informasi. Tujuan utama analisis serangan adalah untuk mengetahui cara kerja serangan, titik lemah yang dimanfaatkan penyerang, serta dampak yang ditimbulkan terhadap sistem, sehingga dapat dirancang mekanisme pencegahan dan mitigasi yang efektif.
Dalam konteks keamanan informasi, serangan umumnya menargetkan tiga aspek utama yang dikenal sebagai CIA Triad, yaitu Confidentiality (kerahasiaan), Integrity (keutuhan data), dan Availability (ketersediaan layanan). Serangan terhadap kerahasiaan bertujuan mencuri atau menyadap informasi, serangan terhadap integritas berusaha mengubah data secara tidak sah, sedangkan serangan terhadap ketersediaan bertujuan mengganggu atau melumpuhkan layanan.
Analisis serangan juga melibatkan pengelompokan jenis serangan, seperti serangan pasif (contoh: sniffing, eavesdropping) dan serangan aktif (contoh: Man-in-the-Middle, spoofing, DoS). Dengan memahami karakteristik setiap serangan, analis keamanan dapat menentukan metode deteksi yang tepat serta menerapkan kontrol keamanan seperti enkripsi, autentikasi, firewall, dan intrusion detection system (IDS).
Secara keseluruhan, dasar teori analisis serangan menjadi landasan penting dalam pengembangan sistem yang aman, karena membantu organisasi mengantisipasi ancaman, mengurangi risiko, dan menjaga keandalan serta kepercayaan terhadap sistem informasi.

## 3. Alat dan Bahan
(- Python 3.x  
- Visual Studio Code / editor lain  
- Git dan akun GitHub  
- Library tambahan (misalnya pycryptodome, jika diperlukan)  )

---

## 4. Langkah Percobaan
Pada akhir sesi ini mahasiswa menghasilkan:

Laporan studi kasus analisis serangan sistem nyata.
Rekomendasi solusi/algoritma pengganti.
Commit Git dengan format week14-analisis-serangan.

---

## 5. Source Code

## 6. Hasil dan Pembahasan
1.Identifikasi Serangan
Pada tahap ini dipilih salah satu kasus nyata serangan kriptografi, misalnya serangan brute force dan dictionary attack pada hash MD5. MD5 banyak digunakan pada sistem lama untuk menyimpan password dalam bentuk hash. Vektor serangan pada kasus ini adalah database password yang bocor, di mana penyerang mencoba mencocokkan hash MD5 dengan kata sandi umum menggunakan kamus atau perhitungan brute force.
Penyebab utama kelemahan terletak pada sifat MD5 yang sudah tidak aman, karena memiliki panjang hash yang relatif pendek dan telah terbukti rentan terhadap collision serta perhitungan cepat menggunakan perangkat keras modern seperti GPU. Hal ini membuat proses penebakan password menjadi sangat efisien bagi penyerang.
2.Evaluasi Kelemahan
Berdasarkan analisis, kelemahan utama pada kasus MD5 tidak hanya berasal dari algoritma kriptografinya, tetapi juga dari implementasi sistem. Secara algoritmik, MD5 dirancang untuk kecepatan, bukan untuk keamanan penyimpanan password, sehingga sangat rentan terhadap brute force. Dari sisi implementasi, banyak sistem menyimpan hash password tanpa menggunakan salt, yang semakin memudahkan serangan dictionary dan rainbow table.
Selain itu, konfigurasi sistem yang buruk, seperti tidak adanya pembatasan percobaan login atau monitoring keamanan, turut memperparah risiko serangan. Dengan demikian, kelemahan dapat muncul dari kombinasi algoritma yang lemah, implementasi yang tidak tepat, dan konfigurasi sistem yang kurang aman.
3.Rekomendasi Solusi
Untuk meningkatkan keamanan, disarankan mengganti algoritma yang sudah tidak aman dengan mekanisme kriptografi yang lebih kuat. Contohnya, penggunaan SHA-256 untuk hashing data umum dan bcrypt, scrypt, atau Argon2 untuk penyimpanan password. Algoritma ini dirancang lebih lambat dan mendukung penggunaan salt, sehingga lebih tahan terhadap brute force dan dictionary attack.
Selain penggantian algoritma, sistem juga perlu menerapkan kebijakan keamanan tambahan seperti pembatasan jumlah percobaan login, penggunaan autentikasi multifaktor, serta pembaruan berkala terhadap konfigurasi kriptografi. Pemilihan algoritma yang tepat akan meningkatkan keamanan sistem tanpa mengorbankan fungsionalitas, sekaligus memperpanjang umur keamanan sistem di masa depan.


---

## 7. Jawaban Pertanyaan
1.Banyak sistem lama masih rentan terhadap brute force atau dictionary attack karena menggunakan algoritma kriptografi usang dan tidak pernah diperbarui sesuai perkembangan ancaman. Selain itu, keterbatasan sumber daya dan ketergantungan pada sistem lama (legacy system) sering membuat organisasi menunda pembaruan keamanan.
2.Perbedaan antara kelemahan algoritma dan kelemahan implementasi terletak pada sumber masalahnya. Kelemahan algoritma berasal dari desain kriptografi itu sendiri, sedangkan kelemahan implementasi muncul akibat kesalahan dalam penerapan, seperti penggunaan parameter yang salah, konfigurasi yang lemah, atau pengelolaan kunci yang buruk.
3.Untuk memastikan sistem kriptografi tetap aman di masa depan, organisasi perlu melakukan audit keamanan secara berkala, mengikuti standar kriptografi terbaru, memperbarui algoritma yang sudah usang, serta meningkatkan kesadaran keamanan bagi pengembang dan pengguna sistem.

---

## 8. Kesimpulan
analisis serangan kriptografi penting untuk memahami kelemahan sistem, baik yang berasal dari algoritma, implementasi, maupun konfigurasi. Dengan melakukan evaluasi dan menerapkan algoritma yang lebih aman serta praktik keamanan yang tepat, sistem dapat terlindungi dari serangan seperti brute force dan dictionary attack, sehingga keamanan informasi dapat terjaga secara berkelanjutan.

---

## 9. Daftar Pustaka
---

## 10. Commit Log
(Tuliskan bukti commit Git yang relevan.  
Contoh:
```
commit abc12345
Author: lesmana desi <lesmanadesi1919@gmail.com>
Date:   2025-12-21

    week2-cryptosystem: implementasi Caesar Cipher dan laporan )
```
