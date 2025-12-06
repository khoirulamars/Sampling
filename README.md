# Analisis Estimasi Dampak Banjir DKI Jakarta 2020 🌊

Repository ini berisi *notebook* analisis statistik untuk mengestimasi rata-rata jumlah jiwa yang terdampak banjir per Kelurahan di Provinsi DKI Jakarta berdasarkan data tahun 2020.

## 📋 Ringkasan
Proyek ini melakukan proses *End-to-End* data analysis, mulai dari pengumpulan data mentah bulanan, pembersihan data (*data cleaning*), hingga penerapan metode statistik inferensial untuk menaksir parameter populasi.

**Tujuan:** Mengestimasi rata-rata jumlah korban terdampak banjir per kelurahan ($\mu_r$) dengan tingkat kepercayaan 95%.

## 📂 Dataset
Sumber data berasal dari Portal Data Terbuka Pemerintah Provinsi DKI Jakarta (**Jakarta Open Data**).
- **Periode:** Januari 2020 - Desember 2020.
- **Data:** Kejadian Bencana Banjir per Bulan.
- **Atribut:** Kota Administrasi, Kecamatan, Kelurahan, Jumlah Terdampak (RW, RT, KK, Jiwa), Ketinggian Air, dll.

## 🛠️ Teknologi & Libraries
Analisis dilakukan menggunakan **Python** dengan *library* berikut:
* `pandas`: Manipulasi dan agregasi data.
* `numpy`: Operasi numerik dan perhitungan varians.
* `scipy.stats`: Perhitungan Z-statistic untuk *Confidence Interval*.
* `re`: *Regular Expression* untuk pembersihan teks (nama bulan/kelurahan).

## 🧮 Metodologi Statistik
1.  **Preprocessing:** Penggabungan 12 file CSV bulanan, standarisasi penulisan nama wilayah, dan konversi tipe data.
2.  **Sampling Design:**
    * **Populasi ($N$):** 47 Kecamatan di DKI Jakarta.
    * **Sampel ($n$):** 10 Kecamatan dipilih secara acak (*Random Sampling*).
    * **Unit Estimasi:** Kelurahan.
3.  **Metode Estimasi:** Menggunakan *Ratio Estimator* ($\mu_r = \frac{y_{total}}{M}$) di mana $y$ adalah jumlah jiwa terdampak dan $M$ adalah jumlah kelurahan.

## 📊 Hasil Analisis
Berdasarkan sampel 10 kecamatan (termasuk Jatinegara, Makasar, Cincing, dll):

* **Rata-rata Sampel ($\mu_r$):** ~514 jiwa per kelurahan.
* **Margin of Error ($d$):** ±367 jiwa.
* **95% Confidence Interval:**
    > Kami memperkirakan dengan tingkat kepercayaan 95%, rata-rata jumlah jiwa yang terdampak banjir per kelurahan di DKI Jakarta berkisar antara **146 hingga 881 orang**.

## 🚀 Cara Menjalankan
1.  Pastikan Python dan Jupyter Notebook terinstal.
2.  Install dependencies: `pip install pandas numpy scipy`.
3.  Jalankan file `sampling.ipynb`.
    *(Catatan: Notebook akan mengunduh dataset langsung dari URL data.jakarta.go.id)*
