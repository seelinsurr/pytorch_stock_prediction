> 📄 **Sunum Dosyası:** Projenin sunum slaytlarına [buradan](./stock_market_analysis_slides.pptx) ulaşabilirsiniz.                                                    📈 PyTorch ile Borsa Analizi ve Hisse Senedi Tahmini                                                    
Bu proje, teknoloji devlerinin (Apple, Amazon, Google, Microsoft) geçmiş hisse senedi verilerini analiz etmeyi ve **PyTorch** kullanarak Derin Öğrenme modelleri (**LSTM ve GRU**) ile gelecek fiyat tahminleri yapmayı amaçlamaktadır.

## 🚀 Proje Adımları ve Özellikler

* **Keşifsel Veri Analizi (EDA):** `yfinance` kütüphanesi ile Yahoo Finance üzerinden geçmiş veriler çekildi. Günlük getiriler, hareketli ortalamalar (Moving Averages) ve hisseler arası korelasyon analizleri yapıldı.
* **Veri Ön İşleme:** Modelin daha iyi öğrenebilmesi için Kapanış (Close) fiyatları `MinMaxScaler` ile [0, 1] aralığına ölçeklendirildi. Zaman serisi verisi, kayan pencere (sliding window) yöntemiyle son 60 güne bakarak bir sonraki günü tahmin edecek şekilde yeniden yapılandırıldı.
* **PyTorch Entegrasyonu:** NumPy dizileri PyTorch Tensor'lerine dönüştürüldü ve eğitim sürecini optimize etmek için `DataLoader` ile batch'ler (16'lık paketler) halinde modellere beslendi.
* **Derin Öğrenme Modelleri:** PyTorch `nn.Module` yapısı kullanılarak iki farklı mimari inşa edildi:
  * 2 Katmanlı **LSTM** Modeli
  * 2 Katmanlı **GRU** Modeli (Dropout = 0.2)
* **Değerlendirme:** Modeller Mean Squared Error (MSE) loss fonksiyonu ve Adam optimizer ile eğitildi. Başarımları Root Mean Squared Error (RMSE) metriği ile ölçüldü.

## 📊 Model Karşılaştırması (LSTM vs. GRU)

Proje sonucunda her iki modelin de test verisi üzerindeki performansı ve eğitim süreleri karşılaştırılmıştır:
* GRU modeli, daha az parametre içerdiği için LSTM'e kıyasla daha hızlı eğitilmiştir.
* Her iki modelin de test tahminleri ters dönüşüm (inverse transform) ile orijinal fiyat ölçeğine getirilmiş ve doğruluklarını görsel olarak değerlendirmek için gerçek kapanış fiyatlarıyla birlikte grafiğe dökülmüştür.

## 🛠️ Kullanılan Teknolojiler
* **Dil:** Python 3
* **Veri Çekme & İşleme:** yfinance, Pandas, NumPy, Scikit-Learn
* **Görselleştirme:** Matplotlib, Seaborn
* **Derin Öğrenme Çerçevesi:** PyTorch,

    
