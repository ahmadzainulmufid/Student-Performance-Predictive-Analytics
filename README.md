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

---

## 🎯 Business Understanding

### 📝 Problem Statements

- Banyak faktor mempengaruhi kinerja akademik siswa. Tantangan utamanya adalah memprediksi kelulusan siswa berdasarkan data akademik dan sosial-ekonomi.

### 🎯 Goals

- Membangun model prediksi kelulusan siswa.
- Membantu pendidik mengambil keputusan intervensi berbasis data.
- Memahami faktor-faktor utama keberhasilan akademik siswa.

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

### 🗂️ Fitur Utama

Beberapa fitur penting: `sex`, `age`, `studytime`, `failures`, `absences`, `G1`, `G2`, `G3`.

### 🔍 Exploratory Data Analysis (EDA)

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

1. **Encoding Variabel Kategorikal** menggunakan Label Encoding.
2. **Pemisahan Fitur dan Target**:
   - Target: `G3`, dikonversi menjadi binary (lulus/tidak lulus).
3. **Seleksi Fitur**:
   - Menggunakan fitur signifikan: `G1`, `G2`, `studytime`, `failures`, `absences`, `age`, `sex`.
4. **Split Data**:
   - 80% training, 20% testing.
5. **Feature Scaling**:
   - StandardScaler untuk SVM dan Logistic Regression.

---

## 🤖 Model Development

### Model yang Dibangun:

- Random Forest Classifier
- Logistic Regression
- Support Vector Machine (SVM)

> 📌 Catatan: Pemilihan model terbaik dijelaskan pada bagian Evaluation.

---

## 🏆 Evaluation

### Metrik Evaluasi:

- Accuracy
- Precision
- Recall
- F1-Score

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
