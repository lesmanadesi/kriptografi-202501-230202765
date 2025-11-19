# Laporan Praktikum Kriptografi
Minggu ke-: 5
Topik:[ cipher klasik ]
Nama:[Lesmana desi]
NIM:[ 230202765]
Kelas:[ 5IKRB]

# 1. Tujuan
Menerapkan algoritma Caesar Cipher untuk enkripsi dan dekripsi teks.
Menerapkan algoritma Vigenère Cipher dengan variasi kunci.
Mengimplementasikan algoritma transposisi sederhana.
Menjelaskan kelemahan algoritma kriptografi klasik dalam konteks keamanan modern.

---
# 2. Dasar Teori
Cipher klasik merupakan bentuk awal dari teknik kriptografi yang digunakan sebelum hadirnya komputer modern. Sistem ini bekerja dengan mengubah plaintext menjadi ciphertext melalui operasi sederhana seperti substitusi dan transposisi. Pada metode substitusi, setiap huruf pada plaintext diganti dengan huruf lain sesuai aturan tertentu, seperti pada Caesar Cipher atau Vigenère Cipher. Sementara itu, metode transposisi tidak mengganti huruf tetapi menata ulang posisi huruf berdasarkan pola tertentu, misalnya pada Rail Fence Cipher. Meskipun metode-metode ini efektif pada masa lalu, cipher klasik memiliki kelemahan mendasar karena ruang kuncinya kecil dan masih mempertahankan pola bahasa alami, sehingga mudah dipecahkan menggunakan analisis frekuensi maupun brute force. Oleh karena itu, cipher klasik hanya digunakan sebagai bahan pembelajaran kriptografi, karena tidak dapat memenuhi standar keamanan modern.

---
# 3.. Alat dan Bahan
(- Python 3.x

Visual Studio Code / editor lain
Git dan akun GitHub
Library tambahan (misalnya pycryptodome, jika diperlukan) )

---
# 4. Langkah Percobaan
(Tuliskan langkah yang dilakukan sesuai instruksi.
Contoh format:

Membuat file caesar_cipher.py di folder praktikum/week5-cryptosystem/src/.
Menyalin kode program dari panduan praktikum.
Menjalankan program dengan perintah python caesar_cipher.py.)

---
# 5. Source Code
langkah 1 def caesar_encrypt(plaintext, key): result = "" for char in plaintext: if char.isalpha(): shift = 65 if char.isupper() else 97 result += chr((ord(char) - shift + key) % 26 + shift) else: result += char return result

def caesar_decrypt(ciphertext, key): return caesar_encrypt(ciphertext, -key)

Contoh uji
msg = "CLASSIC CIPHER" key = 3 enc = caesar_encrypt(msg, key) dec = caesar_decrypt(enc, key) print("Plaintext :", msg) print("Ciphertext:", enc) print("Decrypted :", dec)

langkah 2: def vigenere_encrypt(plaintext, key): result = [] key = key.lower() key_index = 0 for char in plaintext: if char.isalpha(): shift = ord(key[key_index % len(key)]) - 97 base = 65 if char.isupper() else 97 result.append(chr((ord(char) - base + shift) % 26 + base)) key_index += 1 else: result.append(char) return "".join(result)

def vigenere_decrypt(ciphertext, key): result = [] key = key.lower() key_index = 0 for char in ciphertext: if char.isalpha(): shift = ord(key[key_index % len(key)]) - 97 base = 65 if char.isupper() else 97 result.append(chr((ord(char) - base - shift) % 26 + base)) key_index += 1 else: result.append(char) return "".join(result)

Contoh uji
msg = "KRIPTOGRAFI" key = "KEY" enc = vigenere_encrypt(msg, key) dec = vigenere_decrypt(enc, key) print("Plaintext :", msg) print("Ciphertext:", enc) print("Decrypted :", dec)

langkah 3: def transpose_encrypt(plaintext, key=5): ciphertext = [''] * key for col in range(key): pointer = col while pointer < len(plaintext): ciphertext[col] += plaintext[pointer] pointer += key return ''.join(ciphertext)

def transpose_decrypt(ciphertext, key=5): num_of_cols = int(len(ciphertext) / key + 0.9999) num_of_rows = key num_of_shaded_boxes = (num_of_cols * num_of_rows) - len(ciphertext) plaintext = [''] * num_of_cols col = 0 row = 0 for symbol in ciphertext: plaintext[col] += symbol col += 1 if (col == num_of_cols) or (col == num_of_cols - 1 and row >= num_of_rows - num_of_shaded_boxes): col = 0 row += 1 return ''.join(plaintext)

Contoh uji
msg = "TRANSPOSITIONCIPHER" enc = transpose_encrypt(msg, key=5) dec = transpose_decrypt(enc, key=5) print("Plaintext :", msg) print("Ciphertext:", enc) print("Decrypted :", dec)

