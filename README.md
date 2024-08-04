# Parkinson Hastalığı Veri Seti ve Makine Öğrenmesi Analizi

Bu proje, Parkinson hastalığını teşhis etmek ve ilerleyişini izlemek amacıyla çeşitli biyomedikal ses kayıtlarından elde edilen özellikleri içeren bir veri seti üzerinde gerçekleştirilmiştir. Parkinson hastalığı, sinir sistemini etkileyen ve motor kontrol bozuklukları ile karakterize edilen kronik bir hastalıktır. Bu veri seti, Parkinson hastalarının ve sağlıklı bireylerin seslerinden elde edilen özelliklere dayanarak hastalığın var olup olmadığını sınıflandırmak için kullanılmıştır.

## İçindekiler

- [Veri Seti](#veri-seti)
- [Kullanılan Yöntemler](#kullanılan-yöntemler)
- [Sonuçlar](#sonuçlar)
- [Yükleme ve Kullanım](#yükleme-ve-kullanım)

## Veri Seti

Veri seti, Parkinson hastalığı teşhisi ve ilerleyişinin izlenmesi için ses kayıtlarından elde edilen biyomedikal özellikleri içerir. Özellikler, hastaların ve sağlıklı bireylerin seslerinden elde edilmiştir. Veri setinde yer alan özellikler şunları içerir:
- id: Her bir gözlemin benzersiz kimliği.
- gender: Cinsiyet bilgisi (1: Erkek, 0: Kadın).
- PPE: Tepe-taban genliği enerjisi.
- DFA: Detrended Fluctuation Analysis (Trendden Arındırılmış Dalgalanma Analizi) skoru.
- RPDE: Recurrence Period Density Entropy (Yinelenen Dönem Yoğunluk Entropisi) skoru.
- numPulses: Algılanan nabız sayısı.
- numPeriodsPulses: Nabız periyotlarının sayısı.
- meanPeriodPulses: Ortalama nabız periyodu.
- stdDevPeriodPulses: Nabız periyotlarının standart sapması.
- locPctJitter: Lokal yüzdelik titreme.
- tqwt_kurtosisValue_dec_1 - tqwt_kurtosisValue_dec_36: TQWT (Tunable Q-factor Wavelet Transform) kullanılarak elde edilen dekürsis (kurtosis) değerleri.

## Kullanılan Yöntemler

Bu projede aşağıdaki makine öğrenmesi yöntemleri kullanılmıştır:
- **K-En Yakın Komşu (KNN)**: Manhattan mesafe ölçütü kullanılarak modellenmiştir.
- **Destek Vektör Makineleri (SVM)**: Doğrusal çekirdek ile modellenmiştir.
- **Naive Bayes**: Gaussian Naive Bayes sınıflandırıcısı kullanılmıştır.
- **Karar Ağaçları (Decision Tree)**: Gini kriteri kullanılarak modellenmiştir.
- **Oylama Sınıflandırıcısı (Voting Classifier)**: KNN, SVM, Karar Ağaçları ve Naive Bayes algoritmalarının birleşiminden oluşmuştur.
- **Lojistik Regresyon**: Max iterasyon sayısı 2000 ve 'liblinear' çözümleyici kullanılmıştır.

## Sonuçlar

Sonuçlar, her bir modelin doğruluk, precision, recall ve F1 skoru metriklerini içermektedir. Performans karşılaştırması grafiklerle sunulmuştur.

### Örnek Sonuçlar

- **KNN**: Yüksek doğruluk oranı, precision, recall ve F1 skoru.
- **SVM**: İyi doğruluk oranı ve recall, ancak precision daha düşük olabilir.
- **Naive Bayes**: Düşük doğruluk oranı ancak iyi recall.
- **Karar Ağaçları**: İyi sonuçlar elde edilebilir, fakat aşırı uyum riski vardır.
- **Oylama Sınıflandırıcısı**: Tüm modellerin güçlü yönlerini birleştirir.

## Yükleme ve Kullanım

1. **Veri Seti**: Veri setini `Parkinson_Dataset.csv` dosyası ile elde edebilirsiniz.
2. **Bağımlılıklar**: Gerekli Python kütüphanelerini yüklemek için `requirements.txt` dosyasını kullanabilirsiniz. Örneğin:
    ```bash
    pip install pandas matplotlib scikit-learn seaborn
    ```
3. **Kodun Çalıştırılması**: Kod dosyalarını çalıştırarak modelleri eğitebilir ve performanslarını değerlendirebilirsiniz.

---

Bu proje ile ilgili daha fazla bilgi ve güncellemeler için [GitHub Sayfası](https://github.com/SukriyeKaramann/machine-learning) adresini ziyaret edebilirsiniz.
