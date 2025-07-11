# Analisis Sentimen Mengenai Kebijakan Anggaran Pendidikan di Twitter/X

Repositori ini berisi kode dan data untuk studi kasus analisis sentimen netizen di platform X (sebelumnya Twitter) terhadap topik **"anggaran pendidikan"** di Indonesia. Proyek ini disajikan dalam format Jupyter Notebook (`.ipynb`) dan mencakup seluruh alur kerja *machine learning*, mulai dari pengambilan data, pra-pemrosesan, pelabelan otomatis, pelatihan model, hingga evaluasi dan visualisasi hasil.

---

## 📈 Alur Kerja Proyek

Proyek ini dibagi menjadi beberapa tahapan yang dieksekusi secara berurutan melalui Jupyter Notebook:

1.  **Pengambilan Data (`scrapping_tweets.ipynb`)**
    * Proses *scraping* data dilakukan dari platform X menggunakan `Selenium`.
    * Kata kunci yang digunakan adalah `"anggaran pendidikan"` untuk mendapatkan tweet yang relevan.
    * Data yang diambil meliputi nama pengguna, isi tweet, dan waktu unggah.
    * Hasilnya disimpan dalam file `tweets_data.csv`.

2.  **Pra-pemrosesan Data (`data_preprocessing.ipynb`)**
    * Data tweet yang mentah dibersihkan dari *noise* seperti URL, *mention*, *hashtag*, tanda baca, dan angka.
    * Teks kemudian diubah menjadi huruf kecil (*lowercase*), di-tokenisasi, dan *stopwords* Bahasa Indonesia dihapus menggunakan pustaka `NLTK`.
    * Data yang sudah bersih disimpan ke file `tweets_cleaned.csv`.

3.  **Pelabelan Sentimen Otomatis (`data_labelling.ipynb`)**
    * Setiap tweet diberi label sentimen (positif, netral, atau negatif) menggunakan model *pre-trained* **`indolem/indobertweet-base-uncased`** dari Hugging Face Transformers.
    * Tweet beserta label sentimennya disimpan ke file `tweets_with_label.csv`.

4.  **Pelatihan dan Perbandingan Model (`sentiment_analysis_with_multiple_model.ipynb`)**
    * Teks diubah menjadi fitur numerik menggunakan **TF-IDF Vectorizer** dari `scikit-learn`.
    * Beberapa model *machine learning* klasik dilatih dan dibandingkan, antara lain:
        * `Logistic Regression`
        * `Multinomial Naive Bayes`
        * `Linear SVC` (SVM)
        * `Random Forest Classifier`
        * `KNeighbors Classifier` (KNN)
    * Laporan klasifikasi dari semua model disimpan dalam satu file `all_classification_reports.csv`.

5.  **Visualisasi dan Analisis Hasil (`visualization_of_classification_model_evaluation.py`)**
    * Membuat berbagai visualisasi untuk menganalisis data dan membandingkan performa model menggunakan `Matplotlib` dan `Seaborn`. 
    * Visualisasi mencakup perbandingan akurasi, F1-Score, *Word Cloud*, tren waktu, dan *heatmap* frekuensi kata. 

---

## 🛠️ Teknologi dan Modul Utama

* **Pengambilan Data**: `selenium`
* **Manipulasi Data**: `pandas`
* **Pra-pemrosesan Teks**: `nltk`, `re`
* **Model Deep Learning (Pelabelan)**: `torch`, `transformers`
* **Model Machine Learning Klasik**: `scikit-learn` 
* **Visualisasi Data**: `matplotlib`, `seaborn`, `wordcloud` 

---

## 🗂️ Struktur File

* `scrapping_tweets.ipynb`: Notebook untuk mengambil data dari Twitter/X.
* `data_preprocessing.ipynb`: Notebook untuk membersihkan dan memproses teks tweet.
* `data_labelling.ipynb`: Notebook untuk memberikan label sentimen.
* `sentiment_analysis_with_multiple_model.ipynb`: Notebook untuk melatih dan mengevaluasi model ML.
* `visualization_of_classification_model_evaluation.ipynb`: Notebook untuk membuat visualisasi.
* `requirements.txt`: Daftar semua pustaka Python yang dibutuhkan.
* `tweets_data.csv`: Data mentah hasil *scraping*.
* `tweets_cleaned.csv`: Data setelah proses pembersihan.
* `tweets_with_label.csv`: Data yang telah memiliki label sentimen.
* `all_classification_reports.csv`: Laporan klasifikasi dari semua model.

---

## 🚀 Cara Menjalankan (Versi .ipynb)

1.  **Clone Repositori**
    ```bash
    git clone [https://github.com/andirakha/Sentimen-Netizen-Twitter-Anggaran-Pendidikan.git](https://github.com/andirakha/Sentimen-Netizen-Twitter-Anggaran-Pendidikan.git)
    cd Sentimen-Netizen-Twitter-Anggaran-Pendidikan
    ```

2.  **Instalasi Dependensi**
    Sangat disarankan untuk membuat *virtual environment*. Instal semua pustaka yang dibutuhkan menggunakan `pip`.
    ```bash
    pip install -r requirements.txt
    ```
    Anda juga perlu menginstal Jupyter jika belum ada.
    ```bash
    pip install notebook
    ```

3.  **Buka Jupyter Notebook**
    Jalankan perintah berikut di terminal Anda, yang akan membuka antarmuka Jupyter di browser.
    ```bash
    jupyter notebook
    ```

4.  **Jalankan Notebook secara Berurutan**
    Buka dan jalankan sel-sel kode di dalam setiap file `.ipynb` sesuai urutan alur kerja di atas.

    **Catatan Penting**: Pastikan Anda menjalankan semua sel di dalam satu notebook dari atas ke bawah agar alur kerja tetap konsisten.
