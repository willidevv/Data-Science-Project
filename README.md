# 📘 Judul Proyek
*Deteksi Phising Link Dengan Machine Learning*

## 👤 Informasi
- **Nama:** [Alfonsus William Hamonangan Sinaga]  
- **Repo:** [https://github.com/willidevv/Data-Science-Project.git]  
- **Video:** [...]  

---

# 1. 🎯 Ringkasan Proyek
- Menyelesaikan permasalahan sesuai domain  
- Melakukan data preparation  
- Membangun 3 model: **Baseline**, **Advanced**, **Deep Learning**  
- Melakukan evaluasi dan menentukan model terbaik  

---

# 2. 📄 Problem & Goals
**Problem Statements:**  
1.	Model harus bisa dapat mendapatkan hasil secara cepat
2.	Sistem harus dapat mengidentifikasi pola tautan yang mencurigakan
3.	Dibutuhkan model deep learning yang mampu belajar representasi fitur kompleks

**Goals:**  
1.	Membangun model ML dengan metode yang sesuai konteks masalah
2.	Membangun sistem ML yang mampu mengidentifikasi tautan URL di luar dataset
3.	Menggunakan metode yang sesuai dengan konteks masalah dalam merepresentasikan deep learning

---
## 📁 Struktur Folder
```
project/
│
├── data/                   # Dataset (tidak di-commit, download manual)
│
├── notebooks/              # Jupyter notebooks
│   └── ML_Project.ipynb
│
├── src/                    # Source code
│   
├── models/                 # Saved models
│   ├── model_baseline.pkl
│   ├── model_rf.pkl
│   └── model_cnn.h5
│
├── images/                 # Visualizations
│   └── r
│
├── requirements.txt        # Dependencies
├── .gitignore
└── README.md
```
---

# 3. 📊 Dataset
- **Sumber:** https://archive.ics.uci.edu/dataset/967/phiusiil+phishing+url+dataset
- **Jumlah Data:** 235795
- **Tipe:** Categorical, Integer, Continuous

### Fitur Utama
| Fitur | Deskripsi |
|------|-----------|
| ... | ... |

---

# 4. 🔧 Data Preparation
- Cleaning
Pada tahap data cleaning, tidak ditemukan missing values pada seluruh fitur sehingga tidak diperlukan proses imputasi. Selain itu, dataset juga tidak mengandung data duplikat, sehingga seluruh sampel dipertahankan untuk menjaga kelengkapan informasi. Terkait outliers, data tidak dilakukan penghapusan karena outliers tidak selalu merepresentasikan kesalahan, melainkan dapat mencerminkan karakteristik unik dari URL legitimate. Menghilangkan outliers berpotensi menghilangkan pola penting serta menyebabkan ketidakseimbangan data, yang pada akhirnya dapat berdampak negatif pada proses pembelajaran model machine learning.

- Transformasi
Pada tahap feature engineering, dilakukan tiga aktivitas utama yaitu creating new features, feature extraction, dan feature selection untuk meningkatkan kualitas representasi data pada tugas deteksi phishing URL. Pada proses creating new features, dibangun beberapa fitur baru yang dirancang untuk menangkap karakteristik khas URL phishing, antara lain SpecialCharRatio yang merepresentasikan tingkat kompleksitas URL berdasarkan rasio karakter khusus, ComplexURL sebagai fitur biner yang menunjukkan kompleksitas struktur URL berdasarkan jumlah subdomain berlebih atau keberadaan redirect, HasFinancialKeyword yang mengindikasikan adanya kata kunci finansial seperti Bank, Pay, dan Crypto, serta LowContentQualityFlag yang mencerminkan rendahnya kualitas konten halaman web berdasarkan ketiadaan metadata penting seperti judul, deskripsi, dan informasi hak cipta. Fitur-fitur ini dibuat untuk meningkatkan daya diskriminasi model dengan menangkap aspek struktural, semantik, dan kualitas konten yang umum ditemukan pada URL phishing.

Selanjutnya, feature extraction dilakukan secara terbatas karena sebagian besar fitur dalam dataset PhiUSIIL telah berupa fitur numerik hasil ekstraksi sebelumnya. Ekstraksi tambahan yang dilakukan meliputi DomainLength sebagai panjang karakter domain dan URLCharLength sebagai panjang URL mentah (jika tersedia), yang bertujuan memberikan informasi tambahan terkait kompleksitas dan pola string URL tanpa menambah dimensi fitur secara berlebihan. Terakhir, dilakukan feature selection menggunakan pendekatan berbasis korelasi untuk mengidentifikasi dan menghapus fitur numerik yang memiliki korelasi tinggi di atas ambang batas tertentu. Proses ini bertujuan mengurangi multikolinearitas, mencegah overfitting, serta meningkatkan efisiensi dan interpretabilitas model, sehingga hanya fitur yang paling informatif dan tidak redundant yang digunakan pada tahap pemodelan.

- Splitting (train/val/test)

–	Training set: 70% (~17.900 sampel)
 Digunakan untuk melatih model machine learning agar dapat mempelajari pola URL phishing dan legitimate secara optimal.
–	Validation set: 15% (~3.800 sampel)
 Digunakan untuk evaluasi sementara dan pemilihan model atau hyperparameter tanpa menyentuh data uji.
–	Test set: 15% (~3.800 sampel)

Digunakan untuk mengukur performa akhir model secara objektif terhadap data yang benar-benar belum pernah dilihat sebelumnya.
Pembagian data dilakukan menggunakan stratified split untuk menjaga proporsi kelas phishing dan legitimate tetap seimbang. Dataset dibagi menjadi data latih sebesar 70%, data validasi 15%, dan data uji 15%. Data latih digunakan untuk proses pembelajaran model, data validasi untuk evaluasi sementara, dan data uji untuk mengukur performa akhir model secara objektif. Random state ditetapkan untuk memastikan reprodusibilitas hasil.


---

# 5. 🤖 Modeling
- **Model 1 – Baseline:**
  Saya memilih Logistic Regression, dan Logistic Regression adalah algoritma klasifikasi biner yang memprediksi probabilitas suatu data termasuk ke dalam kelas tertentu dengan mengubah kombinasi linier fitur menggunakan fungsi sigmoid. Dan alasan saya memilih model ini dikarenakan model ini cocok untuk algoritma supervised khsusunya klasifikasi biner seperti deteksi phishing link.
  
- **Model 2 – Advanced ML:**
  XGBoost (Extreme Gradient Boosting) adalah algoritma ensemble berbasis gradient boosting yang membangun model secara bertahap menggunakan pohon keputusan. Setiap pohon baru dilatih untuk memperbaiki kesalahan (residual) dari model sebelumnya dengan meminimalkan fungsi loss melalui optimisasi gradien.Saya memilih model ini dikarenakan saya mempertimbangkan tentang kecepatan akurasi terhadap data dengan overfitting minim.
  
- **Model 3 – Deep Learning:** [...]  

---

# 6. 🧪 Evaluation
**Metrik:** Accuracy / F1 / MAE / MSE (pilih sesuai tugas)

### Hasil Singkat
| Model | Score | Catatan |
|-------|--------|---------|
| Baseline | [...] | |
| Advanced | [...] | |
| Deep Learning | [...] | |

---

# 7. 🏁 Kesimpulan
- Model terbaik: [...]  
- Alasan: [...]  
- Insight penting: [...]  

---

# 8. 🔮 Future Work
- [ ] Tambah data  
- [ ] Tuning model  
- [ ] Coba arsitektur DL lain  
- [ ] Deployment  

---

# 9. 🔁 Reproducibility
Gunakan environment:
