# Laporan Praktikum Kriptografi
Minggu ke-: X  
Topik : secret-sharing
Nama: Lesmana Desi
NIM: 230202765 
Kelas: 5ikrb

---

## 1. Tujuan
Setelah mengikuti praktikum ini, mahasiswa diharapkan mampu:

Menjelaskan konsep Shamir Secret Sharing (SSS).
Melakukan simulasi pembagian rahasia ke beberapa pihak menggunakan skema SSS.
Menganalisis keamanan skema distribusi rahasia.

---

## 2. Dasar Teori
Secret Sharing merupakan teknik kriptografi yang digunakan untuk membagi suatu rahasia menjadi beberapa bagian yang disebut share, sehingga rahasia tersebut hanya dapat direkonstruksi apabila sejumlah share tertentu digabungkan. Tujuan utama dari secret sharing adalah meningkatkan keamanan dan keandalan penyimpanan rahasia dengan menghindari ketergantungan pada satu pihak atau satu lokasi penyimpanan.
Salah satu skema secret sharing yang paling terkenal adalah Shamir Secret Sharing (SSS) yang diperkenalkan oleh Adi Shamir pada tahun 1979. Skema ini menggunakan konsep matematika berupa polinomial berderajat Keunggulan utama secret sharing adalah kemampuannya memberikan keamanan informasi secara sempurna (information-theoretic security), karena kepemilikan share yang jumlahnya kurang dari threshold tidak memberikan informasi apa pun mengenai rahasia. Selain itu, secret sharing juga meningkatkan ketersediaan dan toleransi kesalahan, karena rahasia tetap dapat dipulihkan meskipun sebagian share hilang atau tidak tersedia.
Secret sharing banyak diterapkan dalam berbagai bidang, seperti manajemen kunci kriptografi, sistem keamanan terdistribusi, penyimpanan data sensitif, pemulihan akses (recovery), serta pengelolaan kunci pada sistem cryptocurrency dan infrastruktur keamanan modern.

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
<img width="1473" height="1047" alt="Screenshot 2025-12-21 085943" src="https://github.com/user-attachments/assets/bcc31720-a041-4231-a571-7364cca66cca" />
<img width="1505" height="1030" alt="Screenshot 2025-12-21 090630" src="https://github.com/user-attachments/assets/04832777-7589-4700-8ff1-d24250090197" />


## 6. Hasil dan Pembahasan
Hasil eksekusi program Caesar Cipher:
<img width="1470" height="597" alt="Screenshot 2025-12-21 085954" src="https://github.com/user-attachments/assets/182d8c9f-fef7-49ae-978b-3581731ddaaf" />
<img width="1486" height="271" alt="Screenshot 2025-12-21 090611" src="https://github.com/user-attachments/assets/a5edb4c9-d35a-4afb-9f5e-ff52c51b1b31" />
Skema (𝑘,𝑛) pada Shamir Secret Sharing tetap aman meskipun sebagian share bocor karena secara matematis, kepemilikan share yang jumlahnya kurang dari threshold k tidak memberikan informasi apa pun mengenai rahasia. Dengan kurang dari k titik, terdapat banyak kemungkinan polinomial yang dapat dibentuk, sehingga nilai rahasia tidak dapat ditentukan. Hal ini memberikan jaminan keamanan yang kuat secara teori, yang dikenal sebagai information-theoretic security.
Pemilihan nilai threshold 𝑘 memiliki pengaruh besar terhadap keamanan dan ketersediaan sistem. Jika nilai 𝑘 terlalu kecil, maka tingkat keamanan menjadi rendah karena penyerang hanya membutuhkan sedikit share untuk merekonstruksi rahasia. Sebaliknya, jika nilai 𝑘 terlalu besar, sistem menjadi kurang fleksibel karena kehilangan beberapa share saja dapat menyebabkan rahasia tidak dapat dipulihkan, sehingga menurunkan tingkat ketersediaan. Oleh karena itu, pemilihan nilai 𝑘k harus mempertimbangkan keseimbangan antara keamanan dan kemudahan pemulihan data.Dalam penerapannya di dunia nyata, Shamir Secret Sharing banyak digunakan dalam manajemen kunci cryptocurrency untuk membagi private key ke beberapa pihak agar tidak terjadi single point of failure. Selain itu, skema ini juga digunakan dalam sistem pemulihan kata sandi (password recovery), penyimpanan kunci kriptografi perusahaan, serta sistem keamanan terdistribusi lainnya. Dengan penerapan SSS, risiko kehilangan atau pencurian rahasia dapat diminimalkan secara signifikan.


)

---

## 7. Jawaban Pertanyaan
1.Keuntungan utama Shamir Secret Sharing dibandingkan membagikan salinan kunci secara langsung adalah tidak adanya single point of failure. Pada SSS, rahasia tidak pernah disimpan atau dibagikan secara utuh ke satu pihak. Meskipun beberapa share bocor atau dicuri, rahasia tetap aman selama jumlah share tersebut kurang dari threshold yang ditentukan.

2.Peran threshold (k) dalam keamanan secret sharing adalah sebagai batas minimum jumlah share yang dibutuhkan untuk merekonstruksi rahasia. Nilai k menentukan tingkat keamanan dan ketersediaan sistem: semakin besar 𝑘, semakin sulit bagi penyerang untuk memperoleh rahasia, namun semakin tinggi pula risiko rahasia tidak dapat dipulihkan jika terlalu banyak share hilang.
3.Contoh skenario nyata penerapan SSS adalah pada manajemen kunci cryptocurrency. Private key dompet digital dibagi ke beberapa pihak atau perangkat, sehingga transaksi hanya dapat dilakukan jika minimal sejumlah pemilik share menyetujui. Hal ini meningkatkan keamanan dan mencegah kehilangan aset akibat pencurian atau kerusakan satu kunci saja.

---

## 8. Kesimpulan
Shamir Secret Sharing memungkinkan pembagian rahasia secara aman tanpa menyimpan kunci secara utuh pada satu pihak. Dengan adanya threshold, rahasia hanya dapat direkonstruksi oleh pihak yang berwenang, sehingga keamanan dan keandalan sistem meningkat serta risiko kebocoran atau kehilangan kunci dapat diminimalkan.

---

## 9. Daftar Pustaka

## 10. Commit Log
(Tuliskan bukti commit Git yang relevan.  
Contoh:
```
commit abc12345
Author: Lesmana Desi<lesmanadesi1919@gmail.com>
Date:   2025-12-21

    week2-cryptosystem: implementasi Caesar Cipher dan laporan )
```
