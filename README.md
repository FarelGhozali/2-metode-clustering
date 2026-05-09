# Metode Clustering

Proyek ini berisi implementasi metode clustering menggunakan Python di dalam Jupyter Notebook (`main.ipynb`). Untuk menjalankan proyek ini secara aman dan menghindari konflik dependensi di sistem operasi Anda, sangat disarankan untuk menggunakan *Virtual Environment*.

## Persyaratan
- Python 3.x terinstal di sistem Anda.
- `pip` (Python package installer).

## Cara Menjalankan Proyek

Berikut adalah langkah-langkah untuk menyiapkan environment dan menjalankan Jupyter Notebook pada proyek ini:

### 1. Buka Terminal
Buka terminal dan arahkan ke direktori root proyek ini.

### 2. Buat Virtual Environment
Jalankan perintah berikut untuk membuat *virtual environment* baru (di sini kita namakan `venv`):
```bash
python3 -m venv venv
```

### 3. Aktifkan Virtual Environment
Aktifkan *virtual environment* yang baru saja dibuat agar sistem menggunakan environment ini dan bukan environment global (OS).

- **Pengguna Linux/macOS:**
  ```bash
  source venv/bin/activate
  ```
- **Pengguna Windows (Command Prompt):**
  ```cmd
  venv\Scripts\activate
  ```
- **Pengguna Windows (PowerShell):**
  ```powershell
  .\venv\Scripts\Activate.ps1
  ```
*(Jika berhasil, Anda akan melihat awalan `(venv)` pada baris perintah terminal Anda).*

### 4. Instal Dependensi Proyek
Instal semua pustaka (library) yang dibutuhkan oleh proyek ini sesuai dengan daftar yang ada di file `requirements.txt`:
```bash
pip install -r requirements.txt
```
*(Catatan: Jika saat proses instalasi muncul tulisan peringatan seperti "WARNING: Cache entry deserialization failed, entry ignored", Anda dapat **mengabaikannya**. Itu hanya peringatan bahwa pip gagal membaca file cache lama, namun proses unduhan dan instalasi akan tetap berjalan normal).*

### 5. Jalankan Jupyter Notebook
Setelah instalasi paket selesai, jalankan Jupyter Notebook dengan perintah:
```bash
jupyter notebook
```
Perintah ini akan secara otomatis membuka antarmuka Jupyter di browser web Anda. Dari antarmuka tersebut, klik dan buka file **`main.ipynb`** untuk mulai mengeksekusi kode.

### 6. Keluar dari Virtual Environment
Jika Anda sudah selesai mengerjakan proyek dan ingin keluar dari *virtual environment*, cukup jalankan perintah berikut di terminal:
```bash
deactivate
```