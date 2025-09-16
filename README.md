# Analisis Klaster Kepadatan Penduduk Kabupaten Kudus Menggunakan Metode Two-Step Cluster

## Ringkasan Proyek

[cite_start]Proyek ini merupakan analisis data statistik untuk mengidentifikasi pola dan karakteristik kepadatan penduduk di tingkat desa/kelurahan di Kabupaten Kudus tahun 2024[cite: 4]. [cite_start]Sebagai kabupaten dengan luas wilayah terkecil namun memiliki kepadatan penduduk tertinggi di Jawa Tengah, pemahaman distribusi penduduk sangat krusial untuk mendukung kebijakan pemerintah daerah[cite: 145, 146, 147].

[cite_start]Analisis ini menggunakan metode *machine learning* dalam kategori *unsupervised learning*, yaitu **Two-Step Cluster**, untuk mengelompokkan 132 desa/kelurahan berdasarkan 8 variabel demografis[cite: 149, 470, 473]. [cite_start]Untuk mengatasi masalah multikolinearitas yang tinggi pada data, teknik reduksi dimensi **Principal Component Analysis (PCA)** diterapkan sebelum proses klastering[cite: 508].

[cite_start]Proyek ini dilaksanakan sebagai bagian dari kegiatan magang **FMIPA Prigel** di **Badan Pusat Statistik (BPS) Kabupaten Kudus** [cite: 1, 3] [cite_start]selama periode 1 September - 30 November 2024[cite: 33].

## Dataset

* [cite_start]**Sumber Data**: Data sekunder yang digunakan berasal dari publikasi resmi BPS Kabupaten Kudus, yaitu "Kecamatan dalam Angka Tahun 2024"[cite: 165, 188].
* [cite_start]**Variabel**: 8 variabel numerik yang digunakan dalam analisis meliputi[cite: 473]:
    * [cite_start]Jumlah Penduduk [cite: 474]
    * [cite_start]Jumlah Laki-laki [cite: 475]
    * [cite_start]Jumlah Perempuan [cite: 476]
    * [cite_start]Jumlah Kelahiran [cite: 477]
    * [cite_start]Jumlah Kematian [cite: 478]
    * [cite_start]Kepadatan Penduduk (per km²) [cite: 479]
    * [cite_start]Jumlah Kedatangan [cite: 480]
    * [cite_start]Jumlah Kepindahan [cite: 481]

## Metodologi

[cite_start]Analisis data dilakukan mengikuti tahapan *Knowledge Discovery in Databases (KDD)*[cite: 451].

1.  **Preprocessing Data**:
    * [cite_start]Data dipastikan tidak memiliki nilai yang hilang (*missing value*) atau data duplikat[cite: 489, 491].
    * [cite_start]*Outlier* terdeteksi namun tetap dipertahankan untuk menjaga keutuhan data representasi setiap desa[cite: 495].

2.  **Transformasi Data**:
    * [cite_start]Uji VIF menunjukkan adanya multikolinearitas tinggi pada beberapa variabel (nilai VIF ≥ 10)[cite: 506].
    * [cite_start]**Principal Component Analysis (PCA)** digunakan untuk mereduksi 8 variabel menjadi 2 komponen utama yang saling bebas, sehingga mengatasi masalah multikolinearitas[cite: 508, 553].

3.  **Data Mining (Clustering)**:
    * [cite_start]**Metode Two-Step Cluster** diterapkan pada 2 komponen utama hasil PCA[cite: 513].
    * [cite_start]Berdasarkan nilai *Ratio of Distance Measures* tertinggi (2,674), jumlah klaster optimal yang terbentuk adalah **3 klaster**[cite: 517, 518].

4.  **Evaluasi & Visualisasi**:
    * Kualitas klaster dievaluasi menggunakan **Metode Silhouette**, yang menghasilkan skor **0,6**. [cite_start]Nilai ini menunjukkan struktur klaster yang terbentuk berkualitas **baik** (*good*)[cite: 545].
    * [cite_start]Hasil klastering divisualisasikan dalam bentuk peta geografis menggunakan *software* **QGIS** untuk menunjukkan sebaran spasial setiap klaster[cite: 167, 532].

## Hasil Analisis

[cite_start]Analisis berhasil mengelompokkan 132 desa di Kabupaten Kudus menjadi 3 klaster dengan karakteristik unik[cite: 554]:

* **Klaster 1 (39 Desa - 29,5%)**:
    * [cite_start]**Karakteristik**: Jumlah penduduk tinggi dengan kepadatan sedang[cite: 541, 562].
    * [cite_start]**Lokasi**: Umumnya terletak di area dekat pusat kota[cite: 563].

* **Klaster 2 (69 Desa - 52,3%)**:
    * [cite_start]**Karakteristik**: Klaster terbesar dengan jumlah penduduk dan kepadatan tergolong sedang[cite: 535, 559].
    * [cite_start]**Lokasi**: Sebagian besar berada di daerah pinggiran kota[cite: 537, 561].

* **Klaster 3 (24 Desa - 18,2%)**:
    * [cite_start]**Karakteristik**: Klaster terkecil dengan jumlah penduduk rendah namun kepadatan penduduk sangat tinggi[cite: 538, 555].
    * [cite_start]**Lokasi**: Berada di pusat kota dengan luas wilayah yang relatif kecil[cite: 540, 557].

## Rekomendasi

[cite_start]Berdasarkan hasil analisis, beberapa saran kebijakan diajukan kepada pemerintah Kabupaten Kudus[cite: 568]:
* [cite_start]**Untuk Klaster 3 (Pusat Kota)**: Optimalisasi infrastruktur, mendorong pembangunan vertikal, dan mengelola lalu lintas untuk mengurangi kemacetan[cite: 569].
* [cite_start]**Untuk Klaster 2 (Pinggiran Kota)**: Pemerataan pembangunan dan peningkatan sarana transportasi untuk konektivitas yang lebih baik[cite: 570].
* [cite_start]**Untuk Klaster 1 (Dekat Pusat Kota)**: Pengelolaan sumber daya manusia yang efektif dan penyediaan pelatihan keterampilan bagi masyarakat[cite: 571].

## Tools yang Digunakan

* [cite_start]**Analisis Statistik**: SPSS 25 for Windows [cite: 167]
* [cite_start]**Visualisasi Peta**: QGIS 3.40 for Windows [cite: 167]
