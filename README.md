# Makine Öğrenmesi Final Ödevi

## Müşteri Satın Alma Davranışının Tahmin Edilmesi

### Projenin Amacı

Bu projede, müşterilerin satın alma davranışının makine öğrenmesi yöntemleri kullanılarak tahmin edilmesi amaçlanmıştır.

Problem bir **sınıflandırma problemi** olarak ele alınmıştır. Hedef değişken `satin_aldi` olarak belirlenmiştir.

### Kullanılan Teknolojiler

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Google Colab

### Veri Seti

Çalışmada 300 satırdan oluşan müşteri verisi kullanılmıştır.

Veri setinde aşağıdaki değişkenler bulunmaktadır:

- `yas`
- `maas`
- `sehir`
- `egitim`
- `deneyim_yili`
- `satin_aldi`

### Veri Ön İşleme

Proje kapsamında;

- Veri seti incelenmiştir.
- Eksik değerler kontrol edilmiştir.
- Kategorik değişkenler One-Hot Encoding yöntemiyle sayısal forma dönüştürülmüştür.
- Aykırı değer kontrolü yapılmıştır.
- Sayısal değişkenlere StandardScaler ile ölçekleme uygulanmıştır.

### Öznitelik Mühendisliği

Modelin performansını desteklemek amacıyla iki yeni öznitelik oluşturulmuştur:

- `maas_yas_orani`
- `deneyim_maas_orani`

Ayrıca korelasyon analizi kullanılarak hedef değişkenle ilişkili öznitelikler incelenmiştir.

### Kullanılan Modeller

Projede üç farklı sınıflandırma modeli karşılaştırılmıştır:

1. Logistic Regression
2. K-Nearest Neighbors (KNN)
3. Decision Tree

### Model Karşılaştırması

Validation sonuçlarına göre en başarılı model Logistic Regression olmuştur.

| Model | Accuracy | Precision | Recall | F1-Score |
|---|---:|---:|---:|---:|
| Logistic Regression | 0.9556 | 0.9667 | 0.9667 | 0.9667 |
| Decision Tree | 0.9111 | 0.8824 | 1.0000 | 0.9375 |
| KNN | 0.8000 | 0.8182 | 0.9000 | 0.8571 |

### Cross Validation

Logistic Regression modeli için 5 katlı Stratified Cross Validation uygulanmıştır.

Ortalama F1-Score:

**0.9004**

Standart sapma:

**0.0416**

### Hiperparametre Ayarlama

Logistic Regression modeli için Grid Search uygulanmıştır.

En iyi parametreler:

- `C = 1`
- `solver = liblinear`

Grid Search sonucundaki en iyi Cross Validation F1-Score:

**0.8994**

### Test Sonuçları

Seçilen Logistic Regression modeli test veri setinde değerlendirilmiştir.

| Metrik | Sonuç |
|---|---:|
| Accuracy | 0.9111 |
| Precision | 0.9091 |
| Recall | 0.9677 |
| F1-Score | 0.9375 |

### Confusion Matrix

Test verisi üzerinde elde edilen confusion matrix:

```text
[[11  3]
 [ 1 30]]
Modelin Açıklanabilirliği

Logistic Regression modelinin katsayıları incelenerek model kararında etkili olan öznitelikler değerlendirilmiştir.

Ayrıca Decision Tree modelinin feature importance değerleri incelenerek önemli öznitelikler belirlenmiştir.

Sonuç

Bu çalışmada müşteri satın alma davranışını tahmin etmek için farklı makine öğrenmesi modelleri karşılaştırılmıştır.

Validation sonuçlarına göre Logistic Regression en başarılı model olarak seçilmiştir. Yapılan Cross Validation ve Grid Search çalışmaları sonucunda modelin kararlı bir performans gösterdiği görülmüştür.

Test verisinde %91,11 doğruluk ve 0,9375 F1-Score elde edilmiştir.

Bununla birlikte veri setinin sınırlı olması çalışmanın önemli bir kısıtıdır. Daha büyük ve gerçek müşteri verileri kullanılarak modelin gerçek dünya performansı daha kapsamlı şekilde değerlendirilebilir.

Çalıştırma

Projeyi çalıştırmak için Jupyter Notebook veya Google Colab kullanılabilir.

Gerekli Python kütüphaneleri:

pandas
numpy
matplotlib
seaborn
scikit-learn

Notebook dosyası:

Makine_Ogrenmesi_Final_Odevi_Merve_Barisik.ipynb
