# Overview AI dan ML

AI (_artificial intelligence_) dan ML (_machine learning_) adalah bidang ilmu
yang berhubungan erat dengan data dan algoritma. Teknik dan penerapan dari AI
dan ML cukup beragam dan sudah mulai terasa manfaatnya di kehidupan
sehari-hari. ML adalah subset dari AI yang melingkupi upaya penggunaan metode
dan algoritma untuk mempelajari data dan menemukan pola-pola di dalamnya, sehingga
dapat dibuat model yang bisa digunakan untuk prediksi pada data-data baru
(generalisasi). Di dalam ML sendiri terdapat spesialisasi lanjutan yaitu
DL (_deep learning_) yang memadukan proses ekstraksi fitur ke dalam model itu
sendiri, sehingga mengurangi kebutuhan untuk melakukan ekstraksi fitur manual.

## Unsupervised

_Unsupervised learning_ adalah pendekatan ML yang melakukan proses pembelajaran
dari data yang tidak berlabel. Model belajar dari karakteristik data secara
langsung dan tanpa arahan dan pengawasan dari manusia. Model mendapatkan pola
dari kesamaan dan perbedaan antara poin-poin data dan mengelompokkan data ke
dalam kluster-kluster yang bermanfaat dalam upaya memahami data lebih dalam.

### Clustering

_Clustering_ adalah proses mengkategorikan data menjadi kluster-kluster atas
dasar kesamaan dan perbedaan poin-poin data. _Clustering_ digunakan ketika
seorang analis data ingin mendapatkan _insight_ dari data berdasarkan pola
dan pengelompokannya. Contohnya adalah untuk tujuan mencari segmentasi
pelanggan dari sebuah dataset perusahaan elektronika. Dengan _clustering_,
analis data dapat mengkategorikan pelanggan perusahaan tersebut menjadi
kelompok-kelompok yang memiliki sifat-sifat yang unik dan memungkinkan
perusahaan untuk mengambil keputusan dan strategi yang tepat untuk
menangani segmen-segmen pelanggan tersebut.

![Ilustrasi clustering 1](img/clustering-gfg.jpg)
![Ilustrasi clustering 2](img/clustering2-gfg.jpg)

Sumber: https://www.geeksforgeeks.org/clustering-in-machine-learning/

_Clustering_ dibagi menjadi 2 tipe, yaitu "hard" _clustering_ dan "soft"
_clustering_. Perbedaan keduanya yaitu pada _hard clustering_, setiap poin
data masuk ke suatu kluster secara mutlak atau tidak sama sekali. Sedangkan
_soft clustering_ menggunakan angka probabilitas untuk menentukan keanggotaan
kluster suatu poin data. Contoh: terdapat 2 kluster K1 dan K2. Pada
_hard clustering_, poin P1 akan masuk ke K1 atau K2. Pada _soft clustering_,
sebagai contoh P1 berpeluang masuk ke K1 sebesar 0.82 dan ke K2 sebesar
0.18.

#### Penggunaan Teknik Clustering

Kegunaan _clustering_ meliputi, namun tidak terbatas pada:

- Segmentasi pasar: data aktivitas pengguna internet dimodelkan oleh pengiklan
  untuk meningkatkan efektivitas dan relevansi iklan kepada pengguna.
- Analisis keranjang pasar: data penjualan produk digunakan oleh supermarket
  untuk memberikan penawaran promosi yang lebih menarik dan juga untuk
  manajemen stok barang yang lebih _data driven_.
- Analisis jaringan sosial: digunakan dalam menyediakan rekomendasi teman dan
  konten berdasarkan karakteristik akun pengguna.
- Pencitraan medis: _clustering_ digunakan untuk menentukan daerah-daerah tubuh
  yang terkena penyakit, berdasarkan karakteristik yang tampak pada citra medis.
- Deteksi anomali: _clustering_ dapat dimanfaatkan untuk untuk mendeteksi
  adanya pencilan atau _outlier_ dalam data.
- Penyederhanaan dataset yang kompleks: _feature set_ yang rumit dapat
  disederhanakan menjadi kluster-kluster yang unik dan lebih sederhana.

#### Jenis-Jenis Algoritma Clustering

Algoritma clustering ada beberapa macam, di antaranya:

- _Centroid-based clustering_ (_partitioning methods_)
- _Density-based clustering_ (_model-based methods_)
- _Connectivity-based clustering_ (_hierarchical clustering_)
- _Distribution-based clustering_

##### Centroid-based Clustering

_Centroid-based clustering_ meng-klusterkan data berdasarkan jaraknya.
Jarak Euclidian, jarak Manhattan, atau jarak Minkowski sering digunakan
sebagai ukuran kedekatan / kejauhan poin-poin data.

![Centroid clustering distance](img/euclidean-manhattan-minkowski-dist.jpg)

Sumber: https://www.kdnuggets.com/2023/03/distance-metrics-euclidean-manhattan-minkowski-oh.html

Kelemahan dari _clustering_ tipe ini adalah perlunya untuk menentukan
jumlah kluster yang paling optimal. Hal tersebut dapat dilakukan dengan
bantuan teknik _elbow method_ maupun _silhouette method_.

Algoritma yang tergolong dalam tipe _clustering_ ini yaitu:

- K-means (menggunakan rata-rata sebagai centroid; sensitif terhadap _outlier_)
- K-medoids (menggunakan median sebagai centroid; lebih tahan _outlier_)

![K-Means](img/k-means.png)

Sumber: https://www.analyticsvidhya.com/blog/2021/04/k-means-clustering-simplified-in-python/

##### Density-based Clustering

_Density-based clustering_ meng-klusterkan data berdasarkan kerapatan
poin-poin data. Teknik ini lebih mumpuni untuk menghandle data yang
memiliki kluster-kluster yang besar dan bentuknya tidak reguler. Selain
itu, teknik ini juga bisa menentukan jumlah kluster tanpa perlu mencarinya
secara manual.

Algoritma yang sering digunakan dalam teknik _density-based clustering_ adalah
DBSCAN.

![DBSCAN](img/dbscan.gif)

Sumber: https://www.kdnuggets.com/2020/04/dbscan-clustering-algorithm-machine-learning.html

##### Connectivity-based Clustering

_Connectivity-based clustering_ meng-klusterkan data secara hirarkis (seperti
pohon). Kluster yang dihasilkan berwujud _dendrogram_ atau bagan pohon. Ada dua
pendekatan untuk tipe clustering ini, yaitu _divisive_ dan _agglomerative_
_clustering_. Pada _divisive clustering_, semua data pertama-tama dianggap
sebagai anggota dari satu kluster besar, lalu pada setiap tahap dipecah-pecah
menjadi kluster-kluster yang lebih kecil. Hal yang sebaliknya terjadi pada
pendekatan _agglomerative clustering_. Untuk mendapatkan kluster dengan jumlah
tertentu, dapat dilakukan pemotongan _dendrogram_ pada tingkat / level tertentu.

![Dendrogram](img/dendrogram.png)

Sumber: https://www.geeksforgeeks.org/difference-between-agglomerative-clustering-and-divisive-clustering/

##### Distribution-based Clustering

Pada _distribution-based clustering_, poin-poin data dikelompokkan berdasarkan
tendensinya untuk masuk ke dalam salah satu distribusi statistik, contohnya
distribusi Gaussian atau distribusi normal. Teknik ini memiliki kelebihan
dibandingkan _hard clustering_ seperti K-Means, yaitu bisa menyiratkan nilai
ketidakpastian keanggotaan kluster suatu poin data dalam bentuk probabilitas.
Hal ini memungkinkan teknik ini untuk melakukan iterasi untuk meningkatkan
nilai centroid kluster menjadi lebih optimal lagi.

![Gaussian Mixture Model](img/gaussian-mixture-model.jpg)
![Gaussian Mixture Model GIF](img/gaussian-mixture-model.gif)

Sumber: https://builtin.com/articles/gaussian-mixture-model

[Referensi _notebook_ Kaggle untuk K-Means](https://www.kaggle.com/code/kushal1996/customer-segmentation-k-means-analysis)

## Supervised

_Supervised learning_ adalah pendekatan ML yang melakukan proses pembelajaran
dari data yang diberi label. Model belajar dari karakteristik data secara terarah
menggunakan label sebagai petunjuk hubungan antara input dan output model.
Model selanjutnya digunakan untuk memprediksi atau membuat keputusan berdasarkan
data baru yang masuk.

### Klasifikasi

Klasifikasi adalah proses mengkategorikan suatu data ke dalam suatu kelompok
yang bersifat kategorikal. Contohnya adalah pengklasifikasian email sebagai
spam atau non-spam. Proses klasifikasi menggunakan label dan karakteristik
data yang sudah dipelajari sebelumnya untuk memprediksi label / kategori dari
data baru.

Klasifikasi dibagi menjadi beberapa jenis, yaitu klasifikasi biner dan klasifikasi
_multiclass_. Klasifikasi biner mengelompokkan input menjadi 2 kategori saja,
sedangkan klasifikasi _multiclass_ mengelompokkan input menjadi 3 atau lebih
kategori. Contoh klasifikasi biner yaitu menentukan apakah seseorang sedang
sakit atau sehat berdasarkan gejala dan penampilan orang tersebut. Contoh
klasifikasi multiclass yaitu menentukan spesies kucing dari dataset hewan
kucing. Selain itu, terdapat juga klasifikasi multilabel dan
_imbalanced classification_. Pada klasifikasi multilabel, suatu data bisa
masuk ke dalam beberapa jenis label sekaligus. Pada _imbalanced classification_,
data baru bisa masuk ke dalam kelas mayoritas maupun minoritas.

#### Jenis-Jenis Algoritma Klasifikasi

##### Linear Classifiers

Model linear memisahkan kelas-kelas secara linear, sederhana, dan ringan secara
komputasi. Beberapa algoritma klasifikasi linear adalah:

- Logistic Regression
- Support Vector Machines dengan kernel = ‘linear’
- Single-layer Perceptron
- Stochastic Gradient Descent (SGD) Classifier

##### Non-linear Classifiers

Model non-linear memisahkan kelas-kelas secara non-linear. Dengan algoritma tipe ini,
hubungan antara input data dan output label dapat dirumuskan lebih baik. Beberapa
algoritma klasifikasi non-linear adalah:

- K-Nearest Neighbours
- Kernel SVM
- Naive Bayes
- Decision Tree Classification
- Ensemble learning classifiers
- Random Forests
- AdaBoost
- Bagging Classifier
- Voting Classifier
- ExtraTrees Classifier
- Multi-layer Artificial Neural Networks

##### Jenis-Jenis Pembelajar dalam Klasifikasi

###### Pembelajar Malas (Lazy Learners)

Tipe pembelajar malas tidak membuat model selama pelatihan. Tipeini menyimpan
data pelatihan dan menggunakannya untuk mengklasifikasikan data baru saat prediksi.
Kelebihannya adalah cepat dalam prediksi karena tidak memerlukan komputasi tambahan.
Kekurangannya adalah kurang efektif di ruang dimensi tinggi atau dengan data
pelatihan besar. Contoh: K-nearest neighbors (KNN), case-based reasoning.

###### Pembelajar Antusias (Eager Learners)

Tipe pembelajar ini membuat model dari data pelatihan dan menggunakan model ini untuk
mengklasifikasikan data baru saat prediksi. Kelebihannya adalah lebih efektif di
ruang dimensi tinggi dan dengan dataset besar. Kekurangannya adalah membutuhkan waktu pelatihan lebih lama. Contoh: decision trees, random forests, support vector machines (SVM).

##### Evaluasi Model Klasifikasi

- Akurasi Klasifikasi: Proporsi data yang diklasifikasikan dengan benar dari total data. Bisa menyesatkan pada dataset yang tidak seimbang.
- Confusion Matrix: Tabel yang menunjukkan true positives, true negatives, false positives, dan false negatives untuk setiap kelas.
- Presisi: Proporsi true positives dari total prediksi positif.
- Recall: Proporsi true positives dari total positif aktual.
- F1-Score: Rata-rata harmonis dari presisi dan recall, berguna untuk dataset tidak seimbang.
- Kurva ROC dan AUC:
  - Kurva ROC: Plot rasio true positive rate (recall) terhadap false positive rate.
  - AUC: Luas di bawah kurva ROC, mengukur kinerja keseluruhan model.
- Cross-Validation: Teknik membagi data menjadi beberapa lipatan untuk estimasi kinerja model yang lebih robust.

##### Karakteristik Klasifikasi

- Variabel Target Kategorikal: Memprediksi variabel target yang berupa kelas diskret. Contoh: klasifikasi email spam, prediksi risiko penyakit.
- Akurasi dan Tingkat Kesalahan: Diukur dengan akurasi, presisi, recall, dan F1-score.
- Kompleksitas Model: Berkisar dari model linier sederhana hingga model non-linier yang lebih kompleks.
- Overfitting dan Underfitting: Model harus dihindari dari overfitting (terlalu cocok dengan data pelatihan) dan underfitting (tidak cukup cocok dengan data pelatihan).

##### Tahapan Klasifikasi

1. Pemahaman Masalah: Identifikasi label kelas dan hubungan antara data input dan label kelas.
2. Persiapan Data: Pengumpulan, pembersihan, dan pemisahan data menjadi set pelatihan, validasi, dan pengujian.
3. Ekstraksi Fitur: Pilih fitur relevan yang mempengaruhi label atau target.
4. Pemilihan Model: Pilih model yang sesuai berdasarkan ukuran dan kompleksitas data, serta sumber daya komputasi.
5. Pelatihan Model: Sesuaikan parameter model untuk meminimalkan kesalahan antara label kelas yang diprediksi dan yang sebenarnya.
6. Evaluasi Model: Gunakan metrik seperti Log Loss, confusion matrix, presisi, recall, dan AUC-ROC.
7. Penyetelan Model: Sesuaikan parameter atau coba model berbeda jika kinerja tidak memuaskan.
8. Penerapan Model: Terapkan model untuk prediksi data baru dan aplikasi dunia nyata.

### Regresi

Regresi adalah metode statistik yang digunakan untuk menganalisis hubungan antara
variabel target (variabel dependen) dengan variabel predictor (variabel independen).
Dari proses regresi akan didapatkan model yang paling sesuai untuk membuat prediksi
atau menarik kesimpulan dari data baru.

#### Jenis-Jenis Regresi

1. Regresi Sederhana:
   - Menggunakan satu variabel independen untuk memprediksi variabel dependen.
   - Contoh: Memprediksi berat badan berdasarkan tinggi badan.

2. Regresi Berganda:
   - Menggunakan beberapa variabel independen untuk memprediksi variabel dependen.
   - Contoh: Memprediksi harga rumah berdasarkan ukuran, lokasi, dan fitur lainnya.

3. Regresi Nonlinier:
   - Digunakan ketika hubungan antara variabel tidak linear.
   - Contoh: Hubungan kompleks yang tidak dapat diukur dengan garis lurus.

#### Algoritma Regresi

1. Regresi Linear:
   - Mengasumsikan hubungan linear antara variabel independen dan dependen.

   ![Linear regression](img/linear-regression.png)

   Sumber: https://www.analyticsvidhya.com/blog/2021/07/all-you-need-to-know-about-polynomial-regression/

2. Regresi Polinomial:
   - Menggunakan polinomial untuk menangkap hubungan non-linear.

   ![Polynomial regression](img/polynomial-regression.png)

   Sumber: https://www.analyticsvidhya.com/blog/2021/07/all-you-need-to-know-about-polynomial-regression/

3. Support Vector Regression (SVR):
   - Mencari hyperplane yang meminimalkan selisih kuadrat antara nilai yang diprediksi dan aktual.

   ![SVR](img/support-vector-regression.webp)

    Sumber: https://www.analyticsvidhya.com/blog/2020/03/support-vector-regression-tutorial-for-machine-learning/

4. Regresi Decision Tree:
   - Membangun decision tree untuk memprediksi nilai target.

5. Regresi Random Forest:
   - Menggabungkan beberapa decision tree untuk meningkatkan akurasi prediksi.

#### Teknik Regularized Regression

1. Ridge Regression:
   - Menghindari overfitting dengan menambahkan _term_ yang teregulasi dengan parameter
     alpha sehingga membantu algoritma untuk mengecilkan _weight_ sebisa mungkin.

2. Lasso Regression:
   - Menambahkan penalti yang dapat mengatur beberapa bobot menjadi nol, mengurangi
     overfitting.

#### Karakteristik Regresi

- Variabel Target Kontinu: Memodelkan nilai numerik seperti harga rumah atau berat badan.
- Pengukuran Kesalahan: Evaluasi model berdasarkan kesalahan prediksi menggunakan metrik seperti MAE, MSE, dan RMSE.
- Kompleksitas Model: Dari model linear sederhana hingga model non-linear kompleks.
- Overfitting dan Underfitting: Risiko model terlalu cocok atau tidak cocok dengan data.

#### Metrik Evaluasi Regresi

- Mean Absolute Error (MAE): Rata-rata selisih absolut antara nilai yang diprediksi dan nilai aktual.
- Mean Squared Error (MSE): Rata-rata selisih kuadrat antara nilai yang diprediksi dan nilai aktual.
- Root Mean Squared Error (RMSE): Akar kuadrat dari MSE.
- Huber Loss: Fungsi kerugian hybrid yang seimbang antara MAE dan MSE.
- Root Mean Square Logarithmic Error: Menggunakan logaritma dalam penghitungan sehingga
  lebih tahan terhadap _outlier_.
- R² Score: Mengukur seberapa baik model cocok dengan data, dari 0 hingga 1.

#### Aplikasi Regresi

- Prediksi Harga: Misalnya, memprediksi harga rumah berdasarkan fitur-fiturnya.
- Peramalan Tren: Misalnya, meramalkan penjualan produk berdasarkan data historis.
- Identifikasi Faktor Risiko: Misalnya, mengidentifikasi faktor risiko penyakit jantung.
- Pengambilan Keputusan: Misalnya, merekomendasikan investasi berdasarkan data pasar.

#### Keuntungan Regresi

- Mudah dipahami dan diinterpretasikan.
- Tahan terhadap outlier.
- Bisa menangani hubungan linear dan non-linear.

#### Kekurangan Regresi

- Mengasumsikan hubungan linear.
- Sensitif terhadap multikolinearitas.
- Mungkin tidak cocok untuk hubungan yang sangat kompleks.

[Referensi _notebook_ Kaggle Linear Regression](https://www.kaggle.com/code/mohammedezzeldean/car-price-prediction-linearregresion-lasso)

### Time Series Forecasting

Analisis dan _time series forecasting_ penting untuk memprediksi tren,
perilaku, dan fluktuasi berdasarkan data historis. Teknik ini membantu
bisnis membuat keputusan yang terinformasi, mengoptimalkan sumber daya,
dan mengurangi risiko dengan memperkirakan permintaan pasar, fluktuasi
penjualan, harga saham, dan lainnya. Analisis ini juga mendukung perencanaan,
penganggaran, dan strategi di berbagai bidang seperti keuangan, ekonomi,
kesehatan, sains iklim, dan manajemen sumber daya.

_Time series_ adalah rangkaian titik data yang dikumpulkan, direkam, atau
diukur pada interval waktu yang berurutan dan teratur.

#### Komponen Time Series

1. Trend: Gerakan jangka panjang dalam data, seperti peningkatan atau penurunan.
2. Seasonality: Fluktuasi berkala yang terjadi pada interval yang reguler.
3. Variasi Siklis: Fluktuasi jangka panjang yang tidak memiliki periode tetap.
4. Irregularitas (atau Noise): Fluktuasi acak yang tidak dapat dijelaskan oleh tren, musiman, atau siklis.

#### Visualisasi Time Series

Visualisasi time series termasuk teknik seperti line plot, seasonal plot,
histogram, density plot, autocorrelation & partial autocorrelation plot,
spectral analysis, decomposition plot dan lain-lain untuk memahami tren,
pola, dan anomali.

#### Preprocessing Time Series

Preprocessing time series melibatkan pembersihan, transformasi,
dan persiapan data untuk analisis atau peramalan.

##### Teknik Preprocessing

- Stationarity
- Differencing
- Detrending
- Deseasonalizing
- Moving Average
- Exponential Moving Average
- Missing Value Imputation
- Outlier Detection & Removal
- Time Alignment
- Data Transformation
- Scaling
- Normalization

#### Analisis & Dekompisi Time Series

Analisis dan dekomposisi deret waktu melibatkan pemisahan
data menjadi komponen-komponennya, seperti trend, seasonality,
dan residual error dalam data.

##### Teknik Analisis & Dekomposisi

- Autocorrelation Analysis
- Partial Autocorrelation Functions (PACF)
- Trend Analysis
- Seasonality Analysis
- Decomposition
- Spectrum Analysis
- Seasonal & Trend Decomposition with Loess (STL)
- Rolling Correlation
- Cross-correlation Analysis
- Box-Jenkins Method
- Granger Causality Analysis

#### Apa itu Time Series Forecasting?

Time series forecasting adalah teknik statistik untuk memprediksi
nilai masa depan dari deret waktu berdasarkan pengamatan masa lalu.

##### Algoritma Forecasting

- Autoregressive (AR) model
- ARIMA
- ARIMAX
- SARIMA
- SARIMAX
- Vector Autoregression (VAR)
- Theta Method
- Exponential Smoothing Method
- Gaussian Processes Regression
- Generalized Additive Models (GAM)
- Random Forest
- Gradient Boosting Machines (GBM)
- State Space Model
- Hidden Markov Model (HMM)
- Dynamic Linear Model (DLM)
- Recurrent Neural Network (RNN)
- Long Short-Term Memory (LSTM)
- Gated Recurrent Unit (GRU)

#### Evaluasi Time Series Forecasting

Evaluasi melibatkan pengukuran akurasi model peramalan menggunakan metrik
seperti:

- Mean Absolute Error (MAE)
- Mean Absolute Percentage Error (MAPE)
- Mean Squared Error (MSE)
- Root Mean Squared Error (RMSE)
- Forecast Bias
- Forecast Interval Coverage
- Theil's U Statistics

### Teknik Cross-Validation

- Train-Test Split
- Rolling Window Validation
- Time Series Cross-validation
- Walk-forward Validation

## Library Python untuk Analisis & Forecasting Time Series

| Library       | Area Fokus        | Keunggulan                                      | Kelemahan                                      |
|---------------|-------------------|-----------------------------------------------|------------------------------------------------|
| Statsmodels   | Statistik         | Dukungan luas untuk model klasik seperti ARIMA | Terbatas pada model statistik klasik           |
| Pmdarima      | ARIMA             | Memudahkan pemilihan dan penyesuaian ARIMA    | Terbatas pada peramalan berbasis ARIMA         |
| Prophet       | Peramalan Bisnis  | Antarmuka sederhana untuk musiman dan libur   | Kurang fleksibel untuk pola deret waktu kompleks|
| tslearn       | Pembelajaran Mesin| Algoritma pembelajaran mesin untuk klasifikasi | Terbatas pada model statistik klasik           |
| ARCH          | Ekonometrika Keuangan | Model ARCH/GARCH untuk volatilitas finansial | Fokus pada deret waktu finansial saja          |
| GluonTS       | Pembelajaran Mendalam | Model peramalan probabilistik modern         | Memerlukan pemahaman tentang MXNet             |
| PyFlux        | Pembelajaran Mendalam | Model seperti ARIMA dan GARCH dengan inferensi Bayesian | Memerlukan pengetahuan PyTorch                |
| Sktime        | Pembelajaran Mesin | Kerangka kerja terintegrasi untuk berbagai model | Masih dalam pengembangan                       |
| PyCaret        | AutoML            | Otomatisasi peramalan deret waktu              | Kontrol terbatas pada model individu           |
| Darts         | Peramalan Probabilistik | Model peramalan dengan kuantifikasi ketidakpastian | Kurva belajar yang lebih curam                 |
| Kats          | Peramalan Bayesian | Pendekatan Bayesian untuk peramalan           | Antarmuka kurang ramah pengguna                 |
| AutoTS        | Peramalan Otomatis | Otomatisasi pemilihan model dan penyetelan parameter | Kontrol terbatas pada model spesifik          |
| Scikit-learn  | Pembelajaran Mesin | Algoritma untuk regresi dan klasifikasi       | Tidak dirancang khusus untuk analisis deret waktu |
| TensorFlow    | Pembelajaran Mendalam | Kerangka mendalam untuk model kustom          | Memerlukan pengetahuan mendalam tentang deep learning |
| Keras          | API Deep Learning | API tingkat tinggi untuk model deep learning  | Memerlukan pemahaman konsep deep learning       |
| PyTorch       | Pembelajaran Mendalam | Fleksibilitas tinggi untuk prototyping        | Memerlukan pengetahuan mendalam tentang deep learning |

[Referensi _notebook_ Kaggle untuk time series forecasting](https://www.kaggle.com/code/jegun19/predictive-maintenance-time-series-forecasting)

### Object Detection



## Semi-supervised

### LLM (Large Language Model)

# Referensi

1. https://cloud.google.com/discover/what-is-unsupervised-learning
2. https://www.geeksforgeeks.org/clustering-in-machine-learning/
3. https://www.geeksforgeeks.org/getting-started-with-classification/
4. https://www.geeksforgeeks.org/regression-in-machine-learning/
5. https://builtin.com/data-science/regression-machine-learning
6. https://neptune.ai/blog/performance-metrics-in-machine-learning-complete-guide
7. https://www.geeksforgeeks.org/time-series-analysis-and-forecasting/
8. https://www.ibm.com/topics/object-detection
9. https://viso.ai/deep-learning/object-detection/
10. https://www.geeksforgeeks.org/large-language-model-llm/
