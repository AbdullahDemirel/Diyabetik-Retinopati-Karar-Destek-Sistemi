# 👁️ Açıklanabilir Derin Öğrenme Tabanlı Diyabetik Retinopati Karar Destek Sistemi

## 🎯 Proje Hakkında

Bu proje, diyabet hastalarında kalıcı körlüğe yol açabilen **Diyabetik Retinopati (DR)** hastalığının göz dibi (fundus) fotoğrafları üzerinden derin öğrenme mimarileri kullanılarak otomatik olarak sınıflandırılmasını amaçlamaktadır.

Sistem yalnızca bir tahmin üretmekle kalmaz; aynı zamanda **Açıklanabilir Yapay Zeka (XAI)** teknikleri sayesinde modelin hangi patolojik bölgelere odaklandığını **Grad-CAM ısı haritaları** ile görselleştirerek klinisyenlere destek sağlar.

---

# ✨ Özellikler

* 🔍 **5 Evreli Medikal Sınıflandırma Sistemi**

  * Retina görüntülerini ICDR standartlarına uygun şekilde 5 farklı evrede analiz eder.

* 🧠 **Grad-CAM ile Açıklanabilir Yapay Zeka**

  * Modelin hangi lezyonlara odaklandığını ısı haritası ile görselleştirir.

* 📊 **Class Weight Balancing**

  * Dengesiz medikal veri setlerine karşı sınıf ağırlık dengelemesi uygulanmıştır.

* 💻 **Streamlit Tabanlı Klinik Arayüz**

  * Kullanıcı dostu web paneli ile saniyeler içinde analiz yapılabilir.

---

# 🗂️ Veri Seti ve Hibrit Strateji

Modelin genelleme yeteneğini artırmak ve overfitting problemini azaltmak amacıyla 3 farklı açık kaynaklı veri seti birleştirilmiştir.

## Kullanılan Veri Setleri

* **APTOS 2019 Blindness Detection**
* **Messidor Dataset**
* **IDRiD Dataset**

| Özellik               | Değer                      |
| --------------------- | -------------------------- |
| Toplam Görüntü Sayısı | 5.861                      |
| Görüntü Türü          | Renkli Fundus Fotoğrafları |
| Veri Ayrımı           | %80 Eğitim / %20 Doğrulama |
| Giriş Boyutu          | 224x224                    |

---

# 🩺 Klinik Sınıflandırma Kategorileri (ICDR)

| Evre | Klinik Karşılığı | Açıklama                         |
| ---- | ---------------- | -------------------------------- |
| 0    | Normal           | Patolojik bulgu yok              |
| 1    | Hafif NPDR       | Mikroanevrizmalar mevcut         |
| 2    | Orta NPDR        | Kanama ve eksudalar mevcut       |
| 3    | Şiddetli NPDR    | Yoğun retinal hasar              |
| 4    | Proliferatif DR  | Yeni damar oluşumu ve ciddi risk |

---

# 📈 Model Evrimi ve Performans

Projede temel CNN mimarisinden başlayarak transfer learning ve fine-tuning teknikleriyle gelişmiş modeller tasarlanmıştır.

| Model         | Mimari                 | Accuracy  | Açıklama             |
| ------------- | ---------------------- | --------- | -------------------- |
| V1 - Baseline | Basic CNN              | %62       | İlk prototip         |
| V2 - Transfer | ResNet50               | %71       | Transfer Learning    |
| V3 - Balanced | MobileNetV2            | %78       | Class Weight desteği |
| V4 - Advanced | DenseNet121            | %84       | Fine-Tuning          |
| V5 - Ultra    | DenseNet121 + Grad-CAM | **%87.4** | Final model          |

## Eğitim Bilgileri

* ⏱️ Epoch: 10
* ⚙️ Optimizer: Adam
* 📉 Loss Function: Categorical Crossentropy

---

# 🔧 Kullanılan Teknolojiler

| Teknoloji          | Kullanım Amacı         |
| ------------------ | ---------------------- |
| TensorFlow / Keras | Model eğitimi          |
| DenseNet121        | Derin öğrenme mimarisi |
| OpenCV / PIL       | Görüntü işleme         |
| NumPy / Pandas     | Veri işleme            |
| Matplotlib         | Grafikler              |
| Grad-CAM           | Açıklanabilir AI       |
| Streamlit          | Web arayüzü            |

---

# ⚙️ Kurulum

## Gerekli Kütüphaneler

```bash
pip install tensorflow keras streamlit pandas numpy opencv-python matplotlib pillow
```

# 🚀 Projeyi Çalıştırma

```bash
streamlit run app.py
```

---

# 🌐 Tarayıcı Üzerinden Erişim

```plaintext
http://localhost:8501
```

---

# 📌 Geliştirme Süreci

* Hibrit veri seti oluşturuldu.
* Görüntüler normalize edildi.
* Veri artırma (augmentation) uygulandı.
* Class Weight Balancing kullanıldı.
* DenseNet121 Fine-Tuning gerçekleştirildi.
* Grad-CAM entegrasyonu yapıldı.
* Streamlit arayüzü geliştirildi.

---

# ⚠️ Sınırlılıklar ve Gelecek Çalışmalar

* Veri seti daha da genişletilebilir.
* TensorFlow Lite (TFLite) mobil entegrasyonu planlanmaktadır.
* Gerçek klinik testlerle sistemin validasyonu geliştirilecektir.
* Vision Transformer (ViT) mimarileri gelecekte denenebilir.

---

# ⚕️ Tıbbi Uyarı

Bu proje akademik amaçlarla geliştirilmiş bir klinik karar destek sistemidir. Üretilen sonuçlar kesin tıbbi teşhis yerine geçmez. Kesin değerlendirme için uzman bir göz doktoruna başvurulmalıdır.

---

# 👨‍💻 Geliştirici

**Abdullah Demirel**
İnönü Üniversitesi — Bilgisayar Mühendisliği
Yapay Zeka & Derin Öğrenme Çalışmaları
