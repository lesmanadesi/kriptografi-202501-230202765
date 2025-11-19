# Laporan Praktikum Kriptografi
Minggu ke-: 4
Topik: entropy_unicity
Nama: Lesmana Desi  
NIM: 230202765
Kelas: 5 IKRB

## 1. Tujuan
1. Menyelesaikan perhitungan sederhana terkait entropi kunci.
2. Menggunakan teorema Euler pada contoh perhitungan modular & invers.
3. Menghitung unicity distance untuk ciphertext tertentu.
4. Menganalisis kekuatan kunci berdasarkan entropi dan unicity distance.
5. Mengevaluasi potensi serangan brute force pada kriptosistem sederhana.

---

## 2. Dasar Teori
- Entropi kunci merupakan ukuran yang menggambarkan tingkat keacakan atau ketidakpastian dalam suatu sistem. Dalam konteks termodinamika, entropi berkaitan dengan seberapa luas energi dalam suatu sistem tersebar dan seberapa tinggi tingkat ketidakteraturannya. Nilai entropi yang semakin besar menunjukkan bahwa sistem tersebut semakin tidak teratur dan energinya semakin sulit dimanfaatkan secara efisien. Berdasarkan Hukum Kedua Termodinamika, entropi dalam sistem tertutup akan selalu cenderung meningkat seiring waktu, yang berarti bahwa proses alami akan bergerak menuju keadaan yang lebih acak atau tidak teratur. Selain itu, entropi juga dapat dipahami sebagai ukuran dari energi yang tidak dapat digunakan untuk melakukan kerja yang bermanfaat. Dengan demikian, entropi memberikan gambaran tentang seberapa besar tingkat ketidakteraturan suatu sistem sekaligus menunjukkan keterbatasan energi yang tersedia untuk digunakan secara efektif.
---

## 3. Alat dan Bahan
(- Python 3.x  
- Visual Studio Code 
- Git dan akun GitHub  
- google gemini

---

## 4. Langkah Percobaan
1.Membuat file entropy_unicity.py di folder praktikum/week3_entropy_unicity/src/.
2.Menyalin kode program dari panduan praktikum.
- Langkah 1 — Perhitungan Entropi Gunakan rumus:
[ H(K) = \log_2 |K| ]
dengan (|K|) adalah ukuran ruang kunci.
- Langkah 2 — Menghitung Unicity Distance Gunakan rumus:
[ U = \frac{H(K)}{R \cdot \log_2 |A|} ]
dengan:
(H(K)): entropi kunci,
(R): redundansi bahasa (misal bahasa Inggris (R \approx 0.75)),
(|A|): ukuran alfabet (26 untuk A–Z). 6.
- Langkah 3 — Analisis Brute Force Simulasikan waktu brute force dengan asumsi kecepatan komputer tertentu.
Menjalankan program dengan perintah python entropy_unicity.py.)
---

## 5. Source Code
import math

def entropy(keyspace_size):
    return math.log2(keyspace_size)

print("Entropy ruang kunci 26 =", entropy(26), "bit")
print("Entropy ruang kunci 2^128 =", entropy(2**128), "bit")

def unicity_distance(HK, R=0.75, A=26):
    return HK / (R * math.log2(A))

HK = entropy(26)
print("Unicity Distance untuk Caesar Cipher =", unicity_distance(HK))

def brute_force_time(keyspace_size, attempts_per_second=1e6):
    seconds = keyspace_size / attempts_per_second
    days = seconds / (3600*24)
    return days

print("Waktu brute force Caesar Cipher (26 kunci) =", brute_force_time(26), "hari")
print("Waktu brute force AES-128 =", brute_force_time(2**128), "hari")


## 6. Hasil dan Pembahasan
Hasil:
<img width="1919" height="1079" alt="Screenshot 2025-11-19 172914" src="https://github.com/user-attachments/assets/6349875f-77f2-4e32-8734-b069d1655844" />



Pembahasan:
Berdasarkan hasil perhitungan pada program, dapat dilihat bahwa algoritma Caesar Cipher memiliki tingkat keamanan yang sangat rendah. Hal ini ditunjukkan oleh nilai entropinya yang hanya sekitar 4,7 bit, yang berarti ruang kuncinya sangat kecil dan mudah ditebak. Unicity distance Caesar Cipher juga hanya sekitar 1,33, sehingga cipher ini dapat dengan mudah dipecahkan menggunakan sedikit ciphertext, terutama bila terdapat pola bahasa yang berulang. Perhitungan waktu brute force menunjukkan bahwa seluruh kemungkinan kunci Caesar Cipher dapat diuji hampir secara instan, yaitu hanya sekitar 3×10⁻¹⁰ hari atau kurang dari satu detik. Kondisi ini menegaskan bahwa Caesar Cipher tidak layak digunakan sebagai mekanisme keamanan modern.
Sebaliknya, AES-128 menunjukkan tingkat keamanan yang sangat tinggi dengan entropi sebesar 128 bit, menandakan ruang kuncinya yang sangat besar. Waktu brute force yang diperlukan untuk mencoba seluruh kemungkinan kunci AES-128 mencapai 3,9×10²⁷ hari, jumlah waktu yang tidak mungkin dicapai meskipun dengan superkomputer paling kuat sekalipun. Perbandingan ini menunjukkan perbedaan yang sangat signifikan antara cipher klasik seperti Caesar Cipher dan cipher modern seperti AES, di mana AES-128 terbukti sangat aman terhadap serangan brute force maupun analisis kriptografi lainnya.

---

## 7. Jawaban Pertanyaan
1. Apa arti dari nilai entropy dalam konteks kekuatan kunci?
    jawab:Entropi dalam konteks kekuatan kunci adalah ukuran derajat keacakan dan ketidakpastian dari suatu kunci atau password. Nilai entropi diukur dalam satuan bit.Semakin tinggi nilai entropi suatu kunci, semakin kuat dan aman kunci tersebut.

2. Mengapa unicity distance penting dalam menentukan keamanan suatu cipher?
   jawab: Unicity Distance ($U$) adalah jumlah minimum ciphertext (teks tersandi) yang diperlukan agar kunci dekripsi yang benar menjadi unik secara statistik di mata         penyerang.Unicity Distance menentukan seberapa cepat cipher tersebut dapat dipecahkan menggunakan analisis linguistik (memanfaatkan redundansi bahasa) tanpa harus mencoba semua kunci.

3. Mengapa brute force masih menjadi ancaman meskipun algoritma sudah kuat?
   jawab: Serangan brute force adalah upaya sistematis untuk mencoba setiap kemungkinan kunci hingga kunci yang benar ditemukan. Serangan ini tetap menjadi ancaman karena dua alasan utama:

1. Peningkatan Kekuatan Komputasi: Hukum Moore dan kemajuan dalam komputasi paralel, terutama dengan GPU dan komputasi terdistribusi, secara konstan meningkatkan kecepatan hashing dan percobaan kunci. Apa yang sulit dipecahkan sepuluh tahun lalu mungkin menjadi mungkin hari ini.

2. Kelemahan Implementasi (Kunci Pendek/Lemah): Meskipun algoritma (misalnya AES) itu sendiri kuat, keamanan selalu tergantung pada kunci terlemah.

- Jika pengguna memilih kunci yang pendek (misalnya, hanya 40 bit) atau tidak acak (misalnya, password yang umum), entropi kunci menjadi rendah.

- Ketika entropi kunci rendah, ruang kunci menjadi kecil, dan waktu yang dibutuhkan untuk serangan brute force menjadi sangat singkat, membuat cipher tersebut rentan meskipun menggunakan algoritma terkuat.

## 8. Kesimpulan
Penggunaan kriptografi klasik seperti caesar cipher sudah sangat usang, terbukti dari entropy kunci yang sangat rendah sehingga sangat rentan terhadap serangan brute force dan ananlisis frekuensi. Sedangkan penggunaan kriptografi modern seperti AES-128 dengan keamanan entropy 128 bit membuat pemecahan kunci secara komputasi menjadi mustahil, meskipun ancaman brute force tetap ada dengan menyerang penggunaan kombinasi password yang lemah.2–3 kalimat) berdasarkan percobaan.  )

---

## 9. Daftar Pustaka 
Katz, J., & Lindell, Y. (2020). Introduction to Modern Cryptography (3rd ed.). CRC Press.
Stallings, W. (2017). Cryptography and Network Security: Principles and Practice (7th ed.). Pearson Education.
Schneier, B. (2015). Applied Cryptography: Protocols, Algorithms, and Source Code in C (20th Anniversary ed.). John Wiley & Sons.
Shannon, C. E. (1949). Communication Theory of Secrecy Systems. Bell System Technical Journal, 28(4), 656–715.
## 10. Commit Log
week4-entrophy-unicity
Author: lesmana desi <lesmanadesi1919@gmail.com>
Date:   2025-11-04

    week4-entrophy-unicity: entrophy-unicity distance
```
