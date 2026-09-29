# Pertemuan 05 Perulangan Python

**Nama:** Amandita Pebriana Putri  
**NIM:** 2225250134  
**Kelas:** 3A Pendidikan Matematika  

## Tujuan
Menggunakan perulangan `for` dan `while` untuk menyelesaikan masalah iteratif, melakukan validasi input berulang, serta mengakumulasi nilai pada deret matematis.

## Cara Menjalankan
```bash
python kuis/kuis2_deret_aritmetika.py
```

## Algoritma Kuis 2
1. Membaca input nilai suku pertama (`a`) dan beda (`d`) bertipe desimal (`float`).
2. Membaca input banyak suku (`n`) bertipe bilangan bulat (`int`).
3. Memeriksa nilai `n` menggunakan perulangan `while n <= 0`. Jika pengguna memasukkan nilai `n` nol atau negatif, cetak pesan peringatan "n harus bilangan bulat positif." dan minta input `n` kembali hingga bernilai positif.
4. Menginisialisasi variabel akumulator `total = 0` sebelum perulangan.
5. Melakukan perulangan `for` dari `i = 0` sampai `n - 1` (sebanyak `n` kali):
   - Menghitung nilai suku ke-`(i + 1)` dengan rumus: `suku = a + i * d`.
   - Menambahkan nilai `suku` ke dalam variabel `total` (`total += suku`).
   - Menampilkan nomor suku dan nilainya dengan format 2 angka di belakang koma (`:.2f`).
6. Setelah perulangan `for` selesai, tampilkan jumlah akhir (`total`) seluruh suku dengan format 2 angka di belakang koma (`:.2f`).

## Hasil Pengujian (Test Case Wajib Kuis 2)

| Input `a` | Input `d` | Input `n` | Suku yang Dihasilkan | Jumlah (Expected) | Jumlah (Actual) | Status |
| :---: | :---: | :---: | :--- | :---: | :---: | :---: |
| 2 | 3 | 5 | 2.00, 5.00, 8.00, 11.00, 14.00 | 40.00 | 40.00 | Sesuai |
| 10 | -2 | 4 | 10.00, 8.00, 6.00, 4.00 | 28.00 | 28.00 | Sesuai |
| 1.5 | 0.5 | 3 | 1.50, 2.00, 2.50 | 6.00 | 6.00 | Sesuai |
| 2 | 3 | -2 -> 5 | (Input -2 ditolak, diminta ulang hingga n = 5) | 40.00 | 40.00 | Sesuai |

## Refleksi
Kesalahan umum yang sangat rawan terjadi pada perulangan adalah meletakkan inisialisasi akumulator `total = 0` di dalam badan perulangan (`loop`). Jika diletakkan di dalam `loop`, variabel `total` akan terus direset menjadi `0` di setiap iterasi sehingga hasil penjumlahan akhir menjadi salah. Solusinya adalah selalu meletakkan `total = 0` tepat sebelum perulangan `for` dimulai.

Selain itu, pemilihan jenis perulangan harus disesuaikan dengan kebutuhan masalah[cite: 3]. Perulangan `while` sangat tepat digunakan untuk validasi input `n` karena jumlah kesalahan input oleh pengguna tidak dapat diprediksi sejak awal[cite: 3]. Sedangkan perulangan `for` dipasangkan dengan `range(n)` sangat cocok untuk mencetak suku dan menghitung akumulasi total karena jumlah iterasinya sudah pasti sebanyak `n` kali[cite: 3].