# 📄 Student Performance Predictive Analytics

## 🧩 Table of Contents
- [Domain Proyek](#domain-proyek)
- [Business Understanding](#business-understanding)
- [Data Understanding](#data-understanding)
- [Data Preparation](#data-preparation)
- [Modeling](#modeling)
- [Evaluation](#evaluation)

---

## 🏫 Domain Proyek

Domain proyek ini berada di bidang **Pendidikan**, dengan fokus utama pada pembuatan sistem **prediksi performa akademik siswa** menggunakan pendekatan **machine learning**.

---

## 🎯 Latar Belakang

Pendidikan merupakan fondasi utama dalam membangun kualitas sumber daya manusia. Salah satu indikator penting dalam dunia pendidikan adalah **kemampuan siswa dalam memahami mata pelajaran utama** seperti:

- **Matematika**
- **Membaca**
- **Menulis**

Nilai pada mata pelajaran ini sering digunakan untuk mengukur **keberhasilan siswa** dalam proses belajar mengajar.

Namun, dalam kenyataannya, banyak siswa yang mengalami **kesulitan dalam mencapai standar kelulusan**.  
Kondisi ini dapat berdampak jangka panjang terhadap perkembangan akademis dan karier mereka di masa depan.

Oleh karena itu, penting untuk **mengidentifikasi faktor-faktor yang mempengaruhi performa siswa sedini mungkin**, sehingga **intervensi yang tepat** dapat dilakukan.

Dengan memanfaatkan **machine learning**, kita dapat membangun **model prediksi** yang mampu **mengklasifikasikan** apakah seorang siswa akan **lulus** atau **gagal** berdasarkan **nilai akademis** dan **karakteristik demografis** mereka.

Model ini dapat membantu:

- **Guru**
- **Sekolah**
- **Pembuat kebijakan**

dalam mengambil **keputusan berbasis data** untuk meningkatkan **tingkat kelulusan siswa**.

---

## ❓ Mengapa dan Bagaimana Masalah Ini Harus Diselesaikan

### Mengapa Masalah Ini Penting:
- ✅ **Meningkatkan efektivitas intervensi pendidikan:**  
  Dengan prediksi dini, sekolah dapat memberikan dukungan tambahan kepada siswa yang berisiko gagal.
  
- ✅ **Membantu alokasi sumber daya:**  
  Sekolah dapat mengalokasikan program pembelajaran tambahan secara lebih efektif kepada kelompok siswa yang membutuhkan.

- ✅ **Mendorong prestasi akademik:**  
  Dengan memahami faktor-faktor penyebab kegagalan, strategi pembelajaran dapat disesuaikan agar lebih inklusif.

### Bagaimana Menyelesaikannya:
- 📈 Menggunakan pendekatan **machine learning** untuk membangun **model klasifikasi**.
- 📊 Model akan menggunakan **fitur kuantitatif** (nilai ujian) dan **fitur kategorikal** (data demografis) untuk **memprediksi status kelulusan siswa**.

---

## 📚 Referensi

- **Paul E. Barton (Educational Testing Service)**  
  _Barton, P. E. (2003). Parsing the Achievement Gap: Baselines for Tracking Progress. Educational Testing Service._

- **OECD (Organisation for Economic Co-operation and Development)**  
  _OECD. (2012). Equity and Quality in Education: Supporting Disadvantaged Students and Schools. OECD Publishing._

---

> 🔖 *Catatan:*  
Penelitian dari sumber di atas menunjukkan bahwa faktor akademik dan latar belakang sosial-ekonomi memiliki **pengaruh signifikan terhadap performa siswa**.  
Sehingga, **upaya prediksi performa akademik berbasis data** sangatlah relevan dilakukan.

---

## 📚 Business Understanding

### 📝 Problem Statements
Berdasarkan latar belakang, permasalahan yang ingin diselesaikan dalam proyek ini adalah:

- Banyak faktor mempengaruhi kinerja akademik siswa. Salah satu tantangan utama adalah memprediksi apakah seorang siswa akan lulus atau tidak berdasarkan data kinerja mereka.
- Dengan menggunakan data seperti nilai ujian matematika, membaca, menulis, serta faktor sosial-ekonomi lainnya, kita dapat membangun model prediksi untuk membantu pendidik dalam:
  - Mengambil langkah-langkah pencegahan,
  - Memberikan dukungan lebih fokus,
  - Memberikan peringatan dini kepada siswa berisiko gagal.

### 🎯 Goals
Tujuan utama proyek ini adalah membangun model prediksi kelulusan siswa berdasarkan data akademik dan sosial mereka. Secara spesifik:

- Memprediksi status kelulusan siswa (lulus atau gagal).
- Membantu pendidik dalam pengambilan keputusan intervensi.
- Memahami faktor-faktor yang mempengaruhi keberhasilan akademik siswa.

### 💡 Solution Statements
Untuk mencapai tujuan tersebut, beberapa solusi yang dipertimbangkan:

#### Solution 1: 🌲 Random Forest
- **Deskripsi:** Algoritma ensemble yang kuat menggunakan beberapa pohon keputusan.
- **Keunggulan:** Menangani data tidak seimbang dan memberikan feature importance.
- **Evaluasi:** Menggunakan Accuracy, Precision, Recall, dan F1-Score.

#### Solution 2: 🧑‍🏫 Logistic Regression (dengan Hyperparameter Tuning)
- **Deskripsi:** Algoritma klasifikasi sederhana yang efektif untuk masalah biner.
- **Tuning:** Regularisasi untuk mengurangi overfitting dan meningkatkan akurasi.
- **Evaluasi:** Accuracy, Precision, Recall, dan F1-Score.

#### Solution 3: ⚙️ Support Vector Machine (SVM)
- **Deskripsi:** Algoritma efektif untuk klasifikasi, terutama dengan batasan kelas yang jelas.
- **Pendekatan:** Menggunakan kernel untuk memodelkan hubungan non-linear.
- **Evaluasi:** Menggunakan metrik yang sama seperti model lain.

---

## 📊 Data Understanding

### ℹ️ Informasi Umum Data
- **Dataset:** Kinerja akademik siswa dari UCI Machine Learning Repository.
- **Jumlah Data:** 649 baris (siswa) dan 33 kolom (fitur).
- **Kondisi Data:** Tidak ada nilai yang hilang (missing values).

**Link dataset:** [Student Performance Dataset](https://www.kaggle.com/datasets/larsen0966/student-performance-data-set)

### 🧾 Deskripsi Variabel/Fitur
| Fitur       | Deskripsi |
| ----------- | --------- |
| `school` | Nama sekolah (kategorikal - nominal) |
| `sex` | Jenis kelamin (kategorikal - nominal) |
| `age` | Usia (numerik - ordinal) |
| `address` | Tipe alamat (Urban/Rural) (kategorikal - nominal) |
| `famsize` | Ukuran keluarga (kategorikal - nominal) |
| `Pstatus` | Status orang tua (kategorikal - nominal) |
| `Medu` | Pendidikan ibu (0-3) (numerik - ordinal) |
| `Fedu` | Pendidikan ayah (0-3) (numerik - ordinal) |
| `Mjob` | Pekerjaan ibu (kategorikal - nominal) |
| `Fjob` | Pekerjaan ayah (kategorikal - nominal) |
| `reason` | Alasan memilih sekolah (kategorikal - nominal) |
| `guardian` | Wali siswa (kategorikal - nominal) |
| `traveltime` | Waktu perjalanan ke sekolah (1-4) (numerik - ordinal) |
| `studytime` | Waktu belajar per minggu (1-4) (numerik - ordinal) |
| `failures` | Jumlah kegagalan sebelumnya (numerik - ordinal) |
| `schoolsup` | Dukungan akademik dari sekolah (kategorikal - nominal) |
| `famsup` | Dukungan belajar dari keluarga (kategorikal - nominal) |
| `paid` | Kursus berbayar (kategorikal - nominal) |
| `activities` | Kegiatan ekstrakurikuler (kategorikal - nominal) |
| `nursery` | Pendidikan prasekolah (kategorikal - nominal) |
| `higher` | Keinginan lanjut pendidikan tinggi (kategorikal - nominal) |
| `internet` | Akses internet di rumah (kategorikal - nominal) |
| `romantic` | Hubungan romantis (kategorikal - nominal) |
| `famrel` | Hubungan keluarga (1-5) (numerik - ordinal) |
| `freetime` | Waktu luang (1-5) (numerik - ordinal) |
| `goout` | Frekuensi keluar bersama teman (1-5) (numerik - ordinal) |
| `Dalc` | Konsumsi alkohol harian (1-5) (numerik - ordinal) |
| `Walc` | Konsumsi alkohol akhir pekan (1-5) (numerik - ordinal) |
| `health` | Kesehatan siswa (1-5) (numerik - ordinal) |
| `absences` | Jumlah absensi (numerik - ordinal) |
| `G1` | Nilai semester 1 (numerik - ordinal) |
| `G2` | Nilai semester 2 (numerik - ordinal) |
| `G3` | Nilai akhir (numerik - ordinal, target prediksi) |

---

## 🔍 Exploratory Data Analysis (EDA)

Tahapan EDA yang dilakukan:

- **📈 Distribusi Data:** Analisis distribusi fitur numerik.
- **🔗 Korelasi Antar Fitur:** Menggunakan matriks korelasi dan heatmap.
- **📊 Distribusi Kategori:** Frekuensi kategori divisualisasikan dengan bar plot.
- **❌ Missing Values:** Pemeriksaan dan penanganan nilai hilang (jika ada).
- **🚨 Outlier Detection:** Pendeteksian outlier menggunakan box plot atau teknik lain.

EDA ini bertujuan untuk memahami lebih dalam pola data dan mempersiapkan dataset untuk modelling.

---

# 📊 Data Preparation

### Tahapan Data Preparation yang Dilakukan:

#### 1. Encoding Variabel Kategorikal
- Mengubah fitur-fitur kategorikal seperti `sex`, `address`, `famsize`, dll menjadi bentuk numerik menggunakan teknik **Label Encoding**.
- **Alasan:** Algoritma machine learning memerlukan input numerik. Encoding dibutuhkan agar model dapat memproses fitur tersebut dengan baik.

#### 2. Pemisahan Fitur dan Target
- Memisahkan fitur (`X`) dan label target (`y`). 
- Target yang digunakan adalah **G3**, yaitu nilai akhir siswa.
- **Alasan:** Supaya model machine learning dapat belajar dari fitur (`X`) untuk memprediksi target (`y`).

#### 3. Membuat Label Kategori Lulus/Tidak
- Target `G3` diubah menjadi kategori:
  - **Lulus (1):** jika nilai G3 ≥ 10
  - **Tidak lulus (0):** jika nilai G3 < 10
- **Alasan:** Mengubah problem menjadi **binary classification** agar model lebih fokus menentukan kelulusan.

#### 4. Split Data Training dan Testing
- Membagi data menjadi:
  - 80% untuk **training**
  - 20% untuk **testing**
- **Alasan:** Untuk menghindari overfitting dan mengevaluasi performa model pada data yang belum pernah dilihat.

#### 5. Feature Scaling (untuk SVM dan Logistic Regression)
- Menggunakan **StandardScaler** untuk membuat fitur memiliki distribusi rata-rata 0 dan standar deviasi 1.
- **Alasan:** Algoritma seperti SVM dan Logistic Regression sensitif terhadap skala fitur.

---

# 🤖 Modeling

### Model yang Digunakan:

#### 1. Random Forest Classifier
- Model ensemble berbasis decision tree.
- **Parameter:**
  - `n_estimators = 100`
  - `max_depth = None`
  - `random_state = 42`
- **Kelebihan:**
  - Tidak rentan terhadap overfitting karena menggabungkan banyak pohon.
  - Dapat menangani data yang kompleks.
- **Kekurangan:**
  - Cukup berat untuk interpretasi.
  - Memerlukan resource komputasi lebih besar dibanding model sederhana.

#### 2. Logistic Regression
- Model statistik untuk binary classification.
- **Parameter:**
  - `solver = 'liblinear'`
  - `random_state = 42`
- **Kelebihan:**
  - Cepat, sederhana, dan interpretasinya jelas.
  - Bekerja sangat baik untuk dataset linier.
- **Kekurangan:**
  - Tidak bisa menangani masalah non-linear dengan baik.
  - Sensitif terhadap outlier.

#### 3. Support Vector Machine (SVM)
- Model klasifikasi berbasis margin.
- **Parameter:**
  - `kernel = 'linear'`
  - `C = 1.0`
  - `random_state = 42`
- **Kelebihan:**
  - Efektif pada ruang fitur tinggi.
  - Bekerja baik pada dataset kecil sampai menengah.
- **Kekurangan:**
  - Training cukup lama pada dataset besar.
  - Sensitif terhadap scaling data.

---

# 🏆 Pemilihan Model Terbaik

Berdasarkan hasil evaluasi:
- **Random Forest** dipilih sebagai model terbaik karena memiliki **Accuracy** dan **F1-Score** tertinggi.
- Random Forest juga lebih stabil terhadap variasi data dibandingkan model lain.

---

# 📈 Evaluation

### Metrik Evaluasi yang Digunakan:
- **Accuracy:** Proporsi prediksi yang benar terhadap total prediksi.
- **Precision:** Seberapa tepat model dalam memprediksi kelas positif.
- **Recall:** Seberapa banyak kelas positif yang berhasil ditemukan oleh model.
- **F1-Score:** Harmonic mean antara precision dan recall, berguna jika ada ketidakseimbangan kelas.

### Formula:

Accuracy = (TP + TN) / (TP + TN + FP + FN) Precision = TP / (TP + FP) Recall = TP / (TP + FN) F1-Score = 2 * (Precision * Recall) / (Precision + Recall)

> **Keterangan:**
> - TP = True Positive
> - TN = True Negative
> - FP = False Positive
> - FN = False Negative

---

# 📋 Hasil Evaluasi Model

| Model                  | Accuracy | Precision | Recall | F1-Score |
|-------------------------|:--------:|:---------:|:------:|:--------:|
| Random Forest           | 0.9077   | 0.9537    | 0.9364 | 0.9450   |
| Logistic Regression     | 0.9000   | 0.9292    | 0.9545 | 0.9417   |
| Support Vector Machine  | 0.8769   | 0.9123    | 0.9455 | 0.9286   |

- **Random Forest** memiliki skor evaluasi terbaik secara keseluruhan dan dipilih sebagai solusi final.
- **Logistic Regression** sedikit lebih sederhana dan cepat, namun akurasi sedikit di bawah Random Forest.
- **SVM** memberikan performa yang baik, tetapi lebih rendah dibandingkan Random Forest dan Logistic Regression pada dataset ini.

---
