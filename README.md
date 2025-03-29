
# Analisis Prediksi Risiko Pinjaman

Proyek ini bertujuan untuk menganalisis dan memprediksi risiko pinjaman menggunakan dataset yang berisi informasi kredit dari berbagai peminjam dari IDX/Partners periode 2007 - 2014. Data ini mencakup lebih dari 466.285 entri dengan 75 fitur, termasuk informasi keuangan, riwayat kredit, dan variabel lain yang mempengaruhi kelayakan kredit.


## Teknologi yang digunakan 

- `Python` untuk pemrosesan data dan analisis.

- `Pandas` & `NumPy` untuk manipulasi data.

- `Matplotlib` & `Seaborn` untuk visualisasi data.

- `Scikit-learn` untuk pemodelan machine learning.


## Langkah-Langkah Analisis

a. Data Understanding

- Dataset memiliki 466.285 baris dan 75 kolom.

- Mayoritas kolom bertipe object (54 kolom) dan sisanya float64 (21 kolom).

- Banyak nilai yang hilang (missing values), terutama di kolom seperti open_il_6m dan inq_last_12m.

- Beberapa kolom numerik tersimpan sebagai object, seperti loan_amnt, funded_amnt, dan int_rate, sehingga perlu dikonversi.

- Tidak ditemukan data duplikat dalam dataset.

b. Data Cleaning

- Menghapus atau mengimputasi nilai yang hilang.

- Mengonversi kolom dengan tipe data tidak sesuai.

- Menghapus fitur yang memiliki data kosong dalam jumlah besar atau yang tidak relevan.

c. Exploratory Data Analysis (EDA)

- Analisis distribusi pinjaman berdasarkan kategori peminjam.

- Korelasi antara suku bunga (int_rate) dengan kemungkinan gagal bayar.

- Pengaruh jumlah pinjaman terhadap tingkat risiko.

- Visualisasi distribusi kredit yang disetujui dan yang gagal bayar.

d. Model Machine Learning

- Menggunakan algoritma Machine Learning seperti Random Forest, Logistic Regression, dan Gradient Boosting untuk memprediksi risiko pinjaman.

- model Gradient Boosting Classifier memiliki akurasi tertinggi sebesar 89.04%, sehingga dipilih sebagai model terbaik untuk prediksi risiko pinjaman.

- Metrik evaluasi meliputi AUC-ROC, Accuracy, dan Recall.

e. Feature Importance

Model Gradient Boosting Classifier digunakan untuk menentukan fitur paling berpengaruh dalam prediksi risiko pinjaman. Beberapa fitur dengan importance tertinggi meliputi:

- last_pymnt_d - Tanggal pembayaran terakhir, yang berkontribusi besar dalam menentukan kelayakan kredit.

- int_rate - Suku bunga pinjaman, semakin tinggi suku bunga semakin tinggi risiko gagal bayar.

- tot_cur_bal - Total saldo kredit saat ini, menunjukkan kesehatan finansial peminjam.

- dti - Debt-to-Income Ratio, rasio utang terhadap pendapatan yang sangat mempengaruhi kemungkinan gagal bayar.

- inq_last_6mths - Jumlah permintaan kredit dalam 6 bulan terakhir, menandakan seberapa sering peminjam mencari pinjaman baru.



## Insight Bisnis 

a. Kualitas Kredit Berdasarkan Riwayat Keuangan

- Peminjam dengan tingkat utang tinggi (debt-to-income ratio) cenderung memiliki tingkat gagal bayar yang lebih tinggi.

- Pinjaman dengan bunga tinggi (int_rate) lebih sering mengalami gagal bayar, menunjukkan bahwa suku bunga dapat digunakan sebagai indikator risiko.

b. Pentingnya Data Lengkap dalam Evaluasi Kredit

- Banyaknya missing values pada variabel terkait pinjaman dan kredit menunjukkan pentingnya pengelolaan data yang lebih baik dalam industri perbankan.

- Data tidak lengkap dapat menyebabkan model prediksi kurang akurat.

c. Strategi Mitigasi Risiko

- Bank dapat menggunakan model prediksi ini untuk menyaring calon peminjam berdasarkan skor risiko.

- Menetapkan batasan tertentu untuk rasio utang terhadap pendapatan guna mengurangi potensi gagal bayar.

- Memberikan penyesuaian suku bunga berdasarkan probabilitas gagal bayar untuk mengelola risiko lebih baik.


## Kesimpulan

Setelah pemodelan diterapkan:

- Jumlah pinjaman buruk menurun dari 466,285 menjadi 51,758 (penurunan 88.9%).

- Pinjaman baik meningkat menjadi 414,527.

- Model mampu mengklasifikasikan ulang sebagian besar pinjaman buruk sebagai pinjaman baik dengan akurasi tinggi.

- Hasil ini menunjukkan bahwa model dapat meningkatkan efisiensi manajemen risiko kredit dan membantu perusahaan dalam mengurangi kredit macet serta meningkatkan profitabilitas.

