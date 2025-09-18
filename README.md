🌟 Proje Özeti

Mobil telefon pazarının dinamik yapısı göz önüne alındığında, bir telefonun fiyat aralığını doğru bir şekilde tahmin etmek hem tüketiciler hem de üreticiler için büyük önem taşımaktadır.
Bu çalışma, Python programlama dili ve güçlü makine öğrenimi kütüphaneleri kullanılarak mobil cihaz özelliklerinden fiyat aralığı tahmini yapan sağlam bir sınıflandırma modeli sunmaktadır.

✨ Temel Özellikler ve Uygulanan Adımlar
1. Veri Yükleme ve Genel Bakış

Pandas kütüphanesi kullanılarak veri seti bir DataFrame'e yüklendi.

Veri setinin ilk 5 satırı, boyutu (kayıt ve nitelik sayısı) ve veri tipleri incelenerek genel bir ön bilgi edinildi.

<img width="495" height="574" alt="image" src="https://github.com/user-attachments/assets/df20f533-9f7c-4844-81a9-d69fdfb8d31f" />
2. Veri Görselleştirme (EDA)
📊 Countplot Grafikleri

Kategorik değişkenlerin (örn: blue, dual_sim, g4, cores, g3, touch_screen, wifi, price_range) sınıf dağılımları countplot ile incelendi.

<img width="465" height="301" alt="image" src="https://github.com/user-attachments/assets/f4ae8a21-ffe5-4f7a-81bc-b403a80b56b4" /> <img width="457" height="301" alt="image" src="https://github.com/user-attachments/assets/a557c4ca-f554-4966-a3be-d5efe2245ec4" /> <img width="461" height="298" alt="image" src="https://github.com/user-attachments/assets/fdcb8a6f-dec9-4074-b56d-f5e01a52bcd6" /> <img width="460" height="300" alt="image" src="https://github.com/user-attachments/assets/e2cf8811-371b-4732-be2f-85a65359b758" /> <img width="467" height="308" alt="image" src="https://github.com/user-attachments/assets/2dadd1fb-53c6-48cc-9992-5f90dfceb864" /> <img width="467" height="303" alt="image" src="https://github.com/user-attachments/assets/5523ba67-8ad9-44d2-b632-3b2f1ac89920" /> <img width="473" height="307" alt="image" src="https://github.com/user-attachments/assets/949153fb-9e1d-4584-be13-e873cad72360" /> <img width="464" height="305" alt="image" src="https://github.com/user-attachments/assets/92de4daf-6690-48f6-be4e-125f193ad99f" />

Genel Çıkarımlar:

px_height ve swidth'de 0 değerler var → hatalı olabilir.

fcamera değişkeninde aşırı yayılım (aykırı değerler) gözlemlendi.

Mobil telefonlar, 4 fiyat aralığı sınıfına eşit sıklıkta dağılmıştır → veri seti dengelidir.

Bluetooth, 4G, dokunmatik ekran, WiFi, çift SIM desteği gibi özellikler benzer oranlarda dağıtılmıştır.

Mobil telefonların büyük çoğunluğu 3G desteğine sahiptir.

📊 Histogram Grafikleri

Numerik değişkenlerin dağılımları histogram grafikleri ile görselleştirildi.

<img width="597" height="650" alt="image" src="https://github.com/user-attachments/assets/772e1baf-2a2e-4a45-9fab-c18ebe8f208a" />

Not: Özellikle px_height (Piksel Yüksekliği) ve sc_w (Ekran genişliği, cm) özelliklerinde sıfıra yakın birçok değer gözlemlendi → gürültü olabilir.

📊 Boxplot Grafikleri

Özelliklerin hedef değişken (price_range) ile ilişkisi incelendi.

battery, px_height, px_width → hedef değişken üzerinde güçlü etkiye sahip.

<img width="343" height="441" alt="image" src="https://github.com/user-attachments/assets/e8a3e582-9b54-4a7f-84e4-47c270c80077" /> <img width="366" height="470" alt="image" src="https://github.com/user-attachments/assets/c0bdafc7-43eb-4b52-a035-8eb717f439ab" /> <img width="379" height="494" alt="image" src="https://github.com/user-attachments/assets/20eab125-c041-4d47-8465-0b63d3797335" />
3. Korelasyon Analizi

Özellikler arasındaki ilişkiler incelendi.

Genel olarak zayıf ilişkiler gözlemlendi.

<img width="565" height="607" alt="image" src="https://github.com/user-attachments/assets/633ffa82-d2d3-4f00-a769-18e18b3bc691" />
4. Veri Ön İşleme ve Özellik Mühendisliği

Hatalı Değerlerin Doldurulması:
px_height ve swidth → medyan değerleriyle dolduruldu.

Aykırı Değer Analizi ve Baskılanması:
outlier_thresholds fonksiyonu ile aykırı değerler tespit edildi,
replace_with_thresholds ile baskılandı.

Yeni Özellik (ram):
price_range ile güçlü pozitif ilişkisi olan ram öne çıkarıldı.

<img width="847" height="529" alt="image" src="https://github.com/user-attachments/assets/9cbaae22-c20f-4c88-bf16-80175e6e70b0" />

Veri Standartlaştırma:

Kategorik özellikler zaten sayısal olduğu için dummy encoding yapılmadı.

StandardScaler ile veriler standartlaştırıldı.

5. Modelleme ve Değerlendirme

Veri Bölme: Veri seti %80 eğitim / %20 test olarak ayrıldı.

Model: Destek Vektör Makineleri (SVM) kullanıldı.

Sonuç: Test doğruluğu %82.

📊 Karmaşıklık Matrisi
<img width="683" height="581" alt="image" src="https://github.com/user-attachments/assets/8693200e-b4d8-4024-a4b4-da8f6688b55b" />
📑 Sınıflandırma Raporu
              precision    recall  f1-score   support
           0       0.90      1.00      0.95        57
           1       0.76      0.85      0.80        55
           2       0.68      0.66      0.67        59
           3       0.91      0.77      0.83        69

    accuracy                           0.82       240
   macro avg       0.82      0.82      0.82       240
weighted avg       0.82      0.82      0.82       240

🚀 Kullanılan Teknolojiler

Python

Pandas → Veri manipülasyonu ve analizi

NumPy → Sayısal işlemler

Scikit-learn (sklearn) → Makine öğrenimi, veri ön işleme, modelleme

Seaborn & Matplotlib → Görselleştirme ve korelasyon analizleri

🔮 Gelecek Çalışmalar

SVM için farklı kernel türleri (rbf, poly) ve C parametresi optimizasyonu

Gradient Boosting veya XGBoost gibi algoritmaların denenmesi

Performansı düşük sınıflar için Veri Artırma (Data Augmentation) yöntemleri

🤝 Katkıda Bulunma

Bu projeyi daha da geliştirmek için her türlü katkıya açığız!

Yeni fikirler için bir issue açabilirsiniz.

Kod geliştirmeleri için pull request gönderebilirsiniz.
