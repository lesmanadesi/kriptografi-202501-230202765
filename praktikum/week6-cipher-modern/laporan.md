# Laporan Praktikum Kriptografi
Minggu ke-: VI
Topik: Chiper Modern(DES, AES, RSA)
Nama: Lesmana desi
NIM: 230202765
Kelas: 5IKRB

# 1. Tujuan
Mengimplementasikan algoritma DES untuk blok data sederhana.
Menerapkan algoritma AES dengan panjang kunci 128 bit.
Menjelaskan proses pembangkitan kunci publik dan privat pada algoritma RSA.
# 2. Dasar Teori
Cipher modern merupakan teknik kriptografi yang dikembangkan untuk memenuhi kebutuhan keamanan informasi di era digital, di mana data harus terlindungi dari serangan yang semakin kompleks. Berbeda dengan cipher klasik yang hanya mengandalkan operasi sederhana seperti pergeseran huruf dan pengacakan posisi karakter, cipher modern menggunakan prinsip matematika yang kuat, struktur algoritma yang kompleks, serta ukuran kunci yang sangat besar sehingga sulit diretas dengan brute force maupun analisis kriptografis. Cipher modern terbagi menjadi dua kategori utama, yaitu block cipher dan stream cipher. Block cipher, seperti AES (Advanced Encryption Standard), bekerja dengan membagi plaintext menjadi blok-blok data berukuran tetap, kemudian mengaplikasikan serangkaian operasi substitusi, permutasi, dan transformasi matematis menggunakan kunci rahasia. Operasi ini dilakukan dalam beberapa putaran (rounds) untuk memastikan difusi dan konfusi yang kuat sesuai prinsip Claude Shannon. Sementara itu, stream cipher seperti RC4 menghasilkan aliran bit kunci semu (keystream) yang kemudian di-xor dengan data secara berurutan, sehingga cocok untuk komunikasi yang membutuhkan kecepatan tinggi.
Cipher modern juga dirancang agar tahan terhadap berbagai jenis serangan seperti differential cryptanalysis, linear cryptanalysis, maupun serangan waktu (timing attack). Selain itu, algoritma modern menggunakan kunci dengan panjang minimal 128 bit, sehingga jumlah kemungkinan kunci mencapai angka astronomis dan tidak dapat ditembus oleh brute force. Kriptografi modern juga memanfaatkan fungsi hash, mode operasi (CBC, CTR, GCM), serta teknik randomisasi untuk memperkuat keamanan data. Dengan kombinasi struktur matematis yang kuat dan standar keamanan internasional, cipher modern menjadi fondasi utama dalam melindungi data pada aplikasi perbankan, komunikasi internet, transaksi digital, hingga sistem keamanan global.
# 3. Alat dan Bahan
Python 3.11
Visual Studio Code
Git dan akun GitHub
# 4. Langkah Percobaan
Membuat file aes.py rsa.py des.py di folder praktikum/week6-cipher-modern/src/.
Menyalin kode program dari panduan praktikum.
Menjalankan kode program.
5. Source Code
from Crypto.Cipher import DES
from Crypto.Random import get_random_bytes

key = get_random_bytes(8)  # kunci 64 bit (8 byte)
cipher = DES.new(key, DES.MODE_ECB)

plaintext = b"ABCDEFGH"
ciphertext = cipher.encrypt(plaintext)
print("Ciphertext:", ciphertext)

decipher = DES.new(key, DES.MODE_ECB)
decrypted = decipher.decrypt(ciphertext)
print("Decrypted:", decrypted)

from Crypto.Cipher import AES
from Crypto.Random import get_random_bytes

key = get_random_bytes(16)  # 128 bit key
cipher = AES.new(key, AES.MODE_EAX)

plaintext = b"Modern Cipher AES Example"
ciphertext, tag = cipher.encrypt_and_digest(plaintext)

print("Ciphertext:", ciphertext)

from Crypto.PublicKey import RSA
from Crypto.Cipher import PKCS1_OAEP

# Generate key pair
key = RSA.generate(2048)
private_key = key
public_key = key.publickey()

# Enkripsi dengan public key
cipher_rsa = PKCS1_OAEP.new(public_key)
plaintext = b"RSA Example"
ciphertext = cipher_rsa.encrypt(plaintext)
print("Ciphertext:", ciphertext)

# Dekripsi dengan private key
decipher_rsa = PKCS1_OAEP.new(private_key)
decrypted = decipher_rsa.decrypt(ciphertext)
print("Decrypted:", decrypted.decode())

# Dekripsi
cipher_dec = AES.new(key, AES.MODE_EAX, nonce=cipher.nonce)
decrypted = cipher_dec.decrypt(ciphertext)
print("Decrypted:", decrypted.decode())
# 6. Hasil dan Pembahasan
<img width="1776" height="746" alt="Screenshot 2025-11-19 180224" src="https://github.com/user-attachments/assets/c0b532b8-0d3f-43d2-8d85-494fd49d23e3" />
<img width="1757" height="789" alt="Screenshot 2025-11-19 180502" src="https://github.com/user-attachments/assets/8faf55a7-9dc8-4fec-8ea2-ca032a7e21a8" />
<img width="1692" height="755" alt="Screenshot 2025-11-19 180607" src="https://github.com/user-attachments/assets/d2b90144-317b-4208-aaa9-c2c9688e52b9" />

# 7. Jawaban Pertanyaan
soal

Apa perbedaan mendasar antara DES, AES, dan RSA dalam hal kunci dan keamanan?
Mengapa AES lebih banyak digunakan dibanding DES di era modern?
Mengapa RSA dikategorikan sebagai algoritma asimetris, dan bagaimana proses pembangkitan kuncinya?
jawaban

Perbedaan utama antara DES, AES, dan RSA terletak pada jenis kunci dan keamanannya. DES dan AES adalah algoritma simetris yang memakai satu kunci untuk enkripsi dan dekripsi, sedangkan RSA adalah asimetris yang menggunakan dua kunci, yaitu publik dan privat. DES memakai kunci 56-bit yang kini dianggap lemah, sementara AES lebih kuat dengan panjang kunci 128, 192, atau 256-bit. RSA lebih sering digunakan untuk pertukaran kunci dan tanda tangan digital karena sifat asimetrisnya.

AES lebih banyak digunakan dibanding DES karena lebih aman, cepat, dan efisien. DES dengan kunci 56-bit mudah dipecahkan dengan brute force, sedangkan AES memiliki struktur yang lebih kompleks dan mendukung panjang kunci lebih besar. Selain itu, AES telah diakui sebagai standar enkripsi internasional (FIPS 197) oleh NIST, sehingga menjadi pilihan utama di berbagai sistem keamanan modern.

RSA disebut algoritma asimetris karena memakai dua kunci berbeda: publik untuk enkripsi dan privat untuk dekripsi. Kuncinya dibentuk dengan memilih dua bilangan prima besar, menghitung hasil kali dan totiennya, lalu menentukan nilai (publik) dan (privat) yang saling berhubungan secara matematis. Dengan cara ini, pesan hanya bisa dibuka oleh pemilik kunci privat yang sesuai.

# 8. Kesimpulan
Dari ketiga algoritma tersebut, dapat disimpulkan bahwa DES, AES, dan RSA memiliki perbedaan mendasar dalam cara kerja dan tingkat keamanannya. DES merupakan algoritma simetris generasi awal yang kini dianggap kurang aman karena panjang kuncinya hanya 56 bit. AES hadir sebagai penggantinya dengan struktur yang lebih kompleks, panjang kunci yang lebih besar, dan tingkat keamanan yang jauh lebih tinggi sehingga menjadi standar enkripsi modern. Sementara itu, RSA termasuk algoritma asimetris yang menggunakan dua kunci berbeda, yaitu publik dan privat, dan banyak digunakan dalam sistem keamanan digital seperti enkripsi kunci, tanda tangan digital, dan autentikasi. Dengan kombinasi penggunaan algoritma simetris dan asimetris, sistem keamanan data saat ini dapat mencapai efisiensi sekaligus perlindungan yang kuat terhadap ancaman siber.

9. Daftar Pustaka
# 10. Commit Log
commit abc12345 Author: lesmana desi (lesmanadesi1919@gmail.com) Date: 19-11-2025
