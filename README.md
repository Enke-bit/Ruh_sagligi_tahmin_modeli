# Ruh Sağlığı Tahmini Yapan Model README

Bu proje, yapay sinir ağı kullanarak ruh sağlığı durumunu tahmin eden bir modelin geliştirilmesi ve değerlendirilmesi üzerine yapılmıştır. Aşağıda modelin tanımlanması, kullanılan veri seti, eğitim sonuçları ve test performansı hakkında detaylar bulabilirsiniz.

## Model Tanımı

Yapay sinir ağı modeli, Keras kütüphanesi üzerinde geliştirilmiştir. Modelin katmanları ve aktivasyon fonksiyonları aşağıdaki gibidir:

```python
model = Sequential([
    Dense(64, input_dim=X_train.shape[1], activation='relu'),
    Dropout(0.5),
    Dense(32, activation='relu'),
    Dropout(0.5),
    Dense(1, activation='sigmoid')
])


Modelin yapılandırması:

Giriş katmanı: 64 nöronlu ReLU aktivasyonu
Dropout katmanı: %50 oranında dropout (overfittingi önlemek için)
Gizli katman: 32 nöronlu ReLU aktivasyonu
Dropout katmanı: %50 oranında dropout
Çıkış katmanı: Sigmoid aktivasyonu ile tek bir nöron (0 veya 1 tahmini)
Veri Seti
Model, ruh sağlığı hakkında çeşitli özellikleri içeren bir veri seti üzerinde eğitilmiştir. Özellikler arasında cinsiyet, ülke, meslek, aile öyküsü, stres düzeyi gibi faktörler bulunmaktadır.

Eğitim Sonuçları
Model eğitimi sırasında kullanılan kayıp fonksiyonu ve optimize edici aşağıdaki gibidir:

Kayıp Fonksiyonu: Binary Crossentropy
Optimizasyon: Adam Optimizer
Test Sonuçları
Modelin test doğruluğu ve sınıflandırma sonuçları şu şekildedir:

Test Doğruluğu: 1.00 (100%)
Precision, Recall, F1-score:

            precision    recall  f1-score   support

        No       1.00      1.00      1.00         1
       Yes       1.00      1.00      1.00         1

  accuracy                           1.00         2
 macro avg       1.00      1.00      1.00         2

weighted avg 1.00 1.00 1.00 2


## Kullanım

Modeli kullanarak tahmin yapmak için, gerekli özellikleri içeren bir girdi verisi sağlanmalıdır. Model, tek bir örneğin tahminini yapabilir veya toplu tahminler üretebilir.

Örnek kullanım:
```python
# Model üzerinden tahmin yapma
prediction = model.predict(input_data)


Geliştirici Bilgileri
Bu proje İbrahim Püsküllü 'e aittir. Herhangi bir soru veya geri bildiriminiz varsa, lütfen ibrahimpuskullu44@gmail.com üzerinden iletişime geçin.
