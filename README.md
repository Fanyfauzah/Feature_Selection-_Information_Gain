
---

# Feature Selection dengan Information Gain

Proyek ini mengimplementasikan algoritma Feature Selection menggunakan metode Information Gain pada dataset keputusan membeli laptop. Proyek ini dibangun sepenuhnya menggunakan Python murni tanpa library eksternal (scikit-learn, pandas, dll.) untuk memberikan pemahaman mendalam tentang logika di balik algoritma Decision Tree.

## Deskripsi Proyek

Tujuan utama proyek ini adalah menentukan fitur mana yang paling berpengaruh dalam memprediksi label Beli_Laptop. Dengan menghitung nilai Entropy dan Information Gain dari setiap fitur, model dapat mengidentifikasi fitur terbaik yang akan digunakan sebagai Root Node dalam pembuatan Decision Tree.

Dataset Overview:

* Total Data: 14 baris.
* Fitur: Penghasilan, Usia_Kategori, Status_Pekerjaan, Punya_Tabungan.
* Label: Beli_Laptop (2 kelas: Ya/Tidak).

## Hasil Analisis (Ranking Fitur)

Berdasarkan perhitungan Information Gain (IG), berikut adalah urutan fitur dari yang paling informatif hingga yang paling tidak informatif:

1. Rank 1 (Root Node): Usia_Kategori (IG: 0.403873)
2. Rank 2: Punya_Tabungan (IG: 0.236122)
3. Rank 3: Penghasilan (IG: 0.103893)
4. Rank 4: Status_Pekerjaan (IG: 0.016112)

Analisis: Fitur Usia_Kategori terpilih sebagai fitur terbaik karena menghasilkan pemisahan subset yang paling murni, terutama pada kelompok "Menengah" yang memiliki nilai entropy 0.0.

## Implementasi Teknis

Proyek ini terdiri dari modul logika inti sebagai berikut:

* hitung_entropy(data): Menghitung ketidakmurnian data (H(S)) menggunakan rumus: H(S) = - SUM [ p(c) * log2(p(c)) ]
* hitung_information_gain(data, indeks_fitur): Menghitung pengurangan entropy setelah dataset dibagi berdasarkan fitur tertentu dengan rumus: IG(S, A) = H(S) - SUM [ (|Sv| / |S|) * H(Sv) ]
* feature_selection(data, fitur): Melakukan pemeringkatan fitur secara otomatis berdasarkan nilai IG tertinggi.

## Cara Menjalankan

1. Pastikan Anda memiliki file dataset_laptop.csv di direktori yang sama.
2. Jalankan notebook information_gain_feature_selection.ipynb menggunakan Jupyter Notebook atau Google Colab.
3. Fungsi jalankan_feature_selection('dataset_laptop.csv') akan memproses data dan menampilkan laporan lengkap secara otomatis.

## Kesimpulan

Dengan nilai Information Gain tertinggi sebesar 0.403873, Usia_Kategori adalah fitur yang paling krusial untuk memisahkan data dalam memprediksi keputusan pembelian laptop. Fitur Status_Pekerjaan memberikan kontribusi paling sedikit, sehingga dapat dipertimbangkan untuk diabaikan dalam penyederhanaan model Decision Tree.
