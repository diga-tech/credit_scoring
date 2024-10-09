# Laporan Proyek Machine Learning - Muhammad Radiga G

## Domain Proyek (Background)

Saat ini industri Perbankan dan Fintech mengalami kemajuan yang pesat seiring dengan kemajuan teknologi. Banyak product yang ditawarkan oleh perbankan dan Fintech seperti Tabungan, Deposito, serta Pinjaman. Pemberian pinjaman kepada individu atau perusahaan memiliki risiko gagal bayar. Rasio kredit NPL di Perbankan di Indonesia hingga Maret 2023 sebesar 2,49% . Hal tersebut membuat bank dan fintech dapat menghadapi kerugian yang tinggi akibat dari gagal bayar. Metode manual dalam menilai Credit Scoring memiliki kelemahan seperti rentan terhadap kesalahan , subjektivitas, dan butuh waktu. Hal tersebut membuat proses credit scoring tidaklah efisien.

Source: [ojk.go.id](https://ojk.go.id/id/kanal/perbankan/data-dan-statistik/laporan-profil-industri-perbankan/Documents/Laporan%20Surveillance%20Perbankan%20Indonesia%20-%20Triwulan%20I%202023.pdf)

## Business Understanding

### Problem Statements

1. Pemberian pinjaman kepada individu atau perusahaan memiliki risiko gagal bayar yang dapat menimbulkan kerugian bagi bank dan fintech fitur atau variabel apa yang dapat menekan risiko gagal bayar?

2. Metode manual dalam menilai credit scoring rentan terhadap kesalahan, memiliki tingkat subjektivitas yang tinggi, dan memerlukan waktu untuk diproses. Sehingga proses penilaian credit scoring manual tidak efisien yang dapat menghambat keputusan pinjaman yang cepat dan akurat. oleh karena itu, fitur apa yang dapat menentukan proses credit scoring agar dapat menjadi efektif dan efisien?

### Goals

1. Mengurangi Risiko Gagal Bayar: Membuat model prediktif yang dapat membantu perbankan dan fintech mengidentifikasi nasabah dengan risiko gagal bayar rendah, sehingga dapat mengurangi kerugian berdasarkan fitur atau variabel yang berkorelasi.

2. Mengembangkan sistem berbasis data dengan machine learning untuk memberikan penilaian credit scoring secara objektif, mengurangi subjektivitas, serta mempercepat proses pengambilan keputusan pinjaman. Mempertimbangkan berbagai variabel atau fitur seperti pendapatan, keterlambatan pembayaran, dan riwayat kredit untuk mengurangi tingkat kesalahan dalam penilaian.

### Solution statements

Menggunakan empat model untuk membandingkan dan memberikan solusi yang terbaik dalam membuat Credit Scoring Predictive yang efektif dan efisien. Adapun model yang digunakan adalah Random Forest, Logistic Regresion, Decision Tree, dan Gradien Boosting. Metrik evaluasi menggunakan Mean Squared Error (MSE) untuk mengukur seberapa besar model salah dalam melakukan predictive sementara R-squared digunakan untuk mengetahui seberapa baik model dalam mengevaluasi pola data.

## Data Understanding

Melakukan Data Acquisition Credit Scoring dari Kaggle https://www.kaggle.com/datasets/parisrohan/credit-score-classification/data . Dataset ini memiliki 100.000 data yang terdiri dari 28 Columns. Dataset ini menjelaskan mengenai informasi customers termasuk data-data demografi, payment behaviour, credit score. Tujuan dari project ini adalah membuat sistem yang efektif dalam melakukan prediksi peminjam berdasarkan tiga kategori Good, Standard, dan Poor.

### Variabel-variabel pada dataset adalah sebagai berikut:

- ID: Unique identifier.

- Customer_ID: ID untuk setiap konsumen.

- Month: Bulan.

- Name: Nama konsumen.

- Age: Umur Konsumen.

- SSN: Social Security Number of the customer.

- Occupation: Pekerjaan konsumen.

- Annual_Income: Pendapatan tahunan.

- Monthly_Inhand_Salary: Pendapatan bersih setiap bulan.

- Num_Bank_Accounts: Jumlah akun bank milik konsumen.

- Num_Credit_Card: Jumlah kartu kredit yang dimiliki konsumen.

- Interest_Rate: Sukuk bunga.

- Num_of_Loan: Jumlah pinjaman konsumen.

- Type_of_Loan: Tipe pinjaman konsumen.

- Delay_from_due_date: Keterlambatan bayar oleh konsumen.

- Num_of_Delayed_Payment: Jumlah dana yang telat dibayar oleh konsumen.

- Changed_Credit_Limit: limit karu kredit yang idubah.

- Num_Credit_Inquiries: Jumlah permintaan kredit yang dilakukan oleh nasabah.

- Credit_Mix: Campuran dari berbagai jenis rekening kredit yang dimiliki oleh nasabah.

- Outstanding_Debt: Jumlah Outstanding debt.

- Credit_Utilization_Ratio: Rasio kartu kredit yang dapat digunakan.

- Credit_History_Age: Umur kartu kredit.

- Payment_of_Min_Amount: Minimum pembayaran yang dilakukan.

- Total_EMI_per_month: Total Equated Monthly Installment (EMI) yang dibayar oleh konsumen.

- Amount_invested_monthly: Jumlah investasi bulanan.

- Payment_Behaviour: Cara Bayar Konsumen.

- Monthly_Balance: Jumlah saldo bulanan.

- Credit_Score: Credit score konsumen.

![Data](documents/data.png)

## Data Preparation

Pada tahap ini akan melakukan cleaning data untuk membuat credit scoring predictive. Tahap pertama menghilangkan column yang tidak dibutuhkan dalam proses pembuatan credit scoring. Tahap kedua mengubah tipe data menjadi numeric agar dapat menghilangkan missing value dan mengubah unique value. Tahap ketiga Mengubah data Credit_Mix, Payment_Behaviour, Credit_Score, dan Occupation menjadi label agar mudah dalam melakukan klasifikasi. Tahap selanjutnya Menentukan korelasi dari setiap hubungan data semakin mendekati satu maka saling terkaitan begitupun sebaliknya. Tahap akhir adalah melakukan split data untuk training dan validation.

## Modeling

**Random Forest Model**
Model Random Forest digunakan untuk membantu menangani variabel yang heterogen untuk melihat hubungan antar data. model ini merupakan model esmble learning yang menggabungkan kumpulan decision trees untuk meningkatkan akurasi dengan metrik MSE dan mengurangi overfitting dengan parameter n_estimator yang digunakan sebesar 200.

**Logistic Regression**
Logistic regresion merupakan model yang digunakan untuk memprediksi dengan dua variabel saja. Kasus credit scoring tidak sesuai dengan menggunakan logistic regresion karena memiliki multi variabel

**Decision Tree**
Decision tree merupakan model untuk melakukan klasifikasi dan regresi. Decision tree membagi dataset menjadi subset yang lebih kecil dan lebih homogen berdasarkan fitur-fitur yang paling memisahkan kelas atau nilai target.

**Gradient Boosting**
Gradient Boosting merupakan model yang berdasarkan metode ensemble dengan membangun model secara bertahap dengan menghitung nilai error, membuat decision tree, memperbaiki setiap prediksi dengan rekursi sebelum tahap final model. Adapun parameter yang digunakan n_estimators 100 learning rate 0.1.

## Evaluation

#### MSE

![mse](documents/mse.png)

#### R-Squared

![rsquared](documents/r_squared.png)

Dari hasil yang didapat, Model Random Forest dengan Mean Squared Error (MSE) sebesar 0.2027 dan R-squared sebesar 0.5545, menunjukkan bahwa model ini memiliki tingkat kesalahan yang relatif rendah dibandingkan dengan model lainnya. Sebaliknya, Logistic Regression memiliki performa paling rendah dengan MSE sebesar 0.4873 dan R-squared negatif sebesar -0.0711.

Decision Tree memiliki MSE sebesar 0.3966 dan R-squared sebesar 0.1281 menunjukkan performa yang lebih baik daripada Logistic Regression, tapi masih jauh dari Random Forest. Sementara Gradient Boosting memiliki hasil yang baik dengan MSE sebesar 0.2602 dan R-squared sebesar 0.4280, meski masih di bawah Random Forest.

Dapat disimpulkan bahwa Random Forest adalah model terbaik untuk credit scoring berdasarkan hasil MSE dan R-squared, diikuti oleh Gradient Boosting, sedangkan Logistic Regression adalah yang paling tidak efektif.
