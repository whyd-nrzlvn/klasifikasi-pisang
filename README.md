# Klasifikasi Tingkat Kematangan Pisang 🍌

Sebuah proyek untuk melakukan klasifikasi tingkat kematangan buah pisang secara otomatis menggunakan *Deep Learning*. Proyek ini membandingkan performa dari tiga arsitektur *Convolutional Neural Network* (CNN) yang populer—**MobileNet**, **InceptionV3**, dan **DenseNet201**—dengan dua variasi *head* klasifikasi yang berbeda.

## 🎯 Latar Belakang

Proses penyortiran buah di industri seringkali bersifat manual, yang dapat menyebabkan inkonsistensi dan inefisiensi. Proyek ini bertujuan untuk menciptakan solusi otomatis yang objektif dan terukur menggunakan *Computer Vision* untuk mengkategorikan pisang ke dalam tiga kelas: **Mentah**, **Matang**, dan **Terlalu Matang**.

Eksperimen ini secara sistematis membandingkan 6 variasi model untuk menemukan arsitektur yang paling optimal untuk tugas ini.

## 📂 Struktur Proyek

├── src/                # Kode sumber utama yang fleksibel
│   ├── data_loader.py  # Fungsi untuk memuat dan augmentasi data
│   ├── models.py       # "Pabrik" untuk membuat 6 variasi model
│   └── train.py        # Skrip utama untuk menjalankan eksperimen
├── saved_models/       # Tempat menyimpan model terlatih (.h5)
├── .gitignore          # File yang diabaikan oleh Git
├── README.md           # Anda sedang membacanya
└── requirements.txt    # Daftar library yang dibutuhkan

## ⚙️ Cara Menjalankan
Clone Repository Ini

Bash

git clone https://github.com/whyd-nrzlvn/klasifikasi-pisang.git
cd klasifikasi-pisang
Install Semua Library yang Dibutuhkan
Pastikan Anda memiliki Python dan pip terinstall. Jalankan perintah ini di terminal untuk menginstall semua library yang diperlukan.

Bash

pip install -r requirements.txt
Jalankan Training Model
Gunakan skrip src/train.py untuk melatih model. Anda bisa memilih arsitektur dan tipe head melalui command-line.

--base_model: Pilih antara mobilenet, inception, atau densenet.

--head_type: Pilih antara original atau modified.

--data_dir: Wajib diisi, arahkan ke path folder dataset Anda.

Contoh Perintah:

Melatih InceptionV3 dengan head original:

Bash

python src/train.py --base_model inception --head_type original --data_dir "path/ke/data"

Melatih DenseNet dengan head modifikasi:

Bash

python src/train.py --base_model densenet --head_type modified --data_dir "path/ke/data"
Model yang sudah dilatih akan disimpan secara otomatis di dalam folder saved_models/ dengan nama yang sesuai (misal: inception_original.h5).

## 💾 Dataset

Dataset yang digunakan dalam proyek ini terdiri dari 1000 gambar pisang yang dibagi menjadi tiga kelas. Dataset tidak disertakan langsung di dalam repository ini karena ukurannya yang besar.

Untuk menjalankan training, Anda perlu mengunduh dataset secara terpisah.

1.  **Unduh dataset** dari link berikut: [Link Google Drive Anda]
2.  Saat menjalankan skrip training, arahkan argumen `--data_dir` ke lokasi folder hasil ekstraksi tersebut.

## 🛠️ Dibangun Dengan
* **TensorFlow / Keras**
* **Python 3.x**
* **Scikit-learn**
* **NumPy**

## 🧑‍💻 Penulis
* **Nama:** Wahyudi Nurzulivan
* **LinkedIn:** www.linkedin.com/in/wahyudi-nurzulivan-8a764b364
