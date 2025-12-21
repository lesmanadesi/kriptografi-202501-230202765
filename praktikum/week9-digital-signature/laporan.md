# Laporan Praktikum Kriptografi
Minggu ke-: 9
Topik: Digital Signature  
Nama: Lesmana Desi
NIM: 230202765
Kelas: 5IKRB  

## 1. Tujuan
1. Mengimplementasikan tanda tangan digital menggunakan algoritma RSA/DSA.
2. Memverifikasi keaslian tanda tangan digital.
3. Menjelaskan manfaat tanda tangan digital dalam otentikasi pesan dan integritas data.

## 2. Dasar Teori
Digital signature atau tanda tangan digital merupakan teknik kriptografi yang digunakan untuk menjamin keaslian (authentication), keutuhan data (integrity), dan nirpenyangkalan (non-repudiation) dalam komunikasi digital. Digital signature berfungsi sebagai pengganti tanda tangan manual pada dokumen elektronik, namun dengan tingkat keamanan yang lebih tinggi karena berbasis algoritma matematika dan kriptografi kunci publik.

Digital signature bekerja dengan memanfaatkan kriptografi asimetris, yaitu menggunakan sepasang kunci yang saling berhubungan, terdiri dari private key (kunci privat) dan public key (kunci publik). Private key bersifat rahasia dan hanya dimiliki oleh pengirim, sedangkan public key dapat diketahui oleh pihak lain untuk keperluan verifikasi.

Proses pembentukan digital signature diawali dengan melakukan hashing terhadap dokumen menggunakan fungsi hash kriptografis seperti SHA-256. Fungsi hash akan menghasilkan nilai ringkas (message digest) yang unik untuk setiap dokumen. Nilai hash tersebut kemudian dienkripsi menggunakan private key pengirim, sehingga terbentuklah digital signature.

## 3. Alat dan Bahan
- Python 3.11
- Visual Studio Code   
- Git dan akun GitHub

# 4. Langkah Percobaan
1. Membuat file `digital signature.py` di folder `praktikum/week9-Digital Signature/src/`.
2. Menyalin kode program dari panduan praktikum.
3. Menjalankan program dengan perintah `python digital signature.py`.
4. mengerjakan quis

## 5. Source Code
<img width="1397" height="1024" alt="Screenshot 2025-12-21 082727" src="https://github.com/user-attachments/assets/7ead5538-57d3-4b01-9d45-1cfea491e887" />

## 6. Hasil dan Pembahasan

<img width="1274" height="861" alt="Screenshot 2025-12-21 082642" src="https://github.com/user-attachments/assets/a00c214b-717b-4351-9445-ed1b845942e2" />

## 7. Jawaban Pertanyaan
1. Apa perbedaan utama antara enkripsi RSA dan tanda tangan digital RSA?
Perbedaan utama antara enkripsi RSA dan tanda tangan digital RSA terletak pada tujuan penggunaan dan arah penggunaan kunci. Enkripsi RSA digunakan untuk menjaga kerahasiaan pesan, di mana pesan dienkripsi menggunakan public key penerima dan hanya dapat didekripsi menggunakan private key penerima. Dengan demikian, hanya pihak yang memiliki private key yang dapat membaca isi pesan.Sebaliknya, tanda tangan digital RSA digunakan untuk menjamin keaslian dan keutuhan pesan, bukan untuk menyembunyikan isi pesan. Pada tanda tangan digital RSA, pengirim membuat tanda tangan dengan mengenkripsi nilai hash pesan menggunakan private key pengirim. Tanda tangan ini kemudian diverifikasi oleh penerima menggunakan public key pengirim. Jadi, fokus utama tanda tangan digital bukan pada kerahasiaan, melainkan pada validitas dan keaslian pesan.
2. Mengapa tanda tangan digital menjamin integritas dan otentikasi pesan?
Tanda tangan digital menjamin integritas pesan karena prosesnya melibatkan fungsi hash kriptografis. Setiap perubahan sekecil apa pun pada pesan akan menghasilkan nilai hash yang berbeda. Saat penerima membandingkan hash hasil verifikasi tanda tangan dengan hash pesan yang diterima, perbedaan nilai hash menunjukkan bahwa pesan telah diubah.Selain itu, tanda tangan digital menjamin otentikasi karena tanda tangan dibuat menggunakan private key pengirim yang bersifat rahasia dan unik. Jika tanda tangan dapat diverifikasi menggunakan public key pengirim, maka dapat dipastikan bahwa pesan benar-benar berasal dari pemilik kunci tersebut. Dengan demikian, tanda tangan digital memastikan bahwa pesan tidak hanya utuh, tetapi juga berasal dari sumber yang sah.
3. Bagaimana peran Certificate Authority (CA) dalam sistem tanda tangan digital modern?
Certificate Authority (CA) berperan sebagai pihak ketiga terpercaya yang menjamin keterkaitan antara identitas seseorang atau organisasi dengan public key yang digunakan dalam tanda tangan digital. CA menerbitkan sertifikat digital yang berisi informasi identitas pemilik, public key, masa berlaku, serta tanda tangan digital CA itu sendiri.Dalam sistem tanda tangan digital modern, CA memastikan bahwa public key yang digunakan untuk verifikasi benar-benar milik pihak yang mengklaimnya, sehingga mencegah serangan penyamaran (impersonation). Saat sebuah tanda tangan digital diverifikasi, sistem juga akan memeriksa validitas sertifikat digital yang dikeluarkan oleh CA. Dengan adanya CA, kepercayaan dalam komunikasi dan transaksi digital dapat terjaga secara luas dan aman.

## 8. Kesimpulan
Digital signature merupakan mekanisme keamanan berbasis kriptografi kunci publik yang berfungsi untuk menjamin keaslian, keutuhan, dan nirpenyangkalan suatu pesan atau dokumen digital. Dengan memanfaatkan fungsi hash dan penggunaan private key serta public key, digital signature mampu memastikan bahwa data tidak mengalami perubahan dan benar-benar berasal dari pihak yang sah. Selain itu, dukungan Certificate Authority (CA) dalam penerbitan sertifikat digital memperkuat kepercayaan terhadap identitas pemilik kunci, sehingga digital signature menjadi komponen penting dalam sistem keamanan dan transaksi elektronik modern.
## 9. Daftar Pustaka

## 10. Commit Log
commit week9-digital-signature
Author: Lesmana Desi <lesmanadesi1919@gmail.com>
Date:   2025-12-21
