# Slide 1: Judul Proyek
**Komparasi Performa Algoritma Unsupervised Learning: K-Means vs Agglomerative Hierarchical Clustering**

* **Anggota Kelompok:**

---

# Slide 2: Latar Belakang & Tujuan
**Mengapa Clustering? **
* **Problem:** Mengidentifikasi pola tersembunyi dalam dataset multidimensi tanpa label target.
* **Tujuan Proyek:**
    1. Mengimplementasikan dua paradigma *clustering* yang berbeda (Partisi vs Hierarki).
    2. Melakukan evaluasi kuantitatif menggunakan *Silhouette Score*.
    3. Visualisasi data 4D ke dalam bidang 2D menggunakan PCA (*Principal Component Analysis*).

---

# Slide 3: Metode 1 - K-Means Clustering
**Paradigma: Centroid-Based Clustering**
* **Logika:** Membagi data ke dalam *n* klaster dengan cara meminimalkan *inertia* (jarak kuadrat dalam klaster).
* **Karakteristik:**
    * Sangat efisien secara komputasi ($O(n)$).
    * Hasil cenderung berbentuk sperikal (bulat).
    * Memerlukan inisialisasi jumlah *k* di awal.
* **Konfigurasi:** Menggunakan `n_init=10` untuk menghindari *local optima* pada posisi awal *centroid*.

---

# Slide 4: Metode 2 - Agglomerative Clustering
**Paradigma: Hierarchical (Bottom-Up) Clustering**
* **Logika:** Menganggap setiap titik data sebagai klaster individu, lalu menggabungkannya secara bertahap berdasarkan kedekatan jarak hingga mencapai jumlah klaster yang diinginkan.
* **Karakteristik:**
    * Tidak memerlukan inisialisasi pusat data acak.
    * Menghasilkan struktur hierarki yang stabil.
    * Lebih fleksibel dalam menangani bentuk data yang tidak beraturan dibanding K-Means.

---

# Slide 5: Deskripsi Dataset & Preprocessing
**Dataset: Iris Species**
* **Fitur:** Sepal Length, Sepal Width, Petal Length, Petal Width (4 Dimensi).
* **Sumber Data:** [Github Seaborn - Iris CSV](https://github.com/mwaskom/seaborn-data/blob/master/iris.csv)
* **Pipeline Pengolahan Data:**
    1. **Standardization:** Menyamakan skala fitur menggunakan `StandardScaler` (Mean=0, Var=1) karena algoritma clustering berbasis jarak sangat sensitif terhadap skala.
    2. **Dimension Reduction:** Menggunakan PCA untuk mereduksi 4 fitur menjadi 2 komponen utama agar bisa divisualisasikan dalam *scatter plot*.

---

# Slide 6: Analisis Hasil & Evaluasi
**Perbandingan Metrik (Silhouette Score)**

| Metode | Silhouette Score | Keterangan |
| :--- | :--- | :--- |
| **K-Means** | ~0.4599 | Pemisahan antar klaster cukup solid dan efisien. |
| **Agglomerative** | ~0.4466 | Sedikit di bawah K-Means, namun struktur hierarkinya konsisten. |

*Note: Skor mendekati 1 menunjukkan klaster terpisah dengan baik. Skor di atas 0.4 sudah dianggap cukup baik untuk dataset dengan fitur yang tumpang tindih.*

---

# Slide 7: Visualisasi Hasil (Screenshot Program)
*(Instruksi untuk teman: Masukkan screenshot dari output program Jupyter Notebook di sini)*

* **Grafik Kiri:** Plot K-Means (Warna klaster berdasarkan *Centroid*).
* **Grafik Kanan:** Plot Agglomerative (Warna klaster berdasarkan *Connectivity*).
* **Analisis Visual:** Terlihat bagaimana kedua algoritma menentukan batas (*boundary*) pada area yang padat data.

---

# Slide 8: Kesimpulan
* **K-Means** unggul dalam hal kecepatan dan pemisahan yang tegas pada dataset numerik yang terstandarisasi.
* **Agglomerative** memberikan perspektif pengelompokan yang berbeda namun tetap akurat secara matematis.
* Untuk dataset Iris, **K-Means** adalah solusi yang lebih optimal karena struktur datanya yang cenderung mengumpul secara teratur (*well-defined clusters*).