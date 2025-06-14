# Prediksi Intensi Pembelian Konsumen Online Menggunakan Support Vector Machine (SVM)
Proyek ini bertujuan untuk mengembangkan sistem klasifikasi berbasis machine learning untuk memprediksi intensi pembelian konsumen pada platform e-commerce. Model yang digunakan adalah Support Vector Machine (SVM), dengan pendekatan pre-processing, feature selection, dan penanganan data tidak seimbang menggunakan SMOTE. Sistem ini juga dikembangkan dalam bentuk antarmuka web interaktif menggunakan Streamlit.

# Tujuan Project
  - Membangun model klasifikasi SVM untuk memprediksi niat beli pengguna dari perilaku kunjungan mereka (clickstream data).
  - Mengatasi ketidakseimbangan data menggunakan SMOTE.
  - Menggunakan feature selection (Chi-square) untuk meningkatkan efisiensi dan akurasi.
  - Mengembangkan aplikasi interaktif berbasis Streamlit untuk simulasi input dan prediksi real-time.

# Dataset
- Sumber: UCI Machine Learning Repository

  📎 Online Shoppers Purchasing Intention Dataset
- Jumlah data: 12.330 sesi kunjungan pengguna
- Label target: Revenue (TRUE = membeli, FALSE = tidak membeli)
- Imbalanced: ~15.5% sesi berakhir dengan pembelian

# Tahapan Project
1. Pre-Processing
   - Encoding: One-Hot Encoding untuk Month, VisitorType; Label Encoding untuk Weekend dan Revenue.
   - Normalisasi: Menggunakan StandardScaler.
   - Handling Imbalanced: Resampling dengan SMOTE.
2. Feature Selection
   Metode Chi-square (χ²) digunakan untuk memilih 20 fitur paling relevan terhadap target Revenue.
3. Modeling
   - Algoritma: Support Vector Machine (SVM)
   - Fungsi loss: Hinge Loss + L2 Regularisasi
   - Optimisasi: Gradient Descent (Batch) selama 1000 epoch
   - Evaluasi: Accuracy, Precision, Recall, dan F1-Score
4. Antar Muka
    - Dibuat menggunakan Streamlit
    - Fitur:
      1. Login / Sign-Up Otomatis
      2. Input Manual atau Otomatis (Random Generate)
      3. Prediksi niat beli (Will Buy / Won’t Buy)
      4. Riwayat prediksi
      5. Informasi sistem
5. Hasil Prediksi

| Label          | Precision | Recall | F1-score | Support |
|----------------|-----------|--------|----------|---------|
| 0 (tidak beli) | 0.94      | 0.89   | 0.92     | 3127    |
| 1 (akan beli)  | 0.54      | 0.72   | 0.61     | 572     |

    - Akurasi keseluruhan: 86.1%
    - Model efektif mengenali pengguna yang akan membeli (Recall 72%)
    - Masih ada potensi untuk meningkatkan precision dengan teknik lanjutan
