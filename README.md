#  Veri Madenciliği Projesi – Şirket İflas Tahmini

Bu projede, finansal oranlara dayalı olarak şirketlerin **iflas (bankrupt)** durumlarının tahmin edilmesi ve veri yapısının keşfedilmesi amaçlanmıştır. Proje sürecinde aşağıdaki adımlar gerçekleştirilmiştir:

###  1. Veri Analizi
- Veri seti 6819 örnek ve 95 finansal özellik içermektedir.
- Hedef değişken: `Bankrupt?` (0: iflas etmemiş, 1: iflas etmiş).
- Eksik veriler hem **medyan ile** hem de **KNNImputer** ile doldurulmuştur.
- Aykırı değerler Z-score ve IQR yöntemleriyle analiz edilmiştir.
- Özellik önem dereceleri **Random Forest** ile hesaplanmıştır.

### 2. Sınıflama (Classification)
- Logistic Regression, SVM ve Random Forest modelleri karşılaştırılmıştır.
- Performanslar doğruluk, karışıklık matrisi, classification report ve ROC eğrileri ile değerlendirilmiştir.

###  3. Kümeleme (Clustering)
- KMeans, DBSCAN ve Agglomerative Clustering algoritmaları uygulanmıştır.
- Kümeler, gerçek sınıf etiketleri ile karşılaştırılmış; homogeneity, v-measure, ARI gibi metriklerle ölçülmüştür.
- Kümeleme sonuçları **PCA ile 2 boyutlu görselleştirilmiştir**.
- DBSCAN için eps ve min_samples parametreleri grid-search ile optimize edilmiştir.
- KMeans için optimal küme sayısı **Elbow yöntemi** ile analiz edilmiştir.

---

Bu analizler sayesinde, sınıflandırma algoritmalarının başarımı değerlendirilmiş ve kümeleme yöntemlerinin veri yapısını ne ölçüde yansıttığı ortaya konmuştur.
