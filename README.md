# 👁️ Açıklanabilir Derin Öğrenme Tabanlı Diyabetik Retinopati Karar Destek Sistemi



Bu proje; diyabet hastalarında körlüğe yol açabilen Diyabetik Retinopati (DR) hastalığının, göz dibi (retina) fotoğrafları üzerinden yapay zeka ile otomatik, 5 evreli sınıflandırılmasını ve karar mekanizmasının hekime görsel olarak açıklanmasını sağlayan klinik bir karar destek sistemidir.

## ✨ Özellikler

* 🔍 **5 Evreli Sınıflandırma:** Retina görüntüsünü klinik standartlara uygun olarak Sağlıklı, Hafif, Orta, Şiddetli ve İleri Seviye olarak sınıflandırır.
* 🧠 **Açıklanabilir Yapay Zeka (XAI):** Grad-CAM algoritması kullanarak modelin karara varırken retinadaki hangi patolojik lezyonlara ve kanamalara odaklandığını ısı haritası (heat-map) ile görselleştirir.
* 📊 **Sınıf Dengelenmesi:** Medikal veri setlerindeki dengesiz dağılım problemini `Class Weight Balancing` tekniği ile çözer.
* 💻 **Kullanıcı Dostu Arayüz:** Streamlit tabanlı, hekimlerin ve sağlık çalışanlarının kolayca görsel yükleyip saniyeler içinde analiz alabileceği web arayüzü.

## 📦 Teknolojiler ve Kütüphaneler

| Kategori | Kullanılan Teknoloji / Kütüphane |
| :--- | :--- |
| **Ana Model** | DenseNet121 (Fine-Tuned) |
| **Deep Learning Framework** | TensorFlow, Keras |
| **Veri İşleme & Matris** | Pandas, NumPy |
| **Görüntü İşleme** | OpenCV / PIL |
| **Arayüz (Frontend/Demo)** | Streamlit |
| **Görselleştirme** | Matplotlib (Eğitim Grafikleri & Grad-CAM) |

## 📊 Veri Seti ve Hibrit Strateji

Modelin tek bir klinik merkeze bağımlı kalıp ezber yapmasını (overfitting) önlemek amacıyla literatürdeki 3 büyük açık kaynaklı veri seti birleştirilerek **5.861 görüntülük hibrit bir havuz** oluşturulmuştur:
* **APTOS 2019** Blindness Detection
* **Messidor** Evaluation Dataset
* **IDRiD** (Indian Diabetic Retinopathy Image Dataset)

*Veri Ayrımı:* %80 Eğitim (Training) / %20 Doğrulama (Validation)

## 📈 Model Performansı ve Evrimi

Proje sürecinde temel CNN mimarilerinden başlayıp Transfer Learning aşamalarından geçen 5 basamaklı bir model evrimi (V1 - V5 Ultra) tasarlanmıştır.

* **Eğitim Süresi:** Toplam **10 Epoch (92 step/epoch)** sürdü.
* **Başarı Oranı:** Final modelimiz olan V5 Ultra, hibrit test seti üzerinde **%87'nin üzerinde genel doğruluk (accuracy)** değerine ulaşmıştır.

## 🛠️ Çalıştırma Adımları

1. Gerekli kütüphaneleri yükleyin:
```bash
pip install tensorflow keras streamlit pandas numpy opencv-python matplotlib

2. Streamlit arayüzünü ayağa kaldırın:
```streamlit
streamlit run app.py
