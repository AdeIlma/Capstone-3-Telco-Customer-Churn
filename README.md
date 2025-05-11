

---

#- Telco Customer Churn Prediction
## Business Understanding:
Perusahaan Telco adalah penyedia layanan telekomunikasi berbasis langganan yang menghadapi tantangan dalam mempertahankan pelanggan karena meningkatnya jumlah pelanggan yang berhenti menggunakan layanan (churn). Untuk menjaga pertumbuhan dan stabilitas pendapatan, perusahaan dapat memilih antara menarik pelanggan baru atau mempertahankan yang sudah ada—di mana mempertahankan pelanggan terbukti lebih hemat biaya. Untuk itu, proyek ini memanfaatkan pendekatan klasifikasi menggunakan Machine Learning, yang memungkinkan perusahaan memprediksi apakah seorang pelanggan berpotensi churn atau tidak berdasarkan data historis seperti lama berlangganan, jenis kontrak, dan layanan yang digunakan. Dengan prediksi ini, perusahaan dapat mengambil tindakan yang lebih proaktif dan efisien dalam menjaga loyalitas pelanggan.
## Problem Stament 
- Bagaimana memprediksi pelanggan yang berisiko berhenti berlangganan (churn) pada perusahaan telekomunikasi?

- Model klasifikasi apa yang paling efektif untuk memprediksi churn pelanggan?

- Faktor-faktor apa saja yang paling berpengaruh terhadap keputusan pelanggan untuk berhenti berlangganan?

## Goals
Tujuan dari proyek ini adalah untuk membantu perusahaan telekomunikasi mengidentifikasi pelanggan yang kemungkinan besar akan berhenti berlangganan (churn) dengan menggunakan model klasifikasi berbasis Machine Learning. Dengan memanfaatkan data pelanggan yang sudah ada, seperti lama berlangganan, jenis layanan, dan pola penggunaan, model ini diharapkan dapat memberikan prediksi yang akurat. Hasil prediksi ini akan membantu perusahaan mengambil langkah lebih cepat dan tepat untuk mempertahankan pelanggan, mengurangi tingkat churn, dan menjaga kestabilan pendapatan

## Deskripsi Proyek

Proyek ini bertujuan untuk memprediksi churn pelanggan pada perusahaan telekomunikasi menggunakan **machine learning**. Dataset yang digunakan adalah `data_telco_customer_churn.csv`, yang berisi informasi pelanggan seperti layanan yang digunakan, lamanya berlangganan, tagihan bulanan, dan status churn.

## Dataset

* Nama file: `data_telco_customer_churn.csv`
* Target variabel: `Churn` (Yes/No)
* Tipe data: Campuran numerik dan kategorikal
* Permasalahan utama: **Data tidak seimbang** (jumlah pelanggan yang churn lebih sedikit)

## Tahapan Eksperimen

### 1. Penanganan Ketidakseimbangan Data

* Ditemukan bahwa data `Churn` tidak seimbang.
* Solusi: dilakukan teknik **resampling (oversampling atau ADASYN)** untuk menyeimbangkan data antara pelanggan yang churn dan tidak.

### 2. Model Awal dengan Semua Fitur

* Beberapa model dicoba, termasuk:

  * Logistic Regression
  * Random Forest
  * Decision Tree
* **Logistic Regression** memberikan hasil terbaik setelah dilakukan resampling.

### 3. Feature Selection

* Dilakukan eksperimen menggunakan **Logistic Regression** dengan dan tanpa feature selection.
* Hasil: Menggunakan **seluruh fitur** menghasilkan performa yang lebih baik dibandingkan feature selection sederhana.

### 4. Seleksi Fitur Berdasarkan Korelasi

* Digunakan **analisis korelasi** antar fitur untuk memilih fitur berdasarkan nilai korelasi yang tinggi terhadap Churn
* Akurasi meningkat, namun **recall menurun**, yang menunjukkan trade-off antara kedua metrik.

### 5. Hyperparameter Tuning

* Dilakukan **tuning hyperparameter** pada Logistic Regression.
* Setelah tuning, terdapat **penurunan recall dan F2-score** meskipun akurasi sedikit meningkat.

## Hasil Evaluasi (Final Model)

Model akhir menggunakan **Logistic Regression + semua fitur + resampling ADASYN**. Hasil dari confusion matrix:

* **True Negative (TN):** 481
* **False Positive (FP):** 232
* **False Negative (FN):** 40
* **True Positive (TP):** 218

## Metrik Evaluasi

Model dievaluasi menggunakan:

* **Accuracy**
* **Precision**
* **Recall** (fokus utama karena kasus churn penting untuk ditangani)
* **F2-Score**

## Kesimpulan

Model Logistic Regression terbukti paling stabil dan konsisten untuk dataset ini. Meski ada peningkatan akurasi pada beberapa metode, penurunan recall menyebabkan dipilihnya model yang mampu menjaga keseimbangan deteksi churn dengan baik.

---

Jika kamu ingin saya bantu buatkan versi `.md` atau file README yang bisa langsung disalin ke GitHub, tinggal bilang saja. Mau README-nya ditambahkan bagian instalasi dan cara menjalankan kode juga?
