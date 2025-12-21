# Laporan Praktikum Kriptografi
Minggu ke-: 10
Topik: Public Key Infrastructure  
Nama:Lesmana Desi
NIM: 230202765
Kelas: 5IKRB  

## 1. Tujuan
1. Membuat sertifikat digital sederhana.
2. Menjelaskan peran Certificate Authority (CA) dalam sistem PKI.
3. Mengevaluasi fungsi PKI dalam komunikasi aman (contoh: HTTPS, TLS).
   
## 2. Dasar Teori
Certificate Authority (CA) merupakan pihak ketiga terpercaya yang berperan dalam menjamin keaslian identitas entitas pada sistem komunikasi digital. CA bertugas menerbitkan, mengelola, dan memverifikasi sertifikat digital yang menghubungkan identitas suatu individu, organisasi, atau sistem dengan public key tertentu. Dengan adanya CA, kepercayaan dalam pertukaran informasi dan transaksi elektronik dapat terjaga.Sertifikat digital yang diterbitkan oleh CA berisi informasi penting, seperti identitas pemilik sertifikat, public key, masa berlaku, nomor seri, serta tanda tangan digital milik CA. Tanda tangan digital tersebut digunakan untuk memastikan bahwa sertifikat tidak mengalami perubahan dan benar-benar diterbitkan oleh CA yang sah. Jika sertifikat digital berhasil diverifikasi menggunakan public key CA, maka public key di dalam sertifikat dapat dipercaya.
Dalam sistem keamanan modern, CA berfungsi sebagai fondasi Public Key Infrastructure (PKI). PKI menyediakan mekanisme untuk manajemen kunci kriptografi, termasuk proses pendaftaran, penerbitan, pencabutan, dan pembaruan sertifikat digital. CA juga bekerja sama dengan komponen lain seperti Registration Authority (RA) dan Certificate Revocation List (CRL) atau Online Certificate Status Protocol (OCSP) untuk memastikan status keabsahan sertifikat.
Peran CA sangat penting dalam mencegah serangan keamanan seperti Man-in-the-Middle (MITM), karena CA memastikan bahwa public key yang digunakan dalam proses enkripsi dan tanda tangan digital benar-benar milik entitas yang berkomunikasi. Oleh sebab itu, CA banyak digunakan dalam berbagai aplikasi keamanan, seperti protokol SSL/TLS, e-commerce, perbankan digital, e-government, dan sistem tanda tangan digital.

## 3. Alat dan Bahan
- Python 3.11  
- Visual Studio Code / editor lain  
- Git dan akun GitHub  
- Library tambahan (cryptography pyopenssl)
  
## 4. Langkah Percobaan
1. Membuat file `pki.py` di folder `praktikum/week10-pki/src/`.
2. Menyalin kode program dari panduan praktikum.
3. Menjalankan program dengan perintah `python caesar_cipher.py`.
4. mengarjakan quis

## 5. Source Code
<img width="1536" height="1056" alt="Screenshot 2025-12-21 084323" src="https://github.com/user-attachments/assets/d9bb0436-ae31-4ccb-9db7-35bd805f3fb8" />

## 6. Hasil dan Pembahasan
<img width="1509" height="988" alt="Screenshot 2025-12-21 084334" src="https://github.com/user-attachments/assets/c2f43dce-fe57-40d7-be5c-e096f779acb5" />

1. Bagaimana browser memverifikasi sertifikat HTTPS?
Saat pengguna mengakses situs HTTPS, browser akan menerima sertifikat digital dari server. Browser kemudian memeriksa apakah sertifikat tersebut ditandatangani oleh CA yang terpercaya dengan mencocokkannya terhadap daftar root CA yang tersimpan di sistem atau browser. Selanjutnya, browser memverifikasi masa berlaku sertifikat, nama domain, dan status pencabutan sertifikat. Jika seluruh proses verifikasi berhasil, koneksi HTTPS dinyatakan aman.
2. Apa yang terjadi jika CA palsu menerbitkan sertifikat?
Jika CA palsu atau tidak terpercaya menerbitkan sertifikat, browser tidak akan mengenali CA tersebut sebagai pihak terpercaya. Akibatnya, browser akan menampilkan peringatan keamanan kepada pengguna, seperti “Your connection is not private”. Namun, jika CA palsu berhasil menyusup ke dalam daftar root CA, maka sertifikat palsu tersebut dapat digunakan untuk melakukan serangan Man-in-the-Middle (MITM), sehingga membahayakan keamanan komunikasi.
3. Mengapa PKI penting dalam komunikasi aman?
Public Key Infrastructure (PKI) sangat penting karena menyediakan mekanisme kepercayaan terpusat dalam komunikasi digital. PKI memastikan keaslian identitas, menjaga integritas data, serta mendukung enkripsi komunikasi. Tanpa PKI, pengguna tidak dapat memastikan apakah mereka benar-benar berkomunikasi dengan pihak yang sah, sehingga transaksi online seperti perbankan digital, e-commerce, dan layanan e-government menjadi rentan terhadap penyadapan dan pemalsuan.
## 7. Jawaban Pertanyaan
1. Apa fungsi utama Certificate Authority (CA)?
Fungsi utama Certificate Authority (CA) adalah menjamin keaslian identitas pemilik sertifikat digital dengan cara mengaitkan identitas tersebut dengan public key melalui penerbitan sertifikat digital. CA bertindak sebagai pihak ketiga terpercaya yang melakukan verifikasi identitas sebelum menandatangani sertifikat menggunakan private key miliknya, sehingga sertifikat tersebut dapat dipercaya oleh pihak lain dalam sistem komunikasi digital.
2. Mengapa self-signed certificate tidak cukup untuk sistem produksi?
Self-signed certificate tidak cukup untuk sistem produksi karena tidak memiliki jaminan kepercayaan dari pihak ketiga. Sertifikat ini ditandatangani oleh pemiliknya sendiri, sehingga identitas pemilik tidak diverifikasi secara independen. Akibatnya, client seperti browser atau aplikasi akan menampilkan peringatan keamanan dan sertifikat mudah dipalsukan, sehingga rentan terhadap serangan Man-in-the-Middle (MITM). Oleh karena itu, sistem produksi memerlukan sertifikat yang diterbitkan oleh CA resmi dan terpercaya.
3. Bagaimana PKI mencegah serangan MITM dalam komunikasi TLS/HTTPS?
Public Key Infrastructure (PKI) mencegah serangan MITM dengan memastikan bahwa public key yang digunakan dalam komunikasi TLS/HTTPS benar-benar milik server yang sah. PKI menggunakan sertifikat digital yang ditandatangani oleh CA terpercaya, sehingga client dapat memverifikasi keaslian server melalui rantai kepercayaan (chain of trust). Jika sertifikat tidak valid atau tidak dipercaya, koneksi akan ditolak atau diperingatkan, sehingga pihak penyerang tidak dapat menyamar sebagai server yang sah.
## 8. Kesimpulan
Kesimpulannya, Certificate Authority (CA) dan Public Key Infrastructure (PKI) merupakan komponen penting dalam sistem keamanan komunikasi digital karena berperan menjamin keaslian identitas, integritas data, dan kepercayaan antar pihak. Melalui sertifikat digital yang ditandatangani CA, komunikasi TLS/HTTPS dapat terhindar dari serangan Man-in-the-Middle (MITM). Tanpa CA dan PKI yang terpercaya, sistem produksi dan transaksi online tidak dapat menjamin keamanan serta keabsahan komunikasi secara menyeluruh.

## 9. Daftar Pustaka

## 10. Commit Log

commit week10-pki
Author: Lesmana Desi <lesmanadesi1919@gmail.com>
Date:   2025-12-21
