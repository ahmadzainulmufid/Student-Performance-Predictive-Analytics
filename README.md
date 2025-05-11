# 📄 Student Performance Predictive Analytics

## 🧩 Table of Contents
- [Domain Proyek](#domain-proyek)
- [Business Understanding](#business-understanding)
- [Data Understanding](#data-understanding)
- [Data Preparation](#data-preparation)
- [Model Development](#model-development)
- [Evaluation](#evaluation)

---

## 🏫 Domain Proyek

Proyek ini berada di bidang **Pendidikan**, berfokus pada pembuatan sistem **prediksi performa akademik siswa** menggunakan **machine learning**.

Latar Belakang
Dalam dunia pendidikan modern, kemampuan untuk mengidentifikasi siswa yang berisiko gagal studi sangat penting agar intervensi dini bisa diberikan. Banyak siswa menghadapi tantangan akademik dan sosial-ekonomi yang memengaruhi performa belajar mereka. Namun, institusi pendidikan seringkali kesulitan mengantisipasi hal ini secara akurat. Oleh karena itu, proyek ini bertujuan membangun sistem prediksi performa akademik siswa berdasarkan data historis mereka, dengan harapan dapat membantu guru dan pihak sekolah membuat keputusan yang lebih tepat sasaran.

---

## 🎯 Business Understanding

### 📝 Problem Statements

- Sulit memprediksi siswa mana yang berisiko tidak lulus tepat waktu.
- Intervensi sering dilakukan terlambat karena kurangnya data analitik.
- Faktor-faktor penyebab kegagalan siswa belum diketahui secara pasti.

### 🎯 Goals

- Membangun model klasifikasi untuk memprediksi kelulusan siswa.
- Membantu pendidik mengidentifikasi siswa berisiko secara lebih dini.
- Menggali fitur-fitur dominan yang memengaruhi hasil belajar.

### 💡 Solution Statements

Model yang dieksplorasi:
- Random Forest
- Logistic Regression
- Support Vector Machine (SVM)

---

## 📊 Data Understanding

### ℹ️ Informasi Data

- Dataset: Student Performance Dataset dari UCI Repository
- 649 sampel, 33 fitur.
- Tidak ada missing values.

[Link Dataset](https://www.kaggle.com/datasets/larsen0966/student-performance-data-set)

Berikut ini dafar lengkap dan deksripsi semua fitur (33 total)

| Fitur        | Deskripsi                                                                 |
|--------------|---------------------------------------------------------------------------|
| school       | Sekolah tempat siswa belajar (GP = Gabriel Pereira, MS = Mousinho da Silveira) |
| sex          | Jenis kelamin siswa (F = perempuan, M = laki-laki)                        |
| age          | Usia siswa (15–22 tahun)                                                  |
| address      | Tipe alamat (U = urban, R = rural)                                        |
| famsize      | Ukuran keluarga (LE3 = ≤3, GT3 = >3 anggota keluarga)                    |
| Pstatus      | Status hidup orang tua (T = tinggal bersama, A = terpisah)               |
| Medu         | Pendidikan ibu (0–4; 0 = tidak sekolah, 4 = pendidikan tinggi)            |
| Fedu         | Pendidikan ayah (0–4; sama seperti Medu)                                  |
| Mjob         | Pekerjaan ibu (teacher, health, services, at_home, other)                |
| Fjob         | Pekerjaan ayah (teacher, health, services, at_home, other)               |
| reason       | Alasan memilih sekolah (home, reputation, course, other)                 |
| guardian     | Wali siswa (mother, father, other)                                       |
| traveltime   | Waktu tempuh ke sekolah (1–4; 1 = <15m, 4 = >1jam)                        |
| studytime    | Waktu belajar mingguan (1–4; 1 = <2 jam, 4 = >10 jam)                    |
| failures     | Jumlah ketidaklulusan sebelumnya (0–3)                                    |
| schoolsup    | Dukungan tambahan dari sekolah (yes/no)                                  |
| famsup       | Dukungan tambahan dari keluarga (yes/no)                                 |
| paid         | Les tambahan berbayar untuk mata pelajaran (yes/no)                      |
| activities   | Kegiatan ekstrakurikuler (yes/no)                                        |
| nursery      | Apakah siswa pernah ikut taman kanak-kanak (yes/no)                      |
| higher       | Keinginan melanjutkan pendidikan tinggi (yes/no)                         |
| internet     | Akses internet di rumah (yes/no)                                         |
| romantic     | Dalam hubungan romantis (yes/no)                                         |
| famrel       | Hubungan keluarga (1–5; 5 = sangat baik)                                 |
| freetime     | Waktu luang setelah sekolah (1–5)                                        |
| goout        | Frekuensi keluar dengan teman (1–5)                                      |
| Dalc         | Konsumsi alkohol di hari kerja (1–5)                                     |
| Walc         | Konsumsi alkohol di akhir pekan (1–5)                                    |
| health       | Status kesehatan saat ini (1–5)                                          |
| absences     | Jumlah ketidakhadiran                                                    |
| G1           | Nilai ujian pertama (0–20)                                               |
| G2           | Nilai ujian kedua (0–20)                                                 |
| G3           | Nilai akhir (target) (0–20)                                              |

### 🗂️ Fitur Utama

Beberapa fitur penting: `sex`, `age`, `studytime`, `failures`, `absences`, `G1`, `G2`, `G3`.

### 🔍 Exploratory Data Analysis (EDA)

- Heatmap menunjukkan `G1` dan `G2` sangat berkorelasi dengan `G3`, artinya performa masa lalu adalah prediktor utama.
- Boxplot `absences` menunjukkan siswa dengan absensi ekstrem (terlalu sering bolos) cenderung gagal.

Visualisasi:
- **Distribusi Target (G3)**:

  ![Distribusi G3](https://github.com/user-attachments/assets/5766b7d3-50dd-44e7-b481-9ef6e7015134)

- **Heatmap Korelasi**:

  ![heatmap_korelasi](https://github.com/user-attachments/assets/1bc23511-e428-4db3-a9ae-5fdab5c8d267)

- **Boxplot Absences**:

  ![boxplot_absences](https://github.com/user-attachments/assets/ff0c9534-7d16-4223-ae88-ecde9a5fa4c0)

**Insight Penting:**
- Nilai semester 1 dan 2 (`G1`, `G2`) sangat menentukan kelulusan.
- Absensi yang tinggi cenderung berasosiasi dengan kegagalan.

---

## 📈 Data Preparation

### Tahapan Data Preparation:

1. **Cek missing value & duplikasi** – Tidak ditemukan adanya nilai kosong atau duplikat.
2. **Drop fitur non-relevan** – Tidak dilakukan karena semua fitur dianggap relevan dan digunakan dalam analisis.
3. **Feature selection** – Memilih subset fitur seperti `sex`, `age`, `studytime`, `G1`, `G2`, `G3`, dsb dari dataset asli.
4. **Membuat label target `pass`** – Mengubah kolom `G3` menjadi label biner: jika `G3 >= 10` maka `pass = 1`, jika tidak maka `pass = 0`.
5. **Drop kolom `G3`** – Karena nilai `G3` sudah dipakai untuk membuat label, maka kolom ini dihapus dari fitur.
6. **Encoding variabel kategorikal** – Menggunakan `LabelEncoder` untuk kolom bertipe objek seperti `sex`, `school`, `internet`, dll.
7. **Split data** – Data dibagi menjadi 80% data latih dan 20% data uji menggunakan stratifikasi berdasarkan label `pass`.
8. **Normalisasi fitur numerik** – Menggunakan `StandardScaler` agar fitur numerik memiliki distribusi yang seragam.

---

## 🤖 Model Development

### Model yang Dibangun:

### Random Forest
Model ensemble berbasis pohon keputusan. Cocok untuk data tabular.  
- Parameter: `n_estimators=100`, `max_depth=None`, `random_state=42`.

### Logistic Regression
Model linier yang memetakan prediksi probabilitas antara 0–1.  
- Parameter: `solver='liblinear'`, regularisasi default.

### SVM
Model margin-based yang bekerja optimal di ruang berdimensi tinggi.  
- Parameter: kernel `'rbf'`, `C=1.0`, `gamma='scale'`.

> 📌 Catatan: Pemilihan model terbaik dijelaskan pada bagian Evaluation.

---

## 🏆 Evaluation

### Metrik Evaluasi:

### Keterkaitan Evaluasi dengan Business Understanding

1. **Goal 1: Membangun model akurat**
   - Random Forest mencapai F1-score > 94% → berhasil.

2. **Goal 2: Membantu pendidik**
   - Model ini memungkinkan identifikasi awal siswa yang berisiko gagal → mendukung keputusan intervensi.

3. **Goal 3: Mengetahui faktor kunci**
   - Fitur `G1`, `G2`, dan `failures` menjadi indikator paling penting → dapat menjadi bahan diskusi pengajaran.

### Hasil Evaluasi Model

| Model | Accuracy | Precision | Recall | F1-Score |
|:--|:--:|:--:|:--:|:--:|
| Random Forest | **0.9077** | **0.9537** | **0.9364** | **0.9450** |
| Logistic Regression | 0.9000 | 0.9292 | 0.9545 | 0.9417 |
| SVM | 0.8769 | 0.9123 | 0.9455 | 0.9286 |

**Pemilihan Model:**
- Random Forest dipilih karena menghasilkan metrik terbaik dan konsistensi performa.

### Keterkaitan dengan Goals:

- **Problem:** Kesulitan memprediksi kelulusan siswa.
- **Goal:** Membantu pendidik melalui prediksi akurat.
- **Evaluasi:** Model mampu mencapai akurasi dan F1-score >90%.

---

# 📝 Catatan Akhir

Proyek ini menunjukkan bahwa data akademik dan karakteristik siswa dapat digunakan secara efektif untuk membangun sistem prediksi kelulusan berbasis machine learning.

---

# 🎓 Terima Kasih 🙏
