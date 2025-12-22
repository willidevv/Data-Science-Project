# 📘 Judul Proyek
*Deteksi Phising Link Dengan Machine Learning*

## 👤 Informasi
- **Nama:** [Alfonsus William Hamonangan Sinaga]  
- **Repo:** [...]  
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
·	Handling missing values
Tidak ada missing values
·	Removing duplicates
Tidak ada Duplikasi data
·	Handling outliers
Dikarenakan otuliers bukan suatu hal yang harus salah dalam sebuah data, maka untuk itu outliers saya pertahankan dikarenakan alasan ke-khasan dari legitmate takut hilang dan ini memungkinkan salah perhitungan saat nanti membuat model, yang dapat mengakibatkan sebuah data tidak seimbang.

- Transformasi
A.	Creating New Feature
a.	SpecialCharRatio
  Fitur ini dihitung dari rasio jumlah karakter khusus terhadap panjang URL.
  ·	Digunakan untuk merepresentasikan tingkat kompleksitas URL.
  ·	URL phishing cenderung memiliki lebih banyak karakter khusus untuk menyamarkan struktur URL.
b.	ComplexURL
  URL legitimate umumnya memiliki struktur yang lebih sederhana dibandingkan URL phishing.
  Fitur biner yang merepresentasikan kompleksitas struktur URL berdasarkan:
  ·	Jumlah subdomain yang berlebih, atau
  ·	Adanya redirect URL.
c.	HasFinancialKeyword
  Fitur ini menggabungkan beberapa indikator kata kunci finansial seperti Bank, Pay, dan Crypto.
  ·	Digunakan untuk mendeteksi target phishing yang umumnya berkaitan dengan informasi keuangan.
  ·	Nilai 1 menunjukkan adanya indikasi kata kunci finansial.
d.	LowContentQualityFlag
  Fitur ini merepresentasikan kualitas konten halaman web berdasarkan keberadaan metadata penting seperti:
  ·	Judul halaman
  ·	Deskripsi
  ·	Informasi hak cipta
  Alasan Pembuatan Fitur Baru
  Fitur-fitur ini dirancang untuk meningkatkan daya diskriminasi model dengan menangkap karakteristik struktural, semantik, dan kualitas konten yang umum ditemukan pada URL phishing.


B.	Feature Extraction
  Feature extraction dilakukan secara terbatas karena dataset PhiUSIIL sebagian besar sudah berupa fitur numerik hasil ekstraksi sebelumnya
   Ekstraksi yang Dilakukan
  a.	DomainLength: panjang karakter domain
  b.	URLCharLength: panjang URL mentah (jika tersedia)
  Ekstraksi ini digunakan untuk memberikan informasi tambahan terkait kompleksitas dan pola string URL tanpa menambah dimensi yang berlebihan.
  C.	Feature Selection
  Setelah proses pembuatan dan ekstraksi fitur, dilakukan seleksi fitur untuk mengurangi redundansi dan meningkatkan generalisasi model.
  a.	Metode yang Digunakan
  ·	Seleksi Fitur berbasis korelasi
  ·	Fitur numerik dengan korelasi tinggi (di atas threshold tertentu) diidentifikasi dan dihapus
  b.	Tujuan Feature Selection
  ·	Mengurangi multikolinearitas
  ·	Menghindari overfitting
  ·	Meningkatkan efisiensi dan interpretabilitas model
  Proses ini memastikan bahwa hanya fitur yang paling informatif dan tidak redundant yang digunakan pada tahap pemodelan.  
  - Splitting (train/val/test)  

---

# 5. 🤖 Modeling
- **Model 1 – Baseline:** [...]  
- **Model 2 – Advanced ML:** [...]  
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
