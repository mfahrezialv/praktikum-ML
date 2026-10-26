# Praktikum Machine Learning - Prediksi Gaji

Repository ini berisi tugas praktikum mengenai pemodelan Machine Learning menggunakan algoritma **Gradient Boosting Regressor** untuk memprediksi gaji.

## Struktur Folder
- `Praktikum_ML_Gaji/`
  - `Praktikum.ipynb`: Notebook eksperimen dan pelatihan model
  - `gbr_model.joblib`: Model yang telah disimpan
  - `data.json` & `salary_prediction_data.csv`: Dataset dan data sampel



  #  Laporan Analisis Evaluasi Performa Model

Berikut adalah analisis rinci untuk masing-masing metrik evaluasi regresi (**$R^2$ Score**, **MAE**, dan **MSE**) berdasarkan hasil pengujian tiga algoritma (*Lars*, *Linear Regression*, dan *GradientBoostingRegressor*).

---

### 1. Koefisien Determinasi ($R^2$ Score)

* **Acuan Ideal:** Nilai $R^2$ berkisar antara 0 sampai 1. **Semakin mendekati angka 1, semakin baik/sempurna** performa model dalam menjelaskan data.
* **Perbandingan Hasil:**
  * **GradientBoostingRegressor:** $R^2 = \mathbf{0{,}8768}$ (Paling mendekati 1)
  * **Linear Regression:** $R^2 = 0{,}6055$
  * **Lars:** $R^2 = 0{,}1122$ (Paling jauh dari 1)
* **Penjelasan:** 
  Model *Gradient Boosting Regressor* mencatatkan nilai $R^2$ sebesar 0,8768, yang berarti model ini mampu menjelaskan sekitar **87,68% variasi dari variabel target (gaji)**. Sebaliknya, model *Lars* hanya mampu menjelaskan 11,22% variasi data sehingga tergolong sangat buruk.

---

### 2. Mean Absolute Error (MAE)

* **Acuan Ideal:** MAE mengukur rata-rata besarnya kesalahan tebakan secara absolut. **Semakin kecil nilainya (semakin mendekati 0), semakin akurat** model tersebut.
* **Perbandingan Hasil:**
  * **GradientBoostingRegressor:** MAE = $\mathbf{8.330{,}14}$ (Paling kecil / dekat ke 0)
  * **Linear Regression:** MAE = $14.982{,}78$
  * **Lars:** MAE = $23.308{,}34$ (Paling besar)
* **Penjelasan:** 
  *Gradient Boosting* memiliki selisih kesalahan prediksi paling minimal, yaitu rata-rata hanya meleset sebesar 8.330 unit dari gaji aktual. Nilai ini jauh lebih presisi dibandingkan model *Lars* yang tingkat kesalahannya mencapai 23.308 unit.

---

### 3. Mean Squared Error (MSE)

* **Acuan Ideal:** MSE mengukur rata-rata kuadrat dari kesalahan prediksi. Sama seperti MAE, **semakin kecil nilainya (semakin mendekati 0), semakin baik** kualitas prediksinya.
* **Perbandingan Hasil:**
  * **GradientBoostingRegressor:** MSE = $\mathbf{1{,}058 \times 10^8}$ (Paling kecil / dekat ke 0)
  * **Linear Regression:** MSE = $3{,}390 \times 10^8$
  * **Lars:** MSE = $7{,}628 \times 10^8$ (Paling besar)
* **Penjelasan:** 
  Karena kesalahan dikuadratkan, MSE memberikan penalti lebih besar pada tebakan yang meleset jauh (*outlier*). Nilai MSE *Gradient Boosting* yang paling rendah membuktikan bahwa model ini sangat stabil dan minim dari kesalahan tebakan yang ekstrem.

---

### 🏆 Kesimpulan Akhir
Dari perbandingan ketiga metrik di atas, **`GradientBoostingRegressor`** merupakan algoritma **terbaik** karena unggul di seluruh indikator: memiliki $R^2$ paling mendekati 1, serta MAE dan MSE yang paling rendah (mendekati 0).

---

### 📚 Daftar Referensi
1. **Géron, A. (2019).** *Hands-On Machine Learning with Scikit-Learn, Keras, and TensorFlow* (2nd ed.). O'Reilly Media. [Tautan Buku](https://www.oreilly.com/library/view/hands-on-machine-learning/9781492032632/)
2. **James, G., Witten, D., Hastie, T., & Tibshirani, R. (2021).** *An Introduction to Statistical Learning: with Applications in R* (2nd ed.). Springer. [Tautan PDF Resmi](https://hastie.su.domains/ISLR2/ISLRv2_corrected_June_2023.pdf.download.html)