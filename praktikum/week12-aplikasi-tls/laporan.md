# Laporan Praktikum Kriptografi
Minggu ke-: 12
Topik: aplikasi-tls
Nama: Lesmana Desi
NIM: 230202765 
Kelas: 5 IKRB

---

## 1. Tujuan
Setelah mengikuti praktikum ini, mahasiswa diharapkan mampu:

Menganalisis penggunaan kriptografi pada email dan SSL/TLS.
Menjelaskan enkripsi dalam transaksi e-commerce.
Mengevaluasi isu etika & privasi dalam penggunaan kriptografi di kehidupan sehari-hari.

---

## 2. Dasar Teori
Transport Layer Security (TLS) adalah protokol keamanan yang digunakan untuk melindungi komunikasi data pada jaringan komputer, khususnya pada aplikasi berbasis internet. TLS bekerja di lapisan transport dan berfungsi untuk menjamin kerahasiaan (confidentiality), integritas data (integrity), serta otentikasi (authentication) antara klien dan server. Protokol ini merupakan pengembangan dari Secure Socket Layer (SSL) dan saat ini menjadi standar utama dalam komunikasi aman.Dalam penerapannya, TLS menggunakan kombinasi kriptografi asimetris dan simetris. Kriptografi asimetris digunakan pada tahap handshake untuk proses otentikasi dan pertukaran kunci secara aman, biasanya dengan bantuan sertifikat digital yang diterbitkan oleh Certificate Authority (CA). Setelah kunci sesi berhasil dibentuk, TLS beralih menggunakan kriptografi simetris karena lebih efisien untuk mengenkripsi data selama komunikasi berlangsung.
TLS banyak diaplikasikan pada berbagai layanan jaringan, seperti HTTPS pada web, email (SMTPS, IMAPS), VPN, dan aplikasi client-server lainnya. Dengan adanya TLS, data yang dikirimkan melalui jaringan publik terlindungi dari penyadapan, manipulasi, serta serangan Man-in-the-Middle (MITM), sehingga sangat penting dalam menjaga keamanan transaksi dan pertukaran informasi digital.

---

## 3. Alat dan Bahan
(- Python 3.x  
- Visual Studio Code / editor lain  
- Git dan akun GitHub  
- Library tambahan (misalnya pycryptodome, jika diperlukan)  )

---

## 4. Langkah Percobaan
(Tuliskan langkah yang dilakukan sesuai instruksi.  
Contoh format:
1. Membuat file `caesar_cipher.py` di folder `praktikum/week2-cryptosystem/src/`.
2. Menyalin kode program dari panduan praktikum.
3. Menjalankan program dengan perintah `python caesar_cipher.py`.)

---

## 5. Source Code

---

## 6. Hasil dan Pembahasan
1.Analisis SSL/TLS pada Email & Web
Berdasarkan pengamatan pada website e-commerce seperti Tokopedia, Shopee, dan Bukalapak menggunakan browser Chrome atau Firefox, dapat diketahui bahwa seluruh website tersebut telah menggunakan protokol HTTPS yang ditandai dengan ikon gembok pada address bar. Sertifikat digital yang digunakan umumnya diterbitkan oleh Certificate Authority (CA) terpercaya seperti DigiCert, Google Trust Services, atau Let’s Encrypt. Masa berlaku sertifikat biasanya berkisar antara beberapa bulan hingga satu tahun, sesuai dengan kebijakan CA modern.
Algoritma kriptografi yang digunakan pada koneksi HTTPS merupakan kombinasi dari kriptografi asimetris dan simetris. Algoritma asimetris seperti RSA atau ECDSA digunakan pada proses handshake untuk pertukaran kunci dan autentikasi server, sedangkan algoritma simetris seperti AES digunakan untuk mengenkripsi data selama sesi komunikasi berlangsung. Selain itu, fungsi hash seperti SHA-256 digunakan untuk menjaga integritas data.
Perbedaan utama antara website dengan HTTPS dan tanpa HTTPS terletak pada tingkat keamanannya. Website HTTPS mengenkripsi seluruh data yang dikirimkan sehingga terlindungi dari penyadapan dan manipulasi, sedangkan website tanpa HTTPS (HTTP) mengirim data dalam bentuk plaintext yang mudah disadap, dimodifikasi, atau disalahgunakan oleh pihak tidak bertanggung jawab.
2.Studi Kasus E-commerce
Dalam sistem e-commerce, enkripsi TLS berperan penting dalam melindungi data sensitif pengguna, terutama saat proses login, pengisian data pribadi, dan transaksi pembayaran. Informasi seperti username, password, nomor kartu, serta detail transaksi dienkripsi sebelum dikirim melalui jaringan, sehingga hanya server yang sah yang dapat membacanya.Apabila TLS tidak digunakan, transaksi online sangat rentan terhadap berbagai ancaman keamanan. Salah satu ancaman utama adalah serangan Man-in-the-Middle (MITM), di mana penyerang dapat mencegat komunikasi antara pengguna dan server, mencuri kredensial login, atau memanipulasi data transaksi. Selain itu, tanpa TLS, penyerang juga dapat melakukan pencurian identitas dan penyalahgunaan informasi finansial, yang dapat merugikan pengguna maupun penyedia layanan e-commerce.
3.Analisis Etika & Privasi
Penggunaan email terenkripsi seperti PGP dan S/MIME menimbulkan isu privasi yang penting karena hanya pengirim dan penerima yang dapat membaca isi pesan. Hal ini melindungi kerahasiaan komunikasi, namun juga menimbulkan tantangan dalam konteks organisasi dan penegakan hukum.
Dari sisi etika, muncul dilema apakah perusahaan diperbolehkan melakukan dekripsi email karyawan untuk keperluan audit atau keamanan internal. Di satu sisi, perusahaan perlu menjaga keamanan dan kepatuhan terhadap kebijakan internal, namun di sisi lain, privasi karyawan harus tetap dihormati. Oleh karena itu, kebijakan dekripsi harus transparan, memiliki dasar hukum yang jelas, dan disetujui oleh pihak terkait.
Dalam konteks pemerintah, pengawasan terhadap komunikasi terenkripsi juga menimbulkan perdebatan antara kepentingan keamanan nasional dan hak privasi individu. Penggunaan enkripsi yang kuat melindungi masyarakat dari kejahatan siber, tetapi juga dapat menyulitkan proses investigasi hukum. Oleh sebab itu, diperlukan regulasi yang seimbang agar keamanan dan privasi dapat berjalan berdampingan.

## 7. Jawaban Pertanyaan
1.Perbedaan utama antara HTTP dan HTTPS terletak pada keamanannya. HTTP mengirimkan data dalam bentuk teks biasa (plaintext) sehingga mudah disadap dan dimodifikasi oleh pihak lain. Sebaliknya, HTTPS menggunakan protokol TLS untuk mengenkripsi data yang dikirim antara klien dan server, sehingga komunikasi menjadi lebih aman, terlindungi dari penyadapan, dan menjamin integritas data.

2.Sertifikat digital penting dalam komunikasi TLS karena berfungsi untuk memverifikasi identitas server yang diakses. Sertifikat digital yang diterbitkan oleh Certificate Authority (CA) memastikan bahwa public key yang digunakan benar-benar milik server yang sah, sehingga mencegah serangan pemalsuan identitas dan Man-in-the-Middle (MITM).

3.Kriptografi mendukung privasi dalam komunikasi digital dengan mengenkripsi data agar hanya pihak yang berwenang yang dapat mengaksesnya. Namun, di sisi lain, kriptografi juga menimbulkan tantangan hukum dan etika karena dapat menghambat proses pengawasan, investigasi, dan penegakan hukum. Hal ini menimbulkan dilema antara perlindungan hak privasi individu dan kebutuhan negara atau organisasi untuk menjaga keamanan serta kepatuhan hukum.

---

## 8. Kesimpulan
penggunaan HTTPS dan TLS sangat penting untuk melindungi komunikasi digital dari penyadapan dan manipulasi data. Sertifikat digital berperan memastikan keaslian pihak yang berkomunikasi, sementara kriptografi menjaga privasi pengguna. Namun, penerapan enkripsi yang kuat juga perlu diimbangi dengan regulasi dan etika yang tepat agar keamanan dan perlindungan privasi dapat berjalan seimbang.

---

## 9. Daftar Pustaka
---

## 10. Commit Log
(Tuliskan bukti commit Git yang relevan.  
Contoh:
```
commit abc12345
Author: Lesmana Desi <lesmanadesi1919@gmail.com>
Date:   2025-12-21

    week2-cryptosystem: implementasi Caesar Cipher dan laporan )
```
