# Analisis Klaster Kepadatan Penduduk Kabupaten Kudus Menggunakan Metode Two-Step Cluster

## Ringkasan Proyek
Proyek ini menganalisis pola dan karakteristik kepadatan penduduk di tingkat desa/kelurahan di Kabupaten Kudus (tahun data: 2024). Sebagai kabupaten dengan luas wilayah relatif kecil namun berpenduduk padat di Jawa Tengah, pemahaman distribusi penduduk penting untuk mendukung perumusan kebijakan daerah.

Analisis menggunakan *unsupervised learning* **Two-Step Cluster** untuk mengelompokkan 132 desa/kelurahan berdasarkan 8 variabel demografis. Untuk mengatasi multikolinearitas antar-variabel, diterapkan **Principal Component Analysis (PCA)** sebagai tahap prapemrosesan guna mereduksi dimensi ke 2 komponen utama sebelum proses klastering.

Studi ini merupakan bagian dari kegiatan magang FMIPA Prigel di Badan Pusat Statistik (BPS) Kabupaten Kudus pada periode 1 September–30 November 2024.

## Dataset
- **Sumber data**: Publikasi resmi BPS Kabupaten Kudus, khususnya *Kecamatan dalam Angka 2024*.
- **Unit analisis**: 132 desa/kelurahan.
- **Variabel (8)**:
  1) Jumlah Penduduk  
  2) Jumlah Laki-laki  
  3) Jumlah Perempuan  
  4) Jumlah Kelahiran  
  5) Jumlah Kematian  
  6) Kepadatan Penduduk (per km²)  
  7) Jumlah Kedatangan  
  8) Jumlah Kepindahan



## Metodologi
Kerangka kerja mengikuti tahapan **KDD (Knowledge Discovery in Databases)**:

1. **Preprocessing Data**
   - Memastikan tidak ada *missing value* dan duplikasi catatan.
   - *Outlier* terdeteksi dan dipertahankan untuk menjaga representativitas antar-desa.

2. **Transformasi Data**
   - Uji VIF menunjukkan multikolinearitas tinggi (VIF ≥ 10) pada beberapa variabel.
   - **PCA** mereduksi 8 variabel menjadi **2 komponen utama** yang saling bebas.

3. **Data Mining (Clustering)**
   - **Two-Step Cluster** diterapkan pada 2 komponen utama hasil PCA.
   - Berdasarkan *Ratio of Distance Measures* tertinggi (≈2,674), jumlah klaster optimal adalah **3 klaster**.

4. **Evaluasi & Visualisasi**
   - Skor **Silhouette ≈ 0,6** (*good*), menandakan kualitas klaster yang baik.
   - Visualisasi spasial dilakukan di **QGIS** untuk memetakan sebaran tiap klaster.

## Hasil Utama
Pengelompokan 132 desa menjadi **3 klaster** dengan karakteristik ringkas berikut:

- **Klaster 1 (≈39 desa | ~29,5%)**  
  **Karakteristik**: Jumlah penduduk tinggi, kepadatan sedang.  
  **Lokasi**: Umumnya dekat pusat kota.

- **Klaster 2 (≈69 desa | ~52,3%)**  
  **Karakteristik**: Klaster terbesar, jumlah penduduk & kepadatan sedang.  
  **Lokasi**: Banyak di wilayah pinggiran kota.

- **Klaster 3 (≈24 desa | ~18,2%)**  
  **Karakteristik**: Jumlah penduduk rendah, **kepadatan sangat tinggi** (wilayah kecil).  
  **Lokasi**: Pusat kota/inti dengan luas relatif sempit.

## Rekomendasi Kebijakan (Ringkas)
- **Klaster 3 (Pusat Kota)**: Optimalkan infrastruktur, dorong pembangunan vertikal, tata kelola lalu lintas untuk mengurangi kemacetan.
- **Klaster 2 (Pinggiran)**: Pemerataan pembangunan & peningkatan konektivitas transportasi.
- **Klaster 1 (Dekat Pusat Kota)**: Penguatan SDM & program peningkatan keterampilan masyarakat.

## Perangkat Lunak
- **Analisis Statistik**: IBM SPSS Statistics 25 (Windows)
- **Pemetaan**: QGIS 3.40 (Windows)


