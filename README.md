# Mikroskopik Hücre Görüntülerinde Parazit Tespiti için CNN Tabanlı Otomatik Sınıflandırma
Bu projede, mikroskop altında çekilmiş hücre görüntülerinden parazitli olup olmadığını otomatik olarak tahmin etmek için CNN (Convolutional Neural Network) modeli geliştirilmiştir. Her renkli görüntü 103x103 piksel boyutunda ve 3 kanallıdır (RGB). Etiketler 0 (temiz hücre) ve 1 (parazitli hücre) olarak verilmiştir. CNN modeli için sabit giriş boyutu gerekliliğinden dolayı tüm görüntüler 224x224 boyutuna yeniden ölçeklendirilmiştir.

Model, LeNet mimarisine benzer şekilde tasarlanmıştır: 2 adet Conv2D katmanı ile görüntüden kenar, renk ve doku gibi özellikler çıkarılmış, Batch Normalization ile öğrenme stabilize edilmiş, MaxPooling ile boyut indirgenmiş, ardından veriler Flatten katmanı ile düzleştirilmiştir. Sonrasında 2 Dense katman ve çıkışta sigmoid aktivasyonlu tek nöron kullanılmıştır.

Model eğitimi sırasında BinaryCrossentropy kayıp fonksiyonu ve Adam optimizasyon algoritması kullanılmıştır. Performans değerlendirmesi için F1 skoru ve AUC–ROC metrikleri tercih edilmiştir. AUC–ROC eğrisi, modelin sınıfları ayırmadaki başarısını gösterir ve değeri 1’e yaklaştıkça model gücü artar. Tahmin sonucunda 0.5’in üzeri parazitli, altında ise temiz hücre olarak sınıflandırılmıştır.

# Kullanılan Teknolojiler ve Kütüphaneler
TensorFlow / Keras — Derin öğrenme ve CNN modeli geliştirme

NumPy — Veri işlemleri

OpenCV — Görüntü işleme ve yeniden boyutlandırma

Scikit-learn — Model değerlendirme metrikleri

Matplotlib — Sonuçların görselleştirilmesi


# PROJE AŞAMALARI

# 1 -Veri Hazırlama
Mikroskop görüntüleri 103x103 boyutunda renkli olarak sağlandı. CNN için zorunlu giriş boyutu 224x224’e yeniden boyutlandırıldı.

# 2- Model Tasarımı
LeNet benzeri 2 Conv2D katmanı, BatchNorm, MaxPool, Flatten, 2 Dense katmanı ve sigmoid çıkış katmanı oluşturuldu.

# 3- Model Eğitimi
BinaryCrossentropy kayıp fonksiyonu ve Adam optimizasyonu ile model eğitildi.

# 4 - Değerlendirme
F1 skoru ve AUC-ROC metrikleri ile model performansı ölçüldü.

# 5- Sınıflandırma
Tahmin > 0.5 ise parazitli, <= 0.5 ise temiz hücre olarak etiketlendi.

# Dosya Yapısı
├── data/                  # Hücre görüntüleri ve etiketler  
├── model/                 # Eğitilmiş model dosyaları  
├── scripts/               # Eğitim ve değerlendirme kodları  
├── README.md              # Proje açıklaması  
└── requirements.txt       # Kullanılan kütüphaneler 

# Geliştirme Önerileri
Daha derin CNN mimarileri veya transfer öğrenme kullanmak
Veri artırma teknikleri ile model genelleştirmesini geliştirmek
Parazit tiplerine göre çoklu sınıflandırma yapmak

# Proje Sahibi
Çağdaş ÇANKAYA
