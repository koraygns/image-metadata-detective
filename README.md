# 📸 EXIF / XMP / IPTC Okuyucu + AI & Kaynak Analizi
![WebDedik Görsel Metadata Analiz Aracı](https://www.webdedik.com/storage/uploads/banners/exif-metadata-okuyucu-nedir-ai-uretimi-ve-sosyal-medya-kaynagini-tespit-eden-gel.webp)
Modern, tarayıcı tabanlı bir görsel metadata analiz aracı. EXIF, XMP, IPTC, GPS ve ICC verilerini okur, yapay zekâ üretimi ve sosyal medya kaynak analizi için kanıt tabanlı raporlar üretir.

## ✨ Özellikler

### 🔍 Metadata Okuma
- **EXIF**: Kamera bilgileri, çekim parametreleri (ISO, diyafram, enstantane, odak uzunluğu)
- **XMP**: Adobe metadata, yazılım bilgileri, düzenleme geçmişi
- **IPTC**: Fotoğrafçı bilgileri, telif hakları, açıklamalar
- **GPS**: Konum koordinatları ve harita linkleri
- **ICC**: Renk profilleri

### 🤖 AI Üretimi Tespiti
Gelişmiş heuristik algoritmalar ile yapay zekâ ile üretilmiş görselleri tespit eder:

- **AI Araç İzleri**: ChatGPT, Gemini, DALL-E, Midjourney, Stable Diffusion, Adobe Firefly ve 15+ AI aracı
- **Metadata Analizi**: AI keyword'leri, watermark'lar, prompt/seed terimleri
- **Kombinasyon Analizi**: Kamera bilgisi yok + Yazılım var + Tarih yok gibi güçlü göstergeler
- **Görsel Özellikleri**: Standart AI boyutları (512x512, 1024x1024), kare format analizi
- **Program Tespiti**: 3D modelleme (Blender, Maya, Unreal), edit yazılımları (Photoshop, Lightroom)

### 📱 Sosyal Medya Kaynak Analizi
Görselin hangi platformdan geçmiş olabileceğini tespit eder:

- **Platform İzleri**: Instagram, Facebook, WhatsApp, Telegram, Twitter/X, TikTok, Snapchat, Discord, Reddit, Google Photos
- **Metadata Temizliği**: Sosyal medya platformlarının metadata'yı silme/azaltma davranışı analizi
- **Kaynak İpuçları**: URL, Source, DocumentID gibi alanlar

### 📊 Detaylı Raporlar
- **Kategorize Edilmiş Bulgular**: Genel özet, kamera bilgileri, tarih bilgileri, konum, yazılım, metadata bütünlüğü
- **Kanıt Tabanlı Analiz**: Her bulgu için açıklamalar ve olasılık skorları
- **Görselleştirme**: Renk kodlu kartlar (yeşil/sarı/kırmızı), badge'ler, özet panelleri
- **Export**: JSON ve HTML formatında rapor indirme

### 🔒 Gizlilik & Güvenlik
- **100% Offline**: Tüm işlemler tarayıcıda yapılır, dosya dışarı gönderilmez
- **Yerel Dosyalar**: İnternet bağlantısı gerektirmez (exifr kütüphanesi dahil)
- **File:// Protokolü**: Doğrudan dosya sisteminden açılabilir

## 🚀 Kullanım

### Hızlı Başlangıç

1. **Dosyaları İndir**
   ```bash
   git clone <repo-url>
   cd exif
   ```

2. **Tarayıcıda Aç**
   - `index.html` dosyasını çift tıklayarak açın
   - Veya tarayıcıda `file:///path/to/exif/index.html` adresini açın

3. **Görsel Yükle**
   - "Dosya Seç" butonuna tıklayın
   - Veya görseli sürükle-bırak alanına sürükleyin

4. **Raporu İncele**
   - Önizleme & Özet bölümünde hızlı bilgileri görün
   - "Rapor" sekmesinde detaylı bulguları okuyun
   - "Kanıtlar" sekmesinde hangi alanların ipucu verdiğini görün
   - "Ham Metadata" sekmesinde tüm metadata'yı JSON formatında inceleyin

### Rapor İndirme

- **JSON İndir**: Tüm analiz sonuçlarını JSON formatında indirin
- **HTML İndir**: Paylaşılabilir HTML raporu oluşturun

## 📁 Dosya Yapısı

```
exif/
├── index.html          # Ana uygulama dosyası
├── exifr.full.js      # Exifr kütüphanesi (full versiyon, UMD format)
├── exifr.min.js        # Exifr kütüphanesi (lite versiyon, yedek)
├── logo.webp          # Logo dosyası
└── README.md          # Bu dosya
```

## 🎯 Kullanım Senaryoları

### 1. Fotoğrafçılık
- Kamera ayarlarını kontrol etme
- Çekim tarih/saat bilgilerini görme
- GPS koordinatlarını haritada görüntüleme
- Lens ve teknik detayları inceleme

### 2. AI İçerik Tespiti
- Yapay zekâ ile üretilmiş görselleri tespit etme
- AI araç izlerini bulma
- Metadata temizliğine göre AI olasılığını değerlendirme

### 3. Sosyal Medya Analizi
- Görselin hangi platformdan geçtiğini anlama
- Metadata silinme/azaltma davranışını analiz etme
- Kaynak tespiti

### 4. Gizlilik Kontrolü
- GPS koordinatlarını tespit etme
- Kişisel bilgilerin metadata'da olup olmadığını kontrol etme
- Paylaşmadan önce hassas bilgileri temizleme

## 🔬 Teknik Detaylar

### Desteklenen Formatlar
- JPEG / JPG
- PNG
- WebP
- HEIC (tarayıcı desteğine bağlı)
- TIFF (sınırlı)

### Metadata Alanları
- **Kamera**: Make, Model, LensModel, ISO, FNumber, ExposureTime, FocalLength
- **Tarih**: DateTimeOriginal, CreateDate, ModifyDate, MetadataDate
- **Yazılım**: Software, ProcessingSoftware, CreatorTool, xmp:CreatorTool
- **Konum**: GPSLatitude, GPSLongitude, GPSAltitude
- **Diğer**: UserComment, Description, Title, Copyright, Artist

### AI Tespit Algoritması

Program, aşağıdaki faktörlere göre AI olasılığını hesaplar:

1. **Doğrudan AI Araç İzleri** (0-70%): Metadata'da AI aracı isimleri
2. **AI Keyword'leri** (0-50%): "generated", "synthetic", "AI-generated" gibi terimler
3. **Kombinasyon Analizi** (0-45%): Kamera yok + Yazılım var + Tarih yok
4. **Metadata Temizliği** (0-40%): Hiç EXIF alanı yok
5. **Program Tespiti** (0-35%): AI/3D yazılımları
6. **Görsel Özellikleri** (0-15%): Standart AI boyutları, kare format
7. **Kombinasyon Bonusu** (0-30%): Birden fazla gösterge bir arada

**Skor Eşikleri:**
- **Yüksek** (≥60%): Yüksek olasılıkla AI üretimi
- **Orta** (35-59%): Olası AI üretimi veya metadata silinmiş
- **Düşük** (<35%): Muhtemelen gerçek fotoğraf

## 🛠️ Teknolojiler

- **Vanilla JavaScript**: Framework bağımlılığı yok
- **Exifr**: Güçlü metadata okuma kütüphanesi
- **UMD Format**: File:// protokolü ile çalışır
- **Modern CSS**: Gradient'ler, animasyonlar, responsive tasarım
- **ES6+**: Modern JavaScript özellikleri

## 📝 Notlar

### Sınırlamalar
- Metadata yoksa kesin sonuç verilemez
- Bazı platformlar metadata'yı tamamen siler
- AI tespiti olasılık bazlıdır, kesin değildir
- HEIC formatı tüm tarayıcılarda desteklenmeyebilir

### Önemli Uyarılar
- GPS koordinatları gizlilik riski oluşturabilir
- Metadata analizi %100 doğru değildir
- AI tespiti heuristik kurallara dayanır, kesin sonuç değildir

## 🤝 Katkıda Bulunma

Katkılarınızı bekliyoruz! Lütfen:
1. Fork edin
2. Feature branch oluşturun (`git checkout -b feature/amazing-feature`)
3. Commit edin (`git commit -m 'Add amazing feature'`)
4. Push edin (`git push origin feature/amazing-feature`)
5. Pull Request açın

## 📄 Lisans

Bu proje açık kaynaklıdır. İstediğiniz gibi kullanabilir, değiştirebilir ve dağıtabilirsiniz.

## 🙏 Teşekkürler

- [Exifr](https://github.com/MikeKovarik/exifr) - Güçlü metadata okuma kütüphanesi
- Tüm katkıda bulunanlar

---

**Not**: Bu araç, metadata analizi yapar ve olasılık bazlı sonuçlar üretir. Kesin kaynak/üretim yöntemi bazı durumlarda metadata yoksa doğrulanamaz.

