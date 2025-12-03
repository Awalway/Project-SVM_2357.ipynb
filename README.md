# Prediksi Kelulusan Mahasiswa Menggunakan Support Vector Machine (SVM)

Proyek ini adalah tugas Machine Learning untuk memprediksi status kelulusan mahasiswa (Lulus / Belum Lulus) berdasarkan data akademis dan demografis menggunakan algoritma **Support Vector Machine (SVM)**.

## 👤 Identitas Mahasiswa
* **Nama:** Muhamad Ramadan Awaliadi
* **NIM:** 2457201002357
* **Prodi:** Sistem Informasi
* **Kampus:** Universitas Darwan Ali

---

## Deskripsi Dataset
Dataset yang digunakan adalah `datakelulusanmahasiswa.csv`. Data ini berisi rekam jejak akademis mahasiswa.

* **Fitur (Input):**
    * `IPK`: Indeks Prestasi Kumulatif.
    * `IPS 1 - IPS 8`: Indeks Prestasi per semester.
    * `UMUR`: Usia mahasiswa.
    * `STATUS MAHASISWA`: Status aktif perkuliahan.
    * `STATUS NIKAH` & `JENIS KELAMIN`: Data demografis.
* **Target (Label):**
    * `STATUS KELULUSAN`: Label klasifikasi (`LULUS` atau `TIDAK LULUS` / `TEPAT WAKTU` vs `TERLAMBAT`).

*Catatan: Kolom identitas seperti 'NAMA' dihapus saat preprocessing karena tidak relevan untuk prediksi.*

---

## Langkah Pengerjaan
Proses pengerjaan proyek ini mengikuti alur Data Science standar:

1.  **Data Loading:** Memuat dataset dari Google Drive menggunakan Pandas.
2.  **Exploratory Data Analysis (EDA):**
    * Melihat statistik deskriptif.
    * Visualisasi distribusi data (Histogram & Countplot).
3.  **Preprocessing Data:**
    * Cleaning: Menangani *missing values*.
    * Encoding: Mengubah data kategori (teks) menjadi angka menggunakan `LabelEncoder` dan `OneHotEncoder`.
    * **Scaling:** Menggunakan `StandardScaler` untuk menormalisasi fitur (sangat penting untuk SVM).
    * Splitting: Membagi data menjadi 80% Training dan 20% Testing.
4.  **Modeling:**
    * Melatih model SVM.
    * Melakukan **Hyperparameter Tuning** menggunakan `GridSearchCV` untuk mencari parameter terbaik (`C`, `gamma`, dan `kernel`).
5.  **Evaluasi:** Mengukur performa model dengan Confusion Matrix dan Classification Report.

---

## Hasil Evaluasi Model
Berdasarkan hasil training dan testing, didapatkan performa model sebagai berikut:

* **Model Terbaik:** SVM dengan Kernel `linear`
* **Parameter Terbaik:** C = `10`, Gamma = `'scale', 'kernel': 'linear'`
* **Akurasi:** `90.54%`

**Kesimpulan:**
Model mampu memprediksi status kelulusan mahasiswa dengan baik berdasarkan pola nilai IPK/IPS dan status mahasiswa.

## Cara Menjalankan Notebook
Untuk menjalankan proyek ini, Anda memerlukan **Google Colab**.

1.  **Siapkan Dataset:**
    * Unduh file `datakelulusanmahasiswa.csv`.
    * Upload file tersebut ke Google Drive Anda (disarankan di folder utama/root).

2.  **Buka Notebook:**
    * Buka file `SVM_kelulusan.ipynb` di Google Colab.

3.  **Mount Drive:**
    * Jalankan cell pertama untuk menghubungkan Colab dengan Google Drive.

4.  **Eksekusi:**
    * Klik menu **Runtime** > **Run all** (Jalankan semua).
    * Hasil prediksi dan evaluasi akan muncul di bagian output setiap cell.
