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

_Unsupervised learning_ adalah pendekatan ML yang melakukan proses Learning
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
distribusi Gaussian Mixture Model. Teknik ini memiliki kelebihan
dibandingkan _hard clustering_ seperti K-Means, yaitu bisa menyiratkan nilai
ketidakpastian keanggotaan kluster suatu poin data dalam bentuk probabilitas.
Hal ini memungkinkan teknik ini untuk melakukan iterasi untuk meningkatkan
nilai centroid kluster menjadi lebih optimal lagi.

![Gaussian Mixture Model](img/gaussian-mixture-model.jpg)
![Gaussian Mixture Model GIF](img/gaussian-mixture-model.gif)

Sumber: https://builtin.com/articles/gaussian-mixture-model

[Referensi _notebook_ Kaggle untuk K-Means](https://www.kaggle.com/code/kushal1996/customer-segmentation-k-means-analysis)

## Supervised

_Supervised learning_ adalah pendekatan ML yang melakukan proses Learning
dari data yang diberi label. Model belajar dari karakteristik data secara terarah
menggunakan label sebagai petunjuk hubungan antara input dan output model.
Model selanjutnya digunakan untuk memprediksi atau membuat keputusan berdasarkan
data baru yang masuk.

![Supervised learning](img/supervised-learning.png)

Sumber: https://www.datacamp.com/blog/classification-machine-learning

### Klasifikasi

Klasifikasi adalah proses mengkategorikan suatu data ke dalam suatu kelompok
yang bersifat kategorikal. Contohnya adalah pengklasifikasian email sebagai
spam atau non-spam. Proses klasifikasi menggunakan label dan karakteristik
data yang sudah dipelajari sebelumnya untuk memprediksi label / kategori dari
data baru.

![Klasifikasi](img/spam-no-spam.png)

Sumber: https://www.datacamp.com/blog/classification-machine-learning

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

![binary classification](img/binary-classification.png)
![multiclass classification](img/multiclass-classification.png)
![multilabel classification](img/multilabel-classification.png)
![imbalanced classification](img/imbalanced-classification.png)

Sumber: https://www.datacamp.com/blog/classification-machine-learning

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

![conf. matrix](img/confusion-matrix.webp)
![conf. matrix 2](img/confusion-matrix2.webp)
![accuracy](img/accuracy.webp)
![precision](img/precision.webp)
![recall](img/recall.webp)
![f1-score](img/f1-score.webp)

Sumber: https://medium.com/analytics-vidhya/confusion-matrix-accuracy-precision-recall-f1-score-ade299cf63cd

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
- Forecasting Tren: Misalnya, meramalkan penjualan produk berdasarkan data historis.
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
4. Irregularitas (atau Noise): Fluktuasi acak yang tidak dapat dijelaskan oleh tren, Seasonality, atau siklis.

#### Visualisasi Time Series

Visualisasi time series termasuk teknik seperti line plot, seasonal plot,
histogram, density plot, autocorrelation & partial autocorrelation plot,
spectral analysis, decomposition plot dan lain-lain untuk memahami tren,
pola, dan anomali.

#### Preprocessing Time Series

Preprocessing time series melibatkan pembersihan, transformasi,
dan persiapan data untuk analisis atau Forecasting.

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

Analisis dan dekomposisi Time Series melibatkan pemisahan
data menjadi komponen-komponennya, seperti trend, seasonality,
dan residual error dalam data.

![time series component](img/component-of-time-series-forecast.jpg)
![time series component 2](img/time-series-components.jpg)

Sumber: https://www.springboard.com/blog/data-science/time-series-forecasting/

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
nilai masa depan dari Time Series berdasarkan pengamatan masa lalu.

![time series forecast 1](img/time-series-forecasting-overview.webp)

Sumber: https://www.springboard.com/blog/data-science/time-series-forecasting/

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

Evaluasi melibatkan pengukuran akurasi model Forecasting menggunakan metrik
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
| Pmdarima      | ARIMA             | Memudahkan pemilihan dan penyesuaian ARIMA    | Terbatas pada Forecasting berbasis ARIMA         |
| Prophet       | Forecasting Bisnis  | Antarmuka sederhana untuk Seasonality   | Kurang fleksibel untuk pola Time Series kompleks|
| tslearn       | Machine Learning| Algoritma Learning mesin untuk klasifikasi | Terbatas pada model statistik klasik           |
| ARCH          | Ekonometrika Keuangan | Model ARCH/GARCH untuk volatilitas finansial | Fokus pada Time Series finansial saja          |
| GluonTS       | Deep Learning | Model Forecasting probabilistik modern         | Memerlukan pemahaman tentang MXNet             |
| PyFlux        | Deep Learning | Model seperti ARIMA dan GARCH dengan inferensi Bayesian | Memerlukan pengetahuan PyTorch                |
| Sktime        | Machine Learning | Kerangka kerja terintegrasi untuk berbagai model | Masih dalam pengembangan                       |
| PyCaret        | AutoML            | Otomatisasi Forecasting Time Series              | Kontrol terbatas pada model individu           |
| Darts         | Forecasting Probabilistik | Model Forecasting dengan kuantifikasi ketidakpastian | Kurva belajar yang lebih curam                 |
| Kats          | Forecasting Bayesian | Pendekatan Bayesian untuk Forecasting           | Antarmuka kurang ramah pengguna                 |
| AutoTS        | Forecasting Otomatis | Otomatisasi pemilihan model dan penyetelan parameter | Kontrol terbatas pada model spesifik          |
| Scikit-learn  | Machine Learning | Algoritma untuk regresi dan klasifikasi       | Tidak dirancang khusus untuk analisis Time Series |
| TensorFlow    | Deep Learning | Kerangka mendalam untuk model kustom          | Memerlukan pengetahuan mendalam tentang deep learning |
| Keras          | API Deep Learning | API tingkat tinggi untuk model deep learning  | Memerlukan pemahaman konsep deep learning       |
| PyTorch       | Deep Learning | Fleksibilitas tinggi untuk prototyping        | Memerlukan pengetahuan mendalam tentang deep learning |

[Referensi _notebook_ Kaggle untuk time series forecasting](https://www.kaggle.com/code/jegun19/predictive-maintenance-time-series-forecasting)

### Object Detection

Object detection adalah proses dalam visi komputer yang digunakan untuk
mendeteksi adanya objek dengan kelas / jenis tertentu dalam citra digital
seperti foto maupun video. Object detection menjawab pertanyaan:

- Ada object apa saja?
- Di mana objek-objek tersebut berada?

Object detection membedakan antara objek yang dimaksud dengan lingkungan sekitar
dengan menentukan boundary / batas dari objek-objek dalam lingkungan. Object
detection melakukan proses klasifikasi dan lokalisasi dalam proses deteksinya.

![object detection](img/object-detection.webp)
![object detection gif](img/object-detection.gif)

Sumber: https://viso.ai/deep-learning/object-detection/

#### Tahapan Object Detection

1. Input Image: Proses deteksi objek dimulai dengan analisis gambar atau video.
2. Pre-processing: Gambar di-preprocess untuk memastikan format yang sesuai untuk model yang digunakan.
3. Feature Extraction: Model CNN digunakan sebagai ekstraktor fitur, model ini bertanggung jawab untuk membedah gambar menjadi beberapa wilayah dan mengambil fitur dari setiap wilayah untuk mendeteksi pola berbagai objek.
4. Classification: Setiap wilayah gambar diklasifikasikan ke dalam kategori berdasarkan fitur yang diekstraksi. Tugas klasifikasi dilakukan menggunakan SVM atau neural network lainnya yang menghitung probabilitas setiap kategori yang ada di wilayah tersebut.
5. Localization: Secara bersamaan dengan proses klasifikasi, model menentukan bounding box setiap objek yang terdeteksi. Ini melibatkan perhitungan koordinat untuk kotak yang menutupi setiap objek, sehingga secara akurat menentukan lokasinya di dalam gambar.
6. Non-max Suppression: Ketika model mengidentifikasi beberapa bounding box untuk objek yang sama, non-max suppression digunakan untuk menangani tumpang tindih ini. Teknik ini hanya menyimpan bounding box dengan skor kepercayaan tertinggi dan menghapus box lainnya yang tumpang tindih.
7. Output: Proses berakhir dengan gambar asli yang diberi tanda dengan bounding box dan label yang menggambarkan objek yang terdeteksi dan kategori yang sesuai.

#### Teknik-Teknik Object Detection

##### Teknik Tradisional

Teknik tradisional bergantung pada ekstraksi fitur manual dan teknik klasifikasi.
Beberapa contoh teknik tradisional adalah sebagai berikut:

- Haar Cascades
- Histogram of Oriented Gradients (HOG)
- Scale-Invariant Feature Transform (SIFT)

##### Teknik Deep Learning

Dalam teknik deep learning, metode deteksi objek dibagi menjadi 2 jenis, yaitu:

- Single stage detector: dalam satu fase deteksi, dihasilkan bounding box dan
  probabilitas klasifikasi kelas dari objek-objek. Contoh: YOLO (You Only Look Once),
  SSD (Single Shot Multibox Detector).
- Two stage detector: bekerja dalam dua fase, pertama, ditentukan wilayah-wilayah
  kandidat yang akan diklasifikasikan di fase kedua. Contoh: R-CNN (Regions with
  Convolutional Neural Network), Fast R-CNN, Faster R-CNN.

###### Single Stage Detectors

1. YOLO: arsitektur object detection yang memprediksi bounding box dan klasifikasi
   objek dalam satu fase. Bekerja dengan membagi citra ke dalam grid-grid dan
   memprediksi bounding box dan klasifikasi untuk setiap cell dari grid.
2. SSD: arsitektur object detection yang menggunakan feature map dari layer-layer
   CNN untuk mendeteksi objek dalam skala-skala yang berbeda. Bekerja dengan cepat
   dan hanya menggunakan 1 fase saja.

###### Two Stage Detectors

1. R-CNN: Teknik ini menggunakan algoritma selective search untuk menghasilkan 2000 proposal wilayah dari gambar, kemudian wilayah yang diusulkan diubah ukurannya dan dilewatkan melalui model CNN yang telah dilatih untuk mengekstraksi vektor fitur. Vektor fitur ini kemudian dimasukkan ke dalam classifier untuk mengklasifikasikan objek dalam wilayah tersebut.
2. Fast R-CNN: Teknik ini memproses gambar lengkap dengan CNN untuk menghasilkan peta fitur. Lapisan Region of Interest (ROI) Pooling digunakan untuk mengekstraksi vektor fitur dari peta fitur. Teknik ini menggabungkan pendekatan klasifikasi dan regresi dengan menggunakan satu jaringan fully connected untuk memberikan output baik untuk probabilitas kelas maupun koordinat bounding box.
3. Faster R-CNN: Teknik ini menggunakan Region Proposal Network (RPN) yang memprediksi batas objek dari peta fitur yang dibuat oleh CNN awal, kemudian fitur dari wilayah yang diusulkan oleh RPN dipool menggunakan ROI Pooling dan dimasukkan ke dalam jaringan yang memprediksi kelas dan bounding box.

#### Penggunaan Object Detection

- Kendaraan Otonom: Tesla Autopilot, Waymo.
- Pengawasan Publik: mendeteksi lalu lintas, plat nomor, kerumuman massa, pengenalan identitas.
- Deteksi Penyakit: mendeteksi tumor, jaringan yang rusak, dan penyakit lain.
- Robotika: tangan-tangan robotik di pabrik dilengkapi dengan fitur object detection.

## Semi-supervised

Semi-supervised learning adalah paradigma machine learning yang menggunakan
data berlabel dan data tidak berlabel. Dengan menggunakan data berlabel dan tidak
berlabel, model yang dihasilkan bisa belajar dari pola yang ada dengan berbagai
macam teknik. Contoh teknik-teknik tersebut adalah:

- Self-training: menggunakan hubungan dari data berlabel untuk melakukan pseudo-labeling pada
  data tidak berlabel dan dilakukan iterasi.
- Co-training: menggunakan banyak model yang dilatih pada kumpulan fitur yang berbeda, dan
  hasil pseudo-labeling yang bersifat _high agreement_ di antara model-model itu akan
  disimpan.
- Multiview training: model-model dilatih pada berbagai representasi data dari data yang sama.
- Generative model: Meng-generate data sintetis dengan bantuan model generative seperti GAN
  untuk dikombinasikan dengan data riil.
- Transfer learning: melakukan pre-training model dengan data berlabel yang berlimpah lalu
  melakukan fine tuning untuk tujuan tertentu dengan data berlabel yang terbatas.

### LLM (Large Language Model)

LLM atau _large language model_ adalah adalah jenis algoritma kecerdasan buatan yang menerapkan teknik Neural Network dengan banyak parameter untuk memproses dan memahami bahasa manusia atau teks menggunakan teknik self-learning. Tugas seperti pembuatan teks, penerjemahan mesin, penulisan ringkasan, pembuatan gambar dari teks, pengkodean mesin, chatbot, atau Conversational AI adalah aplikasi dari LLM. Contoh model LLM adalah Chat GPT oleh OpenAI, BERT (Bidirectional Encoder Representations from Transformers) oleh Google, dll.

Banyak teknik yang telah dicoba untuk melakukan tugas terkait bahasa alami, tetapi LLM sepenuhnya didasarkan pada metodologi deep learning. Model LLM sangat efisien dalam menangkap hubungan entitas yang kompleks dalam teks dan dapat menghasilkan teks menggunakan semantik dan sintaksis dari bahasa tertentu yang ingin digunakan.

### Gambaran Model LLM

Perkembangan LLM sepanjang waktu dapat dilihat dari perkembangan kemampuan dan
kapabilitas model, seiring dengan peningkatan jumlah dan mutu data yang tersedia
untuk dijadikan dataset training LLM:

- GPT-1 yang dirilis pada tahun 2018 mengandung 117 juta parameter dengan 985 juta kata.
- GPT-2 yang dirilis pada tahun 2019 mengandung 1,5 miliar parameter.
- GPT-3 yang dirilis pada tahun 2020 mengandung 175 miliar parameter.
- Model GPT-4 dirilis pada tahun 2023 dan mengandung triliunan parameter.

### Bagaimana LLM Bekerja?

Model Bahasa Besar (LLM) beroperasi berdasarkan prinsip deep learning, memanfaatkan arsitektur Neural Network untuk memproses dan memahami bahasa manusia.

Model ini dilatih pada dataset yang sangat besar menggunakan teknik self-learning. Inti dari fungsionalitas mereka terletak pada pola dan hubungan rumit yang mereka pelajari dari data bahasa yang beragam selama pelatihan. LLM terdiri dari beberapa lapisan, termasuk lapisan feedforward, lapisan embedding, dan lapisan attention. Mereka menggunakan mekanisme attention, seperti Self-Attention, untuk menimbang pentingnya token yang berbeda dalam sebuah urutan, memungkinkan model untuk menangkap ketergantungan dan hubungan.

### Arsitektur LLM

Arsitektur Model Bahasa Besar (LLM) ditentukan oleh sejumlah faktor, seperti tujuan desain model tertentu, sumber daya komputasi yang tersedia, dan jenis tugas pemrosesan bahasa yang akan dilakukan oleh LLM. Arsitektur umum LLM terdiri dari banyak lapisan seperti lapisan feed forward, lapisan embedding, dan lapisan attention. Sebuah teks yang di-embed di dalamnya dikolaborasikan bersama untuk menghasilkan prediksi.

#### Komponen Penting yang Mempengaruhi Arsitektur Model Bahasa Besar:

- Ukuran Model dan Jumlah Parameter
- Representasi input
- Mekanisme Self-Attention
- Tujuan Pelatihan
- Efisiensi Komputasi
- Pengodean dan Generasi Output

#### Arsitektur Model LLM Berbasis Transformer

Model berbasis transformer, yang telah merevolusi tugas pemrosesan bahasa alami, umumnya mengikuti arsitektur umum yang mencakup komponen-komponen berikut:

- Input Embeddings: Teks input di-tokenisasi menjadi unit yang lebih kecil, seperti kata atau sub-kata, dan setiap token diembed ke dalam representasi vektor kontinu. Langkah embedding ini menangkap informasi semantik dan sintaksis dari input.
- Positional Encoding: Positional encoding ditambahkan ke input embeddings untuk memberikan informasi tentang posisi token karena transformer secara alami tidak mengkode urutan token. Ini memungkinkan model memproses token sambil mempertimbangkan urutan berurutan mereka.
- Encoder: Berdasarkan teknik Neural Network, encoder menganalisis teks input dan menciptakan sejumlah hidden state yang melindungi konteks dan makna data teks. Beberapa lapisan encoder membentuk inti dari arsitektur transformer. Mekanisme Self-Attention dan Neural Network feed-forward adalah dua sub-komponen fundamental dari setiap lapisan encoder.
  - Mekanisme Self-Attention: Self-Attention memungkinkan model untuk menimbang pentingnya token yang berbeda dalam urutan input dengan menghitung skor perhatian. Ini memungkinkan model mempertimbangkan ketergantungan dan hubungan antara token yang berbeda secara kontekstual.
  - Neural Network Feed-Forward: Setelah langkah Self-Attention, Neural Network feed-forward diterapkan pada setiap token secara independen. Jaringan ini mencakup lapisan fully connected dengan fungsi aktivasi non-linear, memungkinkan model menangkap interaksi kompleks antar token.
- Decoder Layers: Dalam beberapa model berbasis transformer, komponen decoder disertakan selain encoder. Lapisan decoder memungkinkan generasi autoregresif, di mana model dapat menghasilkan output berurutan dengan memperhatikan token yang telah dihasilkan sebelumnya.
- Multi-Head Attention: Transformer sering menggunakan perhatian multi-head, di mana Self-Attention dilakukan secara bersamaan dengan bobot perhatian yang dipelajari berbeda. Ini memungkinkan model menangkap berbagai jenis hubungan dan memperhatikan berbagai bagian urutan input secara bersamaan.
- Layer Normalization: Normalisasi lapisan diterapkan setelah setiap sub-komponen atau lapisan dalam arsitektur transformer. Ini membantu menstabilkan proses pembelajaran dan meningkatkan kemampuan model untuk menggeneralisasi di berbagai input.
- Output Layers: Lapisan output dari model transformer dapat bervariasi tergantung pada tugas spesifik. Misalnya, dalam pemodelan bahasa, proyeksi linier diikuti oleh aktivasi SoftMax biasanya digunakan untuk menghasilkan distribusi probabilitas atas token berikutnya.

Penting untuk diingat bahwa arsitektur sebenarnya dari model berbasis transformer dapat berubah dan ditingkatkan berdasarkan penelitian dan kreasi model tertentu. Untuk memenuhi berbagai tugas dan tujuan, beberapa model seperti GPT, BERT, dan T5 dapat mengintegrasikan lebih banyak komponen atau modifikasi.

### Contoh LLM

LLM-LLM berikut adalah beberapa dari jenis LLM yang populer digunakan:

- GPT-3: GPT merupakan singkatan dari Generative pre-trained Transformer dan ini adalah versi ketiga dari model tersebut, oleh karena itu diberi nomor 3. Ini dikembangkan oleh OpenAI dan Anda pasti pernah mendengar tentang Chat GPT yang diluncurkan oleh OpenAI dan merupakan model GPT-3.
- BERT: Singkatan dari Bidirectional Encoder Representations from Transformers. Model bahasa besar ini dikembangkan oleh Google dan umumnya digunakan untuk berbagai tugas terkait bahasa alami. Selain itu, model ini dapat digunakan untuk menghasilkan embedding untuk teks tertentu mungkin untuk melatih model lain.
- RoBERTa: Singkatan dari Robustly Optimized BERT Pretraining Approach. Dalam upaya untuk meningkatkan kinerja arsitektur transformer, RoBERTa adalah versi peningkatan dari model BERT yang dikembangkan oleh Facebook AI Research.
- BLOOM: Ini adalah LLM multibahasa pertama yang dihasilkan oleh asosiasi berbagai organisasi dan peneliti yang menggabungkan keahlian mereka untuk mengembangkan model ini yang mirip dengan arsitektur GPT-3.

![gpt](img/chatgpt.jpeg)
![bert](img/bert.jpg)
![roberta](img/roberta.png)
![bloom](img/bloom.jpg)

### Penggunaan LLM

- Pembuatan Kode: Salah satu kasus penggunaan yang paling luar biasa adalah bahwa LLM dapat menghasilkan kode yang cukup akurat untuk tugas spesifik yang dijelaskan oleh pengguna kepada model.
- Debugging dan Dokumentasi Kode: Jika mengalami kesulitan dengan beberapa bagian kode terkait cara mendebug-nya, maka ChatGPT dapat memberi tahu baris kode yang menimbulkan masalah beserta solusinya. Selain itu, ChatGPT juga bisa menuliskan dokumentasi untuk kode program.
- Menjawab Pertanyaan: ChatGPT bisa dijadikan seperti search engine yang lebih canggih dan mengerti konteks, tidak seperti search engine Google, Bing, dan sebagainya.
- Penerjemahan Bahasa: LLM dapat mengonversi teks dari satu bahasa ke bahasa lain jika dibuat dengan kapabilitas tersebut. Beberapa LLM juga dapat membantu memperbaiki kesalahan tata bahasa dalam teks yang pengguna tulis.

![chatgpt poem](img/ChatGPT-poem.gif)

# Referensi

1. https://cloud.google.com/discover/what-is-unsupervised-learning
2. https://www.geeksforgeeks.org/clustering-in-machine-learning/
3. https://www.geeksforgeeks.org/getting-started-with-classification/
4. https://www.datacamp.com/blog/classification-machine-learning
5. https://medium.com/analytics-vidhya/confusion-matrix-accuracy-precision-recall-f1-score-ade299cf63cd
6. https://www.geeksforgeeks.org/regression-in-machine-learning/
7. https://builtin.com/data-science/regression-machine-learning
8. https://neptune.ai/blog/performance-metrics-in-machine-learning-complete-guide
9. https://www.geeksforgeeks.org/time-series-analysis-and-forecasting/
10. https://www.ibm.com/topics/object-detection
11. https://viso.ai/deep-learning/object-detection/
12. https://www.geeksforgeeks.org/large-language-model-llm/
