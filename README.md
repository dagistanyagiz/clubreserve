# ClubReserve: Spor Tesisi Rezervasyon Uygulaması

ClubReserve, bir spor kompleksindeki halı saha, tenis kortu, voleybol salonu ve golf driving range için online rezervasyon yapılmasını sağlayan bir web uygulamasıdır. Kullanıcı spor türünü, tarihi, saati ve süreyi seçer, kapora bilgilerini görür ve rezervasyonunu oluşturur. Rezervasyonlar tarayıcıda (LocalStorage) saklanır ve "Rezervasyonlarım" bölümünden görüntülenip iptal edilebilir.

**Canlı demo:** `https://dagistanyagiz.github.io/clubreserve/`

![Uygulama ekran görüntüsü](screenshot.png)

## Özellikler

- **4 spor türü:** Futbol (halı saha), tenis, voleybol ve golf. Her birinin kendi sahası, fiyatı ve görseli var.
- **Takvim:** Ay ay gezilebilen takvim. Geçmiş günler seçilemez.
- **Saat seçimi:** 09:00 ile 22:30 arasında 90 dakikalık seanslar. Dolu saatler üstü çizili gösterilir.
- **Süre seçimi:** 60, 90 veya 120 dakika. Fiyat süreye göre otomatik hesaplanır.
- **Kapora ödemesi:** Toplam tutarın %30'u kapora olarak gösterilir, ödeme için banka bilgileri verilir.
- **Rezervasyonlarım:** Oluşturulan rezervasyonlar listelenir. Sayfa yenilense de kaybolmaz (LocalStorage).
- **İptal ve iade:** Kural uygunsa kullanıcı IBAN bilgilerini girerek kapora iadesi talep eder.
- **Duyarlı tasarım:** Masaüstü, tablet ve telefonda düzgün görünür.

## Kullanılan teknolojiler

| Teknoloji | Kullanım amacı |
|---|---|
| **Vite** | Geliştirme sunucusu ve derleme (build) aracı |
| **JavaScript (ES Modules)** | Uygulama mantığı: takvim, saat seçimi, fiyat hesaplama, rezervasyon ve iptal |
| **HTML5** | Sayfa yapısı |
| **CSS3 (saf CSS)** | Tasarım, grid düzenleri ve mobil uyum (media query) |
| **LocalStorage** | Rezervasyonları tarayıcıda saklama |
| **GitHub Pages + GitHub Actions** | Otomatik derleme ve canlıya alma |

## Kurulum ve çalıştırma

Bilgisayarınızda [Node.js](https://nodejs.org) (18 veya üzeri) kurulu olmalıdır.

```bash
# 1. Depoyu indirin
git clone https://github.com/dagistanyagiz/clubreserve.git
cd clubreserve

# 2. Bağımlılıkları kurun
npm install

# 3. Geliştirme sunucusunu başlatın
npm run dev
```

Terminalde çıkan adresi (genellikle `http://localhost:5173`) tarayıcıda açın.

Canlıya almak için derleme:

```bash
npm run build     # dist/ klasörüne derler
npm run preview   # derlenmiş hali yerelde önizler
```

## Proje yapısı

```
clubreserve/
├── index.html              # Sayfa yapısı ve pencereler (modal)
├── styles.css              # Tüm stiller
├── app.js                  # Uygulama mantığı
├── vite.config.js          # Vite ayarları
├── package.json            # Proje bilgileri ve komutlar
└── .github/workflows/
    └── deploy.yml          # GitHub Pages'e otomatik yayınlama
```

## Yapay zekanın kullanımı

Proje geliştirilirken yapay zeka asistanları (Claude, ChatGPT vb.) şu aşamalarda kullanıldı:

1. **Planlama:** Uygulama fikri (spor tesisi rezervasyonu), ekranlar (spor seçimi, takvim, özet paneli, ödeme ve iptal pencereleri) ve veri modeli (rezervasyon nesnesinin alanları) yapay zeka ile birlikte planlandı.
2. **Arayüz tasarımı:** Sayfa düzeni, renk paleti, kart yapıları ve mobil uyum için CSS önerileri alındı.
3. **Kod üretimi:** Takvim oluşturma, saat seçimi, süreye göre fiyat hesaplama ve LocalStorage kayıt/okuma fonksiyonları için yapay zekadan taslak kod alındı, sonra projeye uyarlandı.
4. **İş kuralları:** Kapora oranı (%30) ve 12 saatlik iptal/iade kuralı yapay zeka ile tartışılarak koda eklendi.
5. **Hata ayıklama ve inceleme:** Yapay zeka kodu inceleyip olası hataları gösterdi (örneğin ay geçişinde ayın 31'inde bir ayın atlanması, aynı saatin iki kez rezerve edilebilmesi).
6. **Kurulum ve dokümantasyon:** Projenin Vite yapısına geçirilmesi, GitHub Pages yayın ayarları ve bu README dosyasının taslağı yapay zeka ile hazırlandı.

Yapay zekanın ürettiği kodlar doğrudan kopyalanmadı; her parça tarayıcıda denenip kontrol edildikten sonra projeye eklendi.

## Bilinen eksikler ve geliştirme fikirleri

- Rezervasyonlar yalnızca kullanıcının kendi tarayıcısında saklanır; gerçek kullanımda bir sunucu ve veritabanı gerekir.
- Dolu saatler şu an örnek olarak sabit belirlenmiştir; ileride gerçek rezervasyonlara göre hesaplanabilir.
- Ödeme gerçek değildir, yalnızca akışı gösterir.
- Kullanıcı girişi ve tesis yönetim paneli eklenebilir.

## Geliştirici

**Dağıstan Yağız Yüce**
GitHub: [@dagistanyagiz](https://github.com/dagistanyagiz)
