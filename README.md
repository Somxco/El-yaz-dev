El-yaz-dev
MNIST Veri Seti ile MLP Tabanlı El Yazısı Rakam Tanıma
Test numarası 23120205010
Model Mimarisi ve Hiperparametreler
* Giriş Katmanı: 28x28 = 784 nöron (Flatten)
* Gizli Katman 1: 512 nöron, ReLU aktivasyonu
* Gizli Katman 2: 256 nöron, ReLU aktivasyonu
* Çıkış Katmanı: 10 nöron (Softmax - CrossEntropyLoss içinde)
* Optimizer: Adam (lr=0.001)
* Batch Size: 64
* Epoch: 15
* Kütüphane: PyTorch
* Deney Sonuçları
* Test Doğruluğu (Accuracy): %98.02
* Test Kaybı (Loss): 0.1047
* Eğitim Süresi: ~197 saniye (T4 GPU)
*Eğitim grafiklerinde train loss'un sürekli düşerken validation loss'un 2. epoch'tan sonra artmaya başlaması modelin **overfitting (aşırı öğrenme)** yaptığını göstermektedir. Karmaşıklık matrisinde modelin en çok 9 ile 7 ve 5 ile 3 rakamlarını karıştırdığı görüldü.
* İlk denemede ince kurşun kalem kullandığımda, çizgilerin OpenCV tarafından koparılması ve gölgeler yüzünden model rakamları okuyamadı (Yanlış tahmin).
* İkinci denemede kalın keçeli kalem kullandığımda görüntü işleme başarılı oldu.
* **Modelin Tahmini:** 232220205080
* **Gerçek Numara:** 23120205010
* *Sonuç Değerlendirmesi:* Model MNIST test setinde %98 başarı gösterse de, kendi el yazımda hatalar yaptı. Bunun nedeni dağılım kayması sorunudur. MNIST veri setindeki rakamlar kalın, düzgün ve ortalanmışken; benim yazdığım 1 rakamı eğik ve çentikli, 0 rakamları ise ovaldir. Bu durum, bir yapay zeka modelinin laboratuvar ortamındaki başarısının gerçek hayatta aynı olmayabileceğini kanıtlar.
