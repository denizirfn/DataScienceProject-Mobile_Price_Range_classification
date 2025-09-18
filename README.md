🌟 Proje Özeti

Mobil telefon pazarının dinamik yapısı göz önüne alındığında, bir telefonun fiyat aralığını doğru tahmin etmek hem tüketiciler hem de üreticiler için büyük önem taşır.
Bu çalışma, Python ve güçlü makine öğrenimi kütüphaneleri kullanılarak mobil cihaz özelliklerinden fiyat aralığı tahmini yapan sağlam bir sınıflandırma modeli sunmaktadır.

✨ Temel Özellikler ve Uygulanan Adımlar
1️⃣ Veri Yükleme ve Genel Bakış

Pandas ile veri seti DataFrame’e yüklendi.

Veri setinin:

İlk 5 satırı incelendi

Boyutu (kayıt ve nitelik sayısı)

Veri tipleri analiz edildi.

<img width="495" height="574" alt="image" src="https://github.com/user-attachments/assets/df20f533-9f7c-4844-81a9-d69fdfb8d31f" />
2️⃣ Veri Görselleştirme (EDA)
📊 Countplot Grafikleri

Kategorik değişkenlerin (örn. blue, dual_sim, g4, cores, g3, touch_screen, wifi, price_range) sınıf dağılımları incelendi.

<img width="465" height="301" alt="image" src="https://github.com/user-attachments/assets/f4ae8a21-ffe5-4f7a-81bc-b403a80b56b4" /> … (diğer görseller)

Genel Çıkarımlar:

px_height ve swidth değişkenlerinde 0 değerler var → hatalı olabilir.

fcamera değişkeninde aykırı değerler gözlemlendi.

Mobil telefonlar, 4 fiyat aralığına eşit sıklıkta dağılmıştır → veri seti dengelidir.

Bluetooth, 4G, dokunmatik ekran, WiFi, çift SIM desteği gibi özellikler benzer oranlarda dağıtılmıştır.

Mobil telefonların büyük çoğunluğu 3G desteğine sahiptir.

📊 Histogram Grafikleri

Sayısal değişkenlerin dağılımları incelendi.

<img width="597" height="650" alt="image" src="https://github.com/user-attachments/assets/772e1baf-2a2e-4a45-9fab-c18ebe8f208a" />

Özellikle px_height ve sc_w (ekran genişliği) özelliklerinde sıfıra yakın çok sayıda değer gözlemlendi → gürültü olabilir.

📊 Boxplot Grafikleri

Özelliklerin hedef değişken (price_range) ile ilişkisi analiz edildi.

battery, px_height, px_width → hedef değişken üzerinde güçlü etkiye sahip.

<img width="343" height="441" alt="image" src="https://github.com/user-attachments/assets/e8a3e582-9b54-4a7f-84e4-47c270c80077" /> … (diğer görseller)

3️⃣ Korelasyon Analizi

Özellikler arasındaki ilişkiler incelendi ve genel olarak zayıf korelasyonlar gözlemlendi.

<img width="565" height="607" alt="image" src="https://github.com/user-attachments/assets/633ffa82-d2d3-4f00-a769-18e18b3bc691" />
4️⃣ Veri Ön İşleme ve Özellik Mühendisliği

Hatalı Değerlerin Doldurulması
px_height ve swidth → medyan ile dolduruldu.

Aykırı Değer Analizi ve Baskılanması
outlier_thresholds ve replace_with_thresholds fonksiyonlarıyla tespit ve baskılama.

Yeni Özellik
ram → price_range ile güçlü pozitif ilişkisi nedeniyle öne çıkarıldı.

<img width="847" height="529" alt="image" src="https://github.com/user-attachments/assets/9cbaae22-c20f-4c88-bf16-80175e6e70b0" />

Veri Standartlaştırma

Kategorik özellikler sayısal olduğundan dummy encoding yapılmadı.

StandardScaler ile standartlaştırma uygulandı.

5️⃣ Modelleme ve Değerlendirme

Veri Bölme: %80 eğitim / %20 test

Model: Destek Vektör Makineleri (SVM)

Sonuç: Test doğruluğu %82

📊 Karmaşıklık Matrisi
<img width="683" height="581" alt="image" src="https://github.com/user-attachments/assets/8693200e-b4d8-4024-a4b4-da8f6688b55b" />
📑 Sınıflandırma Raporu
Sınıf	Precision	Recall	F1-Score	Destek
0	0.90	1.00	0.95	57
1	0.76	0.85	0.80	55
2	0.68	0.66	0.67	59
3	0.91	0.77	0.83	69
Genel	0.82	0.82	0.82	240
🚀 Kullanılan Teknolojiler

Python

Pandas → Veri manipülasyonu ve analizi

NumPy → Sayısal işlemler

Scikit-learn (sklearn) → Makine öğrenimi, veri ön işleme, modelleme

Seaborn & Matplotlib → Görselleştirme ve korelasyon analizleri

🔮 Gelecek Çalışmalar

SVM için farklı kernel türleri (rbf, poly) ve C parametresi optimizasyonu

Gradient Boosting veya XGBoost gibi algoritmaların denenmesi

Performansı düşük sınıflar için veri artırma (data augmentation) yöntemleri

🤝 Katkıda Bulunma

Bu projeyi geliştirmek için her türlü katkıya açığız!

💡 Yeni fikirler için issue açabilirsiniz.

🛠 Kod geliştirmeleri için pull request gönderebilirsiniz.
