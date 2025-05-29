Bu proje, mobil cihazların teknik özelliklerine göre fiyat aralıklarını tahmin eden bir makine öğrenmesi modelinin geliştirilmesini amaçlamaktadır.

🔍 Proje Amacı
Mobil telefonların teknik özelliklerine göre (örneğin pil gücü, işlemci hızı, RAM miktarı, vs.) hangi fiyat aralığında yer aldığını tahmin etmek. Bu amaçla sınıflandırma algoritmaları (Random Forest ve SVM) kullanılmıştır.

🧰 Kullanılan Kütüphaneler
pandas

numpy

matplotlib

seaborn

scikit-learn

📁 Veri Kümesi
train_odev.csv adlı dosya kullanılmıştır.

Veri kümesi, çeşitli mobil cihaz özelliklerini ve fiyat aralıklarını (price_range) içermektedir.

📌 Yapılan İşlemler
Veri Yükleme ve İnceleme:

Veri kümesi pandas ile okunarak ilk bakışta genel durumu incelenmiştir.

Veri türleri, eksik değerler ve dağılımlar analiz edilmiştir.

Değişken Tipi Ayırma:

Sayısal ve kategorik değişkenler ayıklanarak analizler bu yapıya göre yürütülmüştür.

Veri Görselleştirme:

Kategorik değişkenler için countplot, sayısal değişkenler için histogram grafikleri çizilmiştir.

Değişkenlerin price_range sınıfı ile olan ilişkisi incelenmiştir.

Özellik Ölçekleme:

Modelleme öncesi sayısal değişkenler StandardScaler ile ölçeklenmiştir.

Modelleme:

RandomForestClassifier ve SVC modelleri eğitilmiş ve test verisi üzerinde değerlendirilmiştir.

Başarı oranları (accuracy, classification_report) kullanılarak karşılaştırılmıştır.

📈 Sonuçlar
Eğitim sonucunda modellerin başarı oranları kıyaslanmış, hangi modelin daha uygun olduğu değerlendirilmiştir.

Model doğrulukları ve sınıf başına performans metrikleri sunulmuştur.

📎 Notlar
Proje, temel sınıflandırma problemlerine yönelik bir çalışma olup; veri ön işleme, görselleştirme ve makine öğrenmesi aşamalarını içermektedir.

Eğitim ve test ayrımı train_test_split ile yapılmıştır.
