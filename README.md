# Dataset Source 
https://www.kaggle.com/datasets/subhamjain/loan-prediction-based-on-customer-behavior?select=Training+Data.csv

# Loan-Prediction-Based-on-Customer-Behavior
Create Model to Predict who possible Defaulters are for the Consumer Loans Product.
Model machine learning untuk memprediksi disetujui atau tidaknya pinjaman berdasarkan perilaku pelanggan

### Deskripsi
Rakamin Final Project oleh group 6 Batch 23

### Background
Bank memberikan pinjaman kepada nasabahnya, dan telah terdapat 252000 nasabah yang telah melakukan pinjaman. Terdapat 12,3% nasabah tidak mampu membayar pinjaman.

### Objective & Methods
- Goals : Menghindari pemberian pinjaman terhadap nasabah yang berpotensi gagal bayar.
- Metode : Membuat model yang dapat memprediksi nasabah yang berpotensi gagal bayar.
- Objektif Bisnis : - Mengurangi persentase nasabah yang gagal bayar menjadi 8%.
                    - Mengurangi jumlah loan loss (pinjaman yang tidak dikembalikan).

### EDA
- Terdapat 252000 baris dengan 13 kolom yang terdiri 7 data integer dan 6 data object
- Tidak terdapat data null, dan tidak terdapat data yang aneh.
- Kolom numerik terdiri dari : income, age, experience, current_job_yrs, current_house_yrs 
- Kolom kategorik terdiri dari: married/single, house_ownership, car_ownership, profession, city, state, dan risk_flag
- Tidak terdapat outlier pada data
- Feature age, income, experience, dan current_house_yrs bentuk distribusinya uniform
- Feature current_job_yrs positively skewed
- Feature dan label (risk_flag) tidak berkorelasi secara linier
- Berdasarkan nilai korelasinya dengan target, feature yang mungkin dipertahankan adalah age, dan experience

### Data Preprocessing
- Tidak terdapat outlier, dan data duplikat
- Dilakukan normalization pada feature numerik dan standardization pada feature current_job_yrs
- Dilakukan label encoding pada feature married/singgle dan car_ownership
- Dilakukan one-hot encoding pada feature house_ownership
- Handle class imbalance dengan SMOTE risk_flag

### Modeling
- Menggunakan Algoritma Random Forest Classifier
- Pemodelan fokus terhadap Metric Recall untuk membuat Nilai False Negative tidak terlalu besar
- False Negative adalah Nasabah yang Akan Gagal Bayar tetapi diprediksi oleh model Tidak Akan Gagal Bayar
- Score Recall sudah memiliki nilai yang cukup baik 
- Dengan melakukan Feature Selection Berdasarkan Feature Impostance dapat membantu memperbaiki Score Recall selama pemodelan
- Setelah dilakukan Hyperparameters Tuning, selisih antara Recall Train dan Recall Test mengalami penurunan meskipun mengakibatkan Score Test menurun
- Disarankan untuk mengumpulkan ulang data - data pada Dataset sehingga Label menjadi lebih Balance dan dapat membantu proses Pemodelan

### Business Impact
- Dapat menurunkan persentase Nasabah yang Gagal Bayar menjadi 2,85 %
- Dapat meningkatkan Profit Bank karena berhasil mencegah Loan Loss akibat Nasabah yang Gagal Bayar
- Dapat mempercepat proses evaluasi Peminjaman yang diajukan oleh Nasabah sehingga membantu kinerja dari Tim Kredit Bank
