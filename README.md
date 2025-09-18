📱 Mobile Phone Price Range Prediction 📈

Bu proje, mobil telefonların özelliklerine dayanarak fiyat aralıklarını tahmin etmek için çeşitli sınıflandırma modelleri geliştirmeyi amaçlamaktadır. Gerçek fiyat tahmini yerine, telefonların hangi fiyat aralığında (düşük, orta, yüksek, çok yüksek maliyet) yer aldığını belirleyen bir sınıflandırma modeli sunulmuştur.

🌟 Proje Özeti

Mobil telefon pazarının dinamik yapısı göz önüne alındığında, telefonların fiyat aralığını doğru tahmin etmek hem tüketiciler hem de üreticiler için önemlidir. Bu çalışmada:

Python ve güçlü makine öğrenimi kütüphaneleri kullanılarak,

Mobil cihaz özelliklerinden fiyat aralığı tahmini yapan,

Sağlam ve güvenilir bir sınıflandırma modeli geliştirilmiştir.

✨ Çalışma Adımları ve Temel Özellikler
1️⃣ Veri Yükleme ve Genel İnceleme

Pandas ile veri seti DataFrame’e yüklendi.

İlk 5 satır, boyutlar ve veri tipleri incelendi.

<img width="495" height="574" alt="image" src="https://github.com/user-attachments/assets/df20f533-9f7c-4844-81a9-d69fdfb8d31f" />
2️⃣ Veri Keşfi ve Görselleştirme (EDA)

📊 Countplot Analizi

Kategorik değişkenlerin (örn: Bluetooth, 3G, 4G, dokunmatik ekran, çift SIM, WiFi, çekirdek sayısı, fiyat aralığı) dağılımları incelendi.

<img width="465" height="301" alt="image" src="https://github.com/user-attachments/assets/f4ae8a21-ffe5-4f7a-81bc-b403a80b56b4" />

Genel Çıkarımlar:

px_height ve sc_width değişkenlerinde 0 değerler mevcut (hatalı).

fcamera değişkeninde aykırı değerler var.

Fiyat aralıkları dengeli dağıtılmıştır (her sınıf eşit sayıda).

3G desteği çoğu cihazda mevcut, diğer özellikler (4G, WiFi, Bluetooth) de benzer oranlarda.

📊 Histogram Analizi

Numerik değişkenler incelendi, özellikle px_height ve sc_width değişkenlerinde sıfır değerler dikkat çekti.

<img width="597" height="650" alt="image" src="https://github.com/user-attachments/assets/772e1baf-2a2e-4a45-9fab-c18ebe8f208a" />

📊 Boxplot Analizi

battery, px_height, px_width → fiyat aralığı üzerinde güçlü etkiye sahip.

<img width="366" height="470" alt="image" src="https://github.com/user-attachments/assets/c0bdafc7-43eb-4b52-a035-8eb717f439ab" />
3️⃣ Korelasyon Analizi

Korelasyon matrisi oluşturuldu.

Genel olarak zayıf ilişkiler olsa da ram, battery, px_width öne çıktı.

<img width="565" height="607" alt="image" src="https://github.com/user-attachments/assets/633ffa82-d2d3-4f00-a769-18e18b3bc691" />
4️⃣ Veri Ön İşleme & Özellik Mühendisliği

Hatalı Değer Düzeltme: px_height ve sc_width → medyan ile dolduruldu.

Aykırı Değer İşleme: outlier_thresholds ve replace_with_thresholds fonksiyonları ile baskılama yapıldı.

Yeni Özellik: ram değişkeni hedef değişkenle güçlü korelasyona sahip olduğundan vurgulandı.

<img width="847" height="529" alt="image" src="https://github.com/user-attachments/assets/9cbaae22-c20f-4c88-bf16-80175e6e70b0" />

Standartlaştırma: StandardScaler ile tüm veriler ölçeklendirildi.

5️⃣ Modelleme ve Değerlendirme

Veri Bölme: Eğitim (%80) – Test (%20).

Model: Destek Vektör Makineleri (SVM). Gürültülü verilere karşı sağlamlığı nedeniyle tercih edildi.

Sonuçlar:

Test doğruluğu: %82

Karmaşıklık Matrisi:

<img width="683" height="581" alt="image" src="https://github.com/user-attachments/assets/8693200e-b4d8-4024-a4b4-da8f6688b55b" />

📑 Sınıflandırma Raporu:

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

Pandas → Veri manipülasyonu

NumPy → Sayısal işlemler

Scikit-learn → Modelleme ve değerlendirme

Matplotlib & Seaborn → Görselleştirme

🔮 Gelecek Çalışmalar

SVM için farklı kernel türleri (RBF, Poly) ve C parametresi optimizasyonu.

Gradient Boosting, XGBoost gibi farklı algoritmaların test edilmesi.

Performansı düşük sınıflar için veri artırma (Data Augmentation) teknikleri.

🤝 Katkıda Bulunma

Projeyi geliştirmek için katkılarınızı bekliyoruz!

Yeni fikirler için issue açabilirsiniz.

Kod geliştirmeleri için pull request gönderebilirsiniz.
