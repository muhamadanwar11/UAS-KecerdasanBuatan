
#  Heart Disease Detection Using Logistic Regression

##  Deskripsi Proyek

Proyek ini bertujuan untuk membangun sistem prediksi penyakit jantung berdasarkan data medis pasien menggunakan algoritma **Logistic Regression**. Model ini diharapkan dapat membantu tenaga medis dalam melakukan deteksi awal terhadap penyakit jantung secara cepat dan efisien.

---

##  Struktur File

| File                                     | Deskripsi                                                                                     |
| ---------------------------------------- | --------------------------------------------------------------------------------------------- |
| `LAPORAN TUGAS BESAR AI.pdf`             | Laporan lengkap tugas besar deteksi penyakit jantung menggunakan AI.                          |
| `Penyakit_Jantung.ipynb`                 | Notebook Python (Google Colab) yang berisi implementasi Logistic Regression.                  |
| `heart.csv`                              | Dataset penyakit jantung dari UCI yang digunakan dalam pelatihan dan pengujian.               |
| `JEFRI - Jurnal Logistic Regression.pdf` | Jurnal ilmiah referensi terkait metode Logistic Regression dalam mendeteksi penyakit jantung. |

---

## 🧭 Langkah-langkah Proyek

### 1. Business Understanding

* Masalah utama: Penyakit jantung merupakan penyebab kematian tertinggi di Indonesia dan dunia.
* Tujuan: Membangun sistem deteksi awal berbasis machine learning.
* Target pengguna: Tenaga medis, peneliti, dan lembaga kesehatan.

### 2. Data Understanding

* Dataset: `heart.csv` berisi 14 fitur dan 303 baris data pasien.
* Fitur penting: `age`, `sex`, `cp`, `chol`, `thalach`, `exang`, `oldpeak`, dll.
* Target klasifikasi: `target` (1 = sakit, 0 = sehat).

### 3. Exploratory Data Analysis (EDA)

* **Visualisasi**: Histogram, boxplot, heatmap korelasi.
* **Temuan**:

  * Korelasi positif: `cp`, `thalach`
  * Korelasi negatif: `oldpeak`, `ca`, `exang`
  * Banyak outlier ditemukan pada `chol`, `trestbps`, dan `ca`.
* **Data imbalance**: Distribusi target cukup seimbang.

### 4. Data Preparation

* **Missing values**: Penanganan pada fitur `oldpeak` (bisa imputasi atau drop).
* **Encoding**: Label Encoding dan One-hot Encoding untuk variabel kategorikal.
* **Normalisasi**: MinMaxScaler digunakan untuk semua fitur numerik.
* **Split data**: 80% training, 20% testing (stratified split).

### 5. Modeling: Logistic Regression

* Digunakan `LogisticRegression()` dari `sklearn.linear_model`
* Parameter penting:

  * `solver='liblinear'`
  * `penalty='l2'`
  * `max_iter=200`

### 6. Evaluation

* **Confusion Matrix**:

  * TP = 137, TN = 116, FP = 34, FN = 21
* **Metrics**:

  * Accuracy: 86%
  * Precision: 80–85%
  * Recall: 87–91%
  * F1-Score: \~0.83

### 7. Deployment (Opsional)

* Model ini direkomendasikan untuk diintegrasikan ke sistem klinis berbasis web atau aplikasi sebagai alat bantu skrining awal.

---

## ⚙️ Requirements

* Python >= 3.7
* Libraries:

  ```bash
  pip install pandas numpy matplotlib seaborn scikit-learn
  ```

---

## Dataset Info

* Sumber: [UCI Heart Disease](https://archive.ics.uci.edu/ml/datasets/Heart+Disease)
* Link Kaggle: [https://www.kaggle.com/ronitf/heart-disease-uci](https://www.kaggle.com/ronitf/heart-disease-uci)

---

## 📚 Referensi

1. Pangaribuan, J.J., et al. (2021). *Machine Learning for Heart Disease Detection*. UPH Journal.
2. Virani, S.S., et al. (2023). *Heart Disease and Stroke Statistics – 2023*. JACC.
3. Kementerian Kesehatan RI. (2022). *Penyakit Jantung Nomor 1 di Indonesia*.
4. WHO. (2024). *Global Heart Disease Report*.
5. Salim Yusuf. (2020). *Global Cardiovascular Inequality Study*.

---

## Kesimpulan

Model Logistic Regression menunjukkan performa **tinggi dan andal** untuk prediksi penyakit jantung, dengan interpretabilitas yang baik dan efisiensi tinggi. Sangat cocok untuk skrining awal dalam dunia medis.
