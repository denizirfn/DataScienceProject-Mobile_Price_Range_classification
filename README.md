📱 Mobile Phone Price Range Prediction 📈

Bu proje, mobil telefonların özelliklerine dayanarak fiyat aralıklarını tahmin etmeyi amaçlamaktadır. Doğrudan gerçek fiyat tahmini yapmak yerine, telefonun hangi fiyat aralığına (düşük, orta, yüksek, çok yüksek) girdiğini belirleyen bir sınıflandırma modeli geliştirilmiştir.

🌟 Proje Özeti

Mobil telefon pazarının dinamik yapısı göz önüne alındığında, bir telefonun fiyat aralığını doğru tahmin etmek hem tüketiciler hem de üreticiler için önemlidir. Bu çalışma, Python ve güçlü makine öğrenimi kütüphaneleri kullanılarak, mobil cihaz özelliklerinden fiyat aralığı tahmini yapan sağlam bir sınıflandırma modeli sunmaktadır.

✨ Temel Özellikler ve Uygulanan Adımlar
1. Veri Yükleme ve Genel Bakış

Veri seti Pandas kullanılarak bir DataFrame’e yüklendi.

Veri setinin ilk 5 satırı, boyutu ve veri tipleri incelendi.

<img width="495" height="574" alt="DataFrame Overview" src="https://github.com/user-attachments/assets/df20f533-9f7c-4844-81a9-d69fdfb8d31f" />
2. Veri Görselleştirme (EDA)

Countplot Grafikleri: Kategorik değişkenlerin dağılımları incelendi.

<img width="465" height="301" alt="countplot1" src="https://github.com/user-attachments/assets/f4ae8a21-ffe5-4f7a-81bc-b403a80b56b4" />
<img width="457" height="301" alt="countplot2" src="https://github.com/user-attachments/assets/a557c4ca-f554-4966-a3be-d5efe2245ec4" />

Histogram Grafikleri: Sayısal değişkenlerin dağılımları gözlemlendi. Özellikle px_height ve swidth değişkenlerinde sıfır değerler dikkat çekti.

<img width="597" height="650" alt="histogram" src="https://github.com/user-attachments/assets/772e1baf-2a2e-4a45-9fab-c18ebe8f208a" />

Boxplot Grafikleri: Özelliklerin hedef değişken (price_range) ile ilişkisi analiz edildi.

<img width="343" height="441" alt="boxplot1" src="https://github.com/user-attachments/assets/e8a3e582-9b54-4a7f-84e4-47c270c80077" />

Genel Çıkarımlar:

px_height ve swidth’de 0 değerler hatalı olabilir.

Mobil telefonlar, fiyat aralığı sınıflarına dengeli şekilde dağılmıştır.

Çoğu telefon Bluetooth, 4G, dokunmatik ekran, Wifi gibi özelliklere sahiptir.

Büyük çoğunluk 3G desteğine sahiptir.

3. Korelasyon Analizi

Özellikler arasındaki ilişkiler ve hedef değişken ile korelasyonlar incelendi.

Başlangıçta zayıf ilişkiler gözlemlendi.

<img width="565" height="607" alt="correlation" src="https://github.com/user-attachments/assets/633ffa82-d2d3-4f00-a769-18e18b3bc691" />
4. Veri Ön İşleme ve Özellik Mühendisliği

Hatalı Değerler: px_height ve swidth’deki 0 değerler medyan ile dolduruldu.

Aykırı Değer Analizi: outlier_thresholds ve replace_with_thresholds fonksiyonları kullanıldı.

<img width="323" height="448" alt="outlier_handling" src="https://github.com/user-attachments/assets/073773ab-3c90-4bc7-ba4b-32439f8984e2" />

Yeni Özellik (ram): price_range ile pozitif ilişkiye sahip yeni bir özellik oluşturuldu.

<img width="847" height="529" alt="feature_engineering" src="https://github.com/user-attachments/assets/9cbaae22-c20f-4c88-bf16-80175e6e70b0" />

Veri Standartlaştırma: Tüm kategorik değişkenler sayısal formatta olduğundan dummy encoding gerekmedi. StandardScaler ile standartlaştırıldı.

5. Modelleme ve Değerlendirme

Veri Bölme: %80 eğitim, %20 test.

Model: Destek Vektör Makineleri (SVM) kullanıldı.

Performans: Test veri setinde %82 doğruluk elde edildi.

Karmaşıklık Matrisi:

<img width="683" height="581" alt="confusion_matrix" src="https://github.com/user-attachments/assets/8693200e-b4d8-4024-a4b4-da8f6688b55b" />

Sınıflandırma Raporu:

              precision    recall  f1-score   support
0             0.90      1.00      0.95        57
1             0.76      0.85      0.80        55
2             0.68      0.66      0.67        59
3             0.91      0.77      0.83        69
accuracy                           0.82       240
macro avg       0.82      0.82      0.82       240
weighted avg    0.82      0.82      0.82       240

🚀 Kullanılan Teknolojiler

Python

Pandas: Veri manipülasyonu ve analizi

NumPy: Sayısal işlemler

Scikit-learn: Makine öğrenimi, veri ön işleme ve değerlendirme

Seaborn & Matplotlib: Görselleştirme

🔮 Gelecek Çalışmalar

Farklı SVM kernel türleri (rbf, poly) ve C parametresi optimizasyonu.

Gradient Boosting / XGBoost gibi farklı algoritmaların denenmesi.

Performansı düşük sınıflar için Veri Artırma (Data Augmentation) uygulanması.

🤝 Katkıda Bulunma

Projeyi geliştirmek için her türlü katkıya açığız!
Lütfen bir issue açın veya pull request gönderin.
