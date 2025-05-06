# YMT5270 - Ara Sınav Projesi: Öğrenci Performans Verisi

## Proje Tanımı
Bu proje, YMT5270 - Yenilikçi Makine Öğrenme Ortamları dersi kapsamında, öğrencilerin sınavlardaki performanslarını tahmin etmek için **Orange Data Mining** platformu kullanılarak yapılan bir sınıflandırma problemidir. Projede, **"Students Performance in Exams"** adlı Kaggle veri seti kullanılmıştır. Bu veri seti, öğrencilerin sınav performanslarını etkileyebilecek faktörleri içermektedir ve sınıflandırma analizi yapılmaktadır.

## Veri Seti
- **Veri Seti Adı**: Students Performance in Exams
- **Kaynak**: [Kaggle - Students Performance in Exams](https://www.kaggle.com/datasets/spscientist/students-performance-in-exams)
- **Lisans**: Kaggle veri setinin lisans koşullarına tabidir.
- **Veri Seti Özellikleri**:
    - 5 özellik (özellikler: gender, race/ethnicity, parental level of education, lunch, test preparation course).
    - Hedef değişken: exam scores (sınav sonuçları).
    - 100 örnek içermektedir.

## Keşifsel Veri Analizi (EDA)
Projede keşifsel veri analizi (EDA) adımlarında aşağıdaki işlemler gerçekleştirilmiştir:
- Veri setinin temel istatistikleri hesaplanmıştır.
- Eksik veriler kontrol edilip, herhangi bir eksiklik bulunmamıştır.
- Aykırı değerler tespit edilmiştir ve uygun görselleştirmeler yapılmıştır (örneğin, histogramlar, kutu grafikleri).
- Öznitelikler arasındaki ilişkiler görselleştirilmiştir (scatter plots, box plots).

## Makine Öğrenmesi Modeli
Proje kapsamında, sınıflandırma problemine yönelik **Logistic Regression** modeli kullanılmıştır. Modelin eğitimi için aşağıdaki adımlar takip edilmiştir:
- Veri, eğitim ve test setlerine bölünmüştür (%70 eğitim, %30 test).
- **Logistic Regression** modeli, eğitim verisi üzerinde eğitilmiştir.
- Modelin başarımı **Test & Score** widget'ı kullanılarak değerlendirilmiştir.

### Model Performansı
Modelin doğruluğu ve performansı aşağıdaki metriklerle değerlendirilmiştir:
- **Accuracy**: Modelin doğruluk oranı.
- **F1-Score**: Dengesiz sınıflandırmalarda performans.
- **Precision** ve **Recall**: Modelin pozitif sınıflandırmalarını değerlendiren metrikler.

## Kullanılan Araçlar
- **Orange Data Mining**: Görsel programlama platformu, veri analizi ve makine öğrenmesi için kullanıldı.
- **Python**: Veri ön işleme ve analiz işlemleri için kullanıldı.
- **Matplotlib** ve **Seaborn**: Veri görselleştirme için kullanıldı.

## Proje Yapısı
- **orange_project.ows**: Orange iş akışı dosyası.
- **Students Performance in Exams.csv**: Veri setinin CSV formatındaki dosyası.
- **ReadMe_YourProject.md**: Proje açıklama dosyası.

## Proje Teslimi
Bu proje, YMT5270 ara sınav projesi kapsamında tamamlanmıştır. Proje, GitHub üzerinden teslim edilecektir.

## Yazar
- **Ad**: [Ömer Faruk KONCA]
- **Email**: [omerkonca01@gmail.com]

