# Klasifikasi Kualitas Wine Menggunakan Random Forest
**Proyek Ujian Tengah Semester (UTS) - Data Mining**

## 👤 Identitas Mahasiswa
- **Nama:** Wismaya Zelda R.
- **NIM:** 2304020006
- **Mata Kuliah:** Data Mining

---

## 📝 Deskripsi Proyek
Proyek ini bertujuan untuk mengembangkan model klasifikasi yang dapat menentukan kualitas anggur (*wine*) berdasarkan atribut kimiawinya. Masalah ini didekati sebagai tugas klasifikasi multi-kelas di mana model harus memprediksi skor kualitas dalam rentang 3 hingga 8.

Tantangan utama dalam proyek ini adalah adanya **ketidakseimbangan kelas** (*class imbalance*), di mana sampel untuk kualitas menengah (5 dan 6) jauh lebih banyak dibandingkan kualitas ekstrem (rendah atau tinggi).

## 📊 Dataset
Dataset yang digunakan mencakup parameter fisikokimia dari sampel wine.
- **Data Training:** Digunakan untuk melatih model dan validasi internal.
- **Data Testing:** Digunakan untuk menguji performa model pada data baru yang belum pernah dilihat.

### Fitur-fitur:
1.  **Fixed Acidity**: Kadar asam tetap.
2.  **Volatile Acidity**: Kadar asam atsiri (berkaitan dengan aroma cuka).
3.  **Citric Acid**: Asam sitrat untuk kesegaran.
4.  **Residual Sugar**: Sisa gula setelah proses fermentasi.
5.  **Chlorides**: Kadar garam.
6.  **Free & Total Sulfur Dioxide**: Pengawet untuk mencegah oksidasi/mikroba.
7.  **Density & pH**: Kerapatan air dan tingkat keasaman.
8.  **Sulphates & Alcohol**: Aditif wine dan kadar alkohol.

## 🛠️ Metodologi Pengerjaan

### 1. Pre-processing Data
- **Feature Scaling**: Menggunakan `StandardScaler` untuk menormalisasi fitur agar memiliki skala yang seragam, yang membantu stabilitas algoritma.
- **Data Splitting**: Membagi dataset menjadi data latih dan data validasi untuk memantau *overfitting*.

### 2. Pemodelan
Model utama yang digunakan adalah **Random Forest Classifier**. Alasan pemilihan model ini adalah:
- Mampu menangani hubungan non-linear antar fitur.
- Memiliki ketahanan terhadap *outliers*.
- Dilengkapi parameter `class_weight='balanced'` untuk memitigasi dampak ketidakseimbangan dataset.

### 3. Evaluasi Model
Model dievaluasi menggunakan metrik:
- **Accuracy Score**: Persentase prediksi yang tepat secara keseluruhan.
- **Confusion Matrix**: Untuk melihat distribusi kesalahan prediksi antar kelas.
- **Classification Report**: Analisis *Precision*, *Recall*, dan *F1-Score* per kelas.

## 📈 Hasil dan Analisis
- **Akurasi Model**: Berhasil mencapai skor **0.61** pada data validasi.
- **Observasi**: Model sangat kuat dalam mengenali kualitas 5 dan 6 karena data pendukung yang melimpah.
- **Limitasi**: Terdapat kesulitan dalam memprediksi kelas minoritas (3, 4, 7, 8). Hal ini menunjukkan bahwa meskipun teknik penyeimbangan berat kelas telah diterapkan, model tetap membutuhkan lebih banyak data untuk varietas wine berkualitas ekstrem.
