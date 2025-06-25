# Dokumentasi Proyek: Classification-Batik-Jawa-using-CNN

## Deskripsi Singkat

Sistem klasifikasi Batik Jawa menggunakan metode Convolutional Neural Network (CNN) untuk mengklasifikasikan gambar batik ke dalam 5 kelas berdasarkan asal daerahnya.

Dataset yang digunakan berasal dari Kaggle:  
https://www.kaggle.com/datasets/reyhanfisena/dataset-batik-jawa

---

## Indeks Proyek

- [Deskripsi Singkat](#deskripsi-singkat)
- [Fitur Utama](#fitur-utama)
- [Struktur Proyek](#struktur-proyek)
- [Roadmap Pengembangan](#roadmap-pengembangan)
- [Cara Kerja Sistem](#cara-kerja-sistem)
- [Petunjuk Penggunaan](#petunjuk-penggunaan)
- [Referensi](#referensi)
- [Acknowledgement](#acknowledgement)
- [Catatan](#catatan)

---

## Fitur Utama

- Klasifikasi gambar batik Jawa ke dalam 5 kelas daerah.
- Augmentasi dan preprocessing otomatis dataset gambar.
- Model CNN yang dapat dikustomisasi (layer, optimizer, dsb).
- Evaluasi model otomatis (classification report, confusion matrix, visualisasi akurasi & loss).
- Dapat dijalankan di Google Colab untuk kemudahan penggunaan.

---

## Struktur Proyek

```
Classification-Batik-Jawa-using-CNN/
│
├── Proyek_Klasifikasi_Batik_Jawa.ipynb         # Notebook utama (Google Colab)
├── README.md                                   # Dokumentasi proyek
├── dataset_batik/                              # Folder dataset (harus di Google Drive untuk Colab)
│     ├── kelas1/
│     ├── kelas2/
│     ├── ...
│     └── kelas5/
├── hasil_model/                                # (Opsional) Hasil training model (.h5 atau .pkl)
└── images/                                     # (Opsional) Visualisasi hasil training
```

---

## Roadmap Pengembangan

- [x] Klasifikasi dasar gambar batik dengan CNN.
- [x] Otomatisasi preprocessing dan augmentasi gambar.
- [x] Evaluasi model dengan classification report & confusion matrix.
- [ ] Implementasi EarlyStopping dan ModelCheckpoint.
- [ ] Penambahan fitur prediksi gambar baru (inference) secara interaktif.
- [ ] Deploy model ke web-app sederhana (streamlit/flask).
- [ ] Penambahan dokumentasi dan contoh visualisasi tiap kelas batik.

---

## Cara Kerja Sistem

1. **Pengambilan dan Persiapan Data**
    - Data batik diunduh dari Kaggle.
    - Dataset disimpan di Google Drive.
    - Data preprocessing menggunakan `ImageDataGenerator` (augmentasi, split training/validation).

2. **Arsitektur Model**
    - Model dibangun dengan Keras Sequential.
    - Layer: Conv2D, MaxPooling2D, Flatten, Dense, Dropout.
    - Fungsi aktivasi: ReLU (hidden), Softmax (output).

3. **Training**
    - Optimizer: Adam.
    - Loss: categorical_crossentropy.
    - Training: 30 epoch, validasi otomatis.

4. **Evaluasi dan Visualisasi**
    - Classification report & confusion matrix.
    - Plot akurasi & loss training/validation.

---

## Petunjuk Penggunaan

1. **Kebutuhan Sistem**
    - Python 3.x
    - TensorFlow & Keras
    - Google Colab (disarankan)
    - Matplotlib, Numpy, Seaborn, scikit-learn

2. **Langkah-langkah Menjalankan Project**
    - Buka notebook `Proyek_Klasifikasi_Batik_Jawa.ipynb` di Google Colab.
    - Mount Google Drive:
      ```python
      from google.colab import drive
      drive.mount('/content/drive')
      ```
    - Pastikan dataset tersedia di folder `/content/drive/MyDrive/dataset_batik`.
    - Jalankan semua sel dari atas ke bawah.
    - Hasil evaluasi dan visualisasi akan tampil di akhir proses.

---

## Referensi

- [Dataset Batik Jawa - Kaggle](https://www.kaggle.com/datasets/reyhanfisena/dataset-batik-jawa)
- [TensorFlow ImageDataGenerator Documentation](https://www.tensorflow.org/api_docs/python/tf/keras/preprocessing/image/ImageDataGenerator)

---

## Acknowledgement

- Terima kasih kepada seluruh kontributor dan user dataset Batik Jawa di Kaggle.
- Inspirasi dan referensi dari berbagai tutorial CNN image classification dengan TensorFlow/Keras.
- Didukung oleh komunitas open source Python & Machine Learning Indonesia.

---

## Catatan

- Proyek ini open for improvement, silakan fork dan kembangkan sesuai kebutuhan.
- Untuk hasil terbaik, pastikan distribusi data antar kelas seimbang.
- Jika menemukan bug atau ingin berkontribusi, silakan ajukan pull request atau issue baru.