# 6. Hasil dan Pembahasan
hasil :
<img width="1814" height="879" alt="Screenshot 2025-11-19 175207" src="https://github.com/user-attachments/assets/6a3daf4b-6ab7-4c01-b434-f410bc7637b7" />
<img width="1875" height="950" alt="Screenshot 2025-11-19 175129" src="https://github.com/user-attachments/assets/ee850d37-b261-4af8-9ffa-3ec2843a0d6a" />
<img width="1829" height="956" alt="Screenshot 2025-11-19 175247" src="https://github.com/user-attachments/assets/39b171f4-7bcd-4242-8ab4-e2fbdbc28aba" />
pembahasan :
Berdasarkan hasil pengujian program, ketiga algoritma kriptografi klasik yaitu Caesar Cipher, Vigenere Cipher, dan Transposition Cipher berhasil dijalankan dengan baik untuk proses enkripsi dan dekripsi. Pada Caesar Cipher, teks “CLASSIC CIPHER” dienkripsi menggunakan pergeseran kunci sebesar 3 dan menghasilkan ciphertext “FDOVVLF FLSKHU”. Ketika dilakukan proses dekripsi, ciphertext tersebut kembali ke plaintext semula tanpa perubahan, menunjukkan bahwa fungsi enkripsi dan dekripsi bekerja dengan benar. Caesar Cipher dikenal sebagai algoritma yang paling sederhana, karena hanya melakukan pergeseran huruf, sehingga mudah dipahami namun juga mudah dipecahkan.
Selanjutnya, algoritma Vigenere Cipher diuji menggunakan plaintext “KRIPTOGRAFI” dan kunci “KEY”. Proses enkripsi menghasilkan ciphertext “UVGZXMQYVPM”, sedangkan proses dekripsi berhasil mengembalikan ciphertext tersebut ke bentuk awal yaitu “KRIPTOGRAFI”. Hasil ini menunjukkan bahwa implementasi Vigenere Cipher sudah sesuai dengan konsep dasarnya, yaitu penggunaan kunci berulang yang memberikan keamanan lebih baik daripada Caesar Cipher karena pergeseran huruf tidak seragam, melainkan bergantung pada karakter kunci.
Pada pengujian Transposition Cipher, plaintext “TRANSPOSITIONCIPHER” diproses menggunakan kunci 5 dan menghasilkan ciphertext “TPIPROOHA5NENICRSTI”. Ciphertext tersebut dapat didekripsi kembali dengan tepat sehingga menghasilkan plaintext asli. Transposition Cipher bekerja dengan cara memindahkan posisi karakter tanpa mengubah bentuk huruf, sehingga menghasilkan pola ciphertext yang berbeda dari metode substitusi seperti Caesar dan Vigenere. Algoritma ini memiliki struktur yang lebih sulit ditebak karena urutan karakter diacak secara sistematis berdasarkan jumlah kolom atau kunci yang digunakan.
Secara keseluruhan, ketiga algoritma terbukti berjalan dengan benar sesuai konsep dasar kriptografi klasik. Meskipun demikian, dari sisi keamanan, metode-metode ini relatif mudah dipecahkan dengan teknik kriptanalisis modern. Caesar Cipher paling mudah dibobol, diikuti oleh Vigenere, sementara Transposition Cipher memiliki pola lebih kompleks namun tetap tidak cukup aman untuk standar kriptografi modern. Namun demikian, ketiga algoritma ini sangat baik digunakan untuk memahami konsep dasar enkripsi dan dekripsi sebelum mempelajari algoritma modern seperti AES.
7. Jawaban Pertanyaan
1. Apa kelemahan utama algoritma Caesar Cipher dan Vigenère Cipher? Caesar Cipher memiliki ruang kunci yang sangat kecil (hanya 25 kemungkinan), sehingga mudah dipecahkan dengan brute-force. Vigenère Cipher lebih kuat, tetapi tetap rentan terhadap frequency analysis dan Kasiski examination jika kuncinya pendek atau berulang.

2. Mengapa cipher klasik mudah diserang dengan analisis frekuensi? Karena cipher klasik tidak mengubah frekuensi kemunculan huruf secara signifikan. Pola distribusi huruf dalam bahasa alami tetap bisa dikenali, sehingga analis dapat menebak substitusi yang digunakan.

3. Bandingkan kelebihan dan kelemahan cipher substitusi vs transposisi. Substitusi Cipher: Mengganti huruf, tetapi mempertahankan urutan. Lebih mudah diimplementasikan, namun pola frekuensi tetap terlihat. Transposisi Cipher: Menyusun ulang urutan huruf tanpa mengganti karakter. Lebih sulit dipecahkan dengan analisis frekuensi, tetapi masih bisa direkonstruksi dengan serangan posisi karakter.
   
# 8. Kesimpulan
Berdasarkan percobaan yang dilakukan, dapat diketahui bahwa cipher klasik hanya mampu memberikan perlindungan yang sangat dasar karena metode enkripsinya masih sederhana dan mudah diprediksi. Baik Caesar Cipher maupun Vigenère Cipher menunjukkan bahwa pola bahasa pada plaintext masih terlihat dalam ciphertext, sehingga analisis frekuensi dapat digunakan untuk memecahkannya dengan relatif cepat. Hal ini membuktikan bahwa teknik penyandian tradisional tidak memiliki kekuatan keamanan yang memadai untuk kebutuhan komunikasi digital masa kini. Meskipun demikian, cipher klasik tetap memiliki nilai penting sebagai sarana untuk memahami prinsip-prinsip dasar enkripsi yang menjadi landasan berkembangnya kriptografi modern.

---
# 10. Daftar Pustaka
Stallings, William. Cryptography and Network Security: Principles and Practice. Pearson Education, 2017.
Katz, Jonathan & Lindell, Yehuda. Introduction to Modern Cryptography. CRC Press, 2020.
Singh, Simon. The Code Book: The Science of Secrecy from Ancient Egypt to Quantum Cryptography. Anchor Books, 1999.

---
# 11. Commit Log
(Tuliskan bukti commit Git yang relevan.
Contoh:
Author: lesmana desi <lesmanadesi1919@gmail.com>
Date:   2025-19-11

---
    
