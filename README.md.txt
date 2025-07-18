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

## ⚙️ Cara Menjalankan Eksperimen

Skrip training dirancang agar fleksibel, memungkinkan Anda untuk melatih model apa pun melalui argumen di command line.

1.  **Clone repository ini:**
    ```bash
    git clone [https://github.com/](https://github.com/)[NAMA_USER_ANDA]/klasifikasi-pisang.git
    cd klasifikasi-pisang
    ```

2.  **Install semua library yang dibutuhkan:**
    ```bash
    pip install -r requirements.txt
    ```

3.  **Jalankan Training:**
    Gunakan perintah `python src/train.py` dengan flag `--base_model`, `--head_type`, dan `--data_dir`.

    * `--base_model`: Pilih antara `mobilenet`, `inception`, atau `densenet`.
    * `--head_type`: Pilih antara `original` atau `modified`.
    * `--data_dir`: Path menuju folder dataset Anda.

    **Contoh Perintah:**

    * Melatih **InceptionV3** dengan *head* **original**:
        ```bash
        python src/train.py --base_model inception --head_type original --data_dir "path/ke/data"
        ```

    * Melatih **DenseNet** dengan *head* **modifikasi**:
        ```bash
        python src/train.py --base_model densenet --head_type modified --data_dir "path/ke/data"
        ```

    * Jika tidak ada flag, defaultnya akan melatih **MobileNet** dengan *head* **modifikasi**:
        ```bash
        python src/train.py --data_dir "path/ke/data"
        ```
    Model yang sudah dilatih akan disimpan secara otomatis di dalam folder `saved_models/` dengan nama yang sesuai (misal: `inception_original.h5`).

## 🛠️ Dibangun Dengan
* **TensorFlow / Keras**
* **Python 3.x**
* **Scikit-learn**
* **NumPy**

## 🧑‍💻 Penulis
* **Nama:** Wahyudi Nurzulivan
* **LinkedIn:** www.linkedin.com/in/wahyudi-nurzulivan-8a764b364