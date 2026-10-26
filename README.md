# Prediksi Kanker Payudara (Breast Cancer Classification) 🩺📊

## Deskripsi Proyek
Proyek ini adalah implementasi *Machine Learning* untuk memprediksi apakah suatu sel tumor payudara bersifat **Ganas (Malignant / M)** atau **Jinak (Benign / B)**. Pemodelan dilakukan berdasarkan ekstraksi ciri fisik sel tumor (seperti radius, tekstur, keliling, area, dan kehalusan).

Fokus utama dari proyek medis ini bukan hanya mendapatkan akurasi yang tinggi, tetapi juga mengoptimalkan metrik **Recall** untuk meminimalisir *False Negative* (pasien kanker ganas yang salah didiagnosis sebagai sehat).

## Dataset
Data yang digunakan adalah **Breast Cancer Wisconsin (Diagnostic) Dataset** yang disediakan oleh UCI Machine Learning. Dataset ini ditarik langsung secara otomatis menggunakan *library* `kagglehub`.
*   **Total Fitur:** 30 Fitur Numerik (`_mean`, `_se`, `_worst`)
*   **Target:** Kolom `diagnosis` (M = 1, B = 0)

## Alur Kerja (Workflow)
1. **Exploratory Data Analysis (EDA):**
   * Menganalisis perbedaan rata-rata dan standar deviasi antara sel jinak dan ganas.
   * Visualisasi rentang nilai ekstrem pada fitur `_worst`.
2. **Data Preprocessing:**
   * **Feature Selection:** Menghapus fitur yang mengalami multikolinearitas (informasi ganda/redundant) seperti `perimeter_mean`, `area_mean`, dan `concavity_mean` yang berkorelasi sangat tinggi (r > 0.90) dengan `radius_mean`.
   * **Label Encoding:** Mengubah target diagnosis dari karakter ('M' dan 'B') menjadi nilai biner (1 dan 0).
   * **Standardization:** Menyamakan rentang skala data menggunakan `StandardScaler`.
3. **Modeling:**
   * Algoritma utama yang digunakan adalah **Logistic Regression** (sangat stabil untuk klasifikasi biner medis).
4. **Evaluasi:**
   * Mengukur performa menggunakan *Accuracy*, *Classification Report* (Precision, Recall, F1-Score), dan *Confusion Matrix*.

## Cara Menjalankan Kode 🚀
1. *Clone* repository ini ke komputer lokal Anda:
   ```bash
   git clone [https://github.com/IGOR100125/breast-cancer-prediction.git](https://github.com/IGOR100125/breast-cancer-prediction.git)
