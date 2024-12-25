# Klasifikasi Penyakit Alzheimer dengan MRI

Proyek ini bertujuan untuk mengklasifikasikan tingkat demensia pada pasien Alzheimer menggunakan gambar MRI otak. Model ini digunakan untuk memprediksi tingkat keparahan demensia pasien, yang dapat membantu dalam deteksi dini dan intervensi. Model ini menggunakan arsitektur **Convolutional Neural Network (CNN)** kustom untuk mengklasifikasikan gambar MRI ke dalam empat kategori: 'Non-demented', 'Very mild demented', 'Mild demented', dan 'Moderate demented'.

## Struktur Proyek

Proyek ini menggunakan **Alzheimer MRI Disease Classification Dataset** dari Hugging Face untuk melatih dan menguji model. Model dibangun menggunakan TensorFlow dan Keras.

## Dataset

- **Nama Dataset:** Alzheimer MRI Disease Classification Dataset  
- **Sumber:** [Alzheimer MRI Disease Classification Dataset](https://www.kaggle.com/datasets/borhanitrash/alzheimer-mri-disease-classification-dataset/data)
- **Detail Dataset:**
  - **Training Set:**
    - Jumlah gambar: 5,120
    - Ukuran Gambar: 128x128x3 (gambar RGB)
  - **Test Set:**
    - Jumlah gambar: 1,280
    - Ukuran Gambar: 128x128x3 (gambar RGB)
  
Dataset ini dibagi menjadi dua bagian: data pelatihan dan data pengujian, dengan label yang terdiri dari kategori berikut:
- `0` - Mild_Demented
- `1` - Moderate_Demented
- `2` - Non_Demented
- `3` - Very_Mild_Demented

## Arsitektur Model

Model yang digunakan untuk proyek ini adalah **Custom Convolutional Neural Network (CNN)**. Model ini terdiri dari beberapa lapisan berikut:

1. **Conv2D** dengan 32 filter, ukuran kernel 3x3, dan aktivasi ReLU.
2. **MaxPooling2D**.
3. **Conv2D** dengan 64 filter, ukuran kernel 3x3, dan aktivasi ReLU.
4. **MaxPooling2D**.
5. **Flatten**.
6. **Dense** dengan 64 unit dan aktivasi ReLU.
7. **Dense** dengan 4 unit dan aktivasi Softmax (untuk klasifikasi multi-kelas).

Model ini dikompilasi menggunakan optimisasi **Adam** dan fungsi loss **categorical cross-entropy**.

### Optimizer:
- Adam (Adaptive Moment Estimation)

### Fungsi Aktivasi:
- ReLU (untuk lapisan tersembunyi)
- Softmax (untuk lapisan output)

### Pelatihan:
- Learning Rate: 0.002
- Jumlah Epochs: 20
- Early Stopping: Patience diatur ke 10 epoch

## Instalasi

Untuk menjalankan proyek ini secara lokal, pastikan Anda telah menginstal dependensi berikut:

```bash
pip install tensorflow
pip install matplotlib
pip install pandas
pip install scikit-learn
pip install huggingface_hub
```
Pastikan untuk mengubah path pada kode sesuai dengan tempat anda meyimpan. DIkarenakan saya membuat di google colab, maka path di source code mengarah ke path dimana dataset saya tersimpan di colab.

## Kesimpulan

Proyek ini menunjukkan penerapan deep learning untuk klasifikasi gambar medis, khususnya klasifikasi penyakit Alzheimer menggunakan gambar MRI. Dengan mengklasifikasikan tingkat keparahan demensia secara akurat, proyek ini bertujuan untuk membantu dalam deteksi dini, yang dapat mengarah pada manajemen dan perawatan pasien yang lebih baik.
