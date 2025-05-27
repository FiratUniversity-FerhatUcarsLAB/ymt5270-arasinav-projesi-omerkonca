# YMT5270 Ara Sınav Projesi: Orange ile Veri Analizi ve Makine Öğrenmesi

## Öğrenci Bilgileri
- **Ad Soyad**: Ömer Faruk Konca
- **Öğrenci Numarası**: 241137129
- **E-posta**: omerkonca01@gmail.com

## Proje Özeti
Bu projede, öğrencilerin sınav başarılarını etkileyen faktörleri analiz etmek ve başarı durumlarını sınıflandırmak amacıyla "Students Performance in Exams" veri seti kullanılmıştır. Orange Data Mining platformu ile görsel programlama ortamında Keşifsel Veri Analizi (EDA) gerçekleştirilmiş ve ardından sınıflandırma problemleri için makine öğrenmesi modelleri uygulanmıştır. Projede Logistic Regression, Random Forest ve Naive Bayes algoritmaları karşılaştırılmış ve en iyi performansı Random Forest modeli göstermiştir. Proje, hem EDA teknikleri hem de makine öğrenmesi modelleme süreçlerini içeren kapsamlı bir çalışma sunmaktadır.

## Veri Seti
### Veri Seti Bilgileri
- **Veri Seti Adı**: Students Performance in Exams
- **Kaynak**: [Kaggle - spscientist](https://www.kaggle.com/datasets/spscientist/students-performance-in-exams)
- **Lisans**: CC0: Public Domain
- **Veri Seti Boyutu**: 1000 satır, 8 sütun

### Veri Seti Tanımı
Veri seti, öğrencilerin cinsiyeti, ebeveyn eğitim düzeyi, öğle yemeği türü ve sınavlara hazırlık kursuna katılıp katılmadığı gibi demografik bilgilerle birlikte matematik, okuma ve yazma notlarını içermektedir. Bu öznitelikler ile öğrencilerin genel akademik başarıları arasındaki ilişkiler incelenmiştir.

### Öznitelik Açıklamaları
| Öznitelik Adı | Veri Tipi | Açıklama | Örnek Değer |
|---------------|-----------|----------|-------------|
| gender | Kategorik | Öğrencinin cinsiyeti | "female" |
| race/ethnicity | Kategorik | Öğrencinin etnik grubu | "group B" |
| parental level of education | Kategorik | Ebeveynin eğitim seviyesi | "bachelor's degree" |
| lunch | Kategorik | Öğle yemeği türü | "standard" |
| test preparation course | Kategorik | Test hazırlık kursuna katılım | "completed" |
| math score | Sayısal | Matematik sınav puanı | 66 |
| reading score | Sayısal | Okuma sınav puanı | 70 |
| writing score | Sayısal | Yazma sınav puanı | 74 |

## Keşifsel Veri Analizi (Explanatory Data Analysis - EDA)
### Temel İstatistikler
- Öğrencilerin ortalama matematik puanı: 66.09
- Ortalama okuma puanı: 69.17
- Ortalama yazma puanı: 68.05
- Cinsiyet, öğle yemeği türü ve kurs katılımı gibi kategorik değişkenlerde dengesizlikler gözlemlendi.

### Veri Ön İşleme
- Eksik veri bulunmamaktadır.
- Aykırı değerler Box Plot yardımıyla incelenmiştir.
- Kategorik değişkenler Orange tarafından otomatik olarak dönüştürülmüştür.
- Math score sınıflandırma için “Geçti” (>=50) ve “Kaldı” (<50) olarak etiketlenmiştir (Select Columns → Feature Constructor kullanıldı).

### Görselleştirmeler

#### Görselleştirme 1: Box Plot – Lunch Türüne Göre Math Score
![Box Plot](goruntuler/lunch_boxplot.png)
> Test hazırlık kursuna katılan öğrencilerde puan ortalamalarının daha yüksek olduğu gözlemlenmiştir.

#### Görselleştirme 2: Scatter Plot – Reading vs Writing
![Scatter Plot](goruntuler/reading_writing_scatter.png)
> Okuma ve yazma puanları arasında güçlü bir pozitif korelasyon olduğu görülmüştür.

### Öznitelik İlişkileri
Scatter plot ve correlation widget'ları ile güçlü korelasyonlar tespit edilmiştir:
- Reading ↔ Writing: 0.87
- Math ↔ Reading: 0.64

## Makine Öğrenmesi Uygulaması
### Kullanılan Yöntem
Sınıflandırma yöntemi kullanılmıştır. Hedef değişken olarak math score'un sınıflandırılmış versiyonu ("Pass"/"Fail") seçilmiştir.

### Modeller ve Parametreler
- **Logistic Regression** (varsayılan ayarlar)
- **Random Forest** (Trees=10)
- **Naive Bayes** (varsayılan)

### Model Değerlendirmesi

#### Metrikler
| Model | Accuracy | Precision | Recall | F1-Score |
|-------|----------|-----------|--------|----------|
| Logistic Regression | 0.83 | 0.84 | 0.81 | 0.825 |
| Random Forest | **0.87** | 0.88 | 0.85 | **0.865** |
| Naive Bayes | 0.79 | 0.80 | 0.78 | 0.79 |

### Sonuçların Yorumlanması
Random Forest modeli, diğer iki modele göre daha yüksek doğruluk ve F1-skoru göstermiştir. Bu durum, veri setinde kategorik ve sayısal verilerin birlikte etkili işlendiğini göstermektedir. Logistic Regression da tatmin edici sonuçlar vermiştir. Daha fazla model (k-NN, SVM) denenerek performans iyileştirilebilir.

## Orange İş Akışı
![Orange İş Akışı](goruntuler/orange_workflow.png)

İş akışı şu adımları içermektedir:
- Veri okuma
- Sütun seçimi ve dönüştürme
- Görselleştirme (box plot, scatter)
- Modelleme (3 farklı sınıflandırıcı)
- Performans karşılaştırması

## Sonuç ve Öneriler
Proje sonucunda demografik verilerin sınav başarıları üzerinde etkili olduğu görülmüştür. Özellikle test hazırlık kursunun başarıya katkısı dikkat çekicidir. Gelecekte daha büyük ve farklı veri setleri ile bu analizler genişletilebilir. Ayrıca diğer makine öğrenmesi algoritmaları ile karşılaştırma yapılabilir.

## Kaynaklar
1. https://www.kaggle.com/datasets/spscientist/students-performance-in-exams  
2. https://orangedatamining.com  
3. Orange Docs & Tutorials  

## Ekler
### Orange Proje Dosyası
> [students-performance.ows](project/students-performance.ows)

### Veri Seti Dosyası veya Bağlantısı
> [StudentsPerformance.csv](https://www.kaggle.com/datasets/spscientist/students-performance-in-exams)
