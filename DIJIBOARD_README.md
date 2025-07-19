# 🗺️ Gaziantep Şehitkamil Dijiboard Yönetim Sistemi

Gaziantep'in Şehitkamil ilçesinde dijital billboard (dijiboard) lokasyonlarını gösteren interaktif harita uygulaması.

## 🎯 Özellikler

### ✨ Ana Özellikler
- **İnteraktif Harita**: Leaflet harita teknolojisi ile Şehitkamil bölgesini gösteren harita
- **Durum Bazlı Marker'lar**: 
  - 🟢 **Yeşil**: Müsait dijiboard'lar
  - 🔴 **Kırmızı**: Kiralı dijiboard'lar  
  - 🟡 **Sarı**: Bakımda olan dijiboard'lar
- **WhatsApp Entegrasyonu**: Müsait dijiboard'lar için doğrudan WhatsApp iletişimi
- **Responsive Tasarım**: Mobil ve masaüstü uyumlu arayüz

### 🛠️ Admin Paneli
- **Kolay Giriş**: Demo şifre ile admin paneline erişim (`admin123`)
- **CRUD İşlemleri**: Dijiboard ekleme, düzenleme, silme
- **Durum Güncelleme**: Hızlı durum değiştirme (Müsait/Kiralı/Bakım)
- **Gerçek Zamanlı Güncelleme**: Değişiklikler anında haritaya yansır

### 📊 İstatistikler
- Toplam dijiboard sayısı
- Durum bazında dağılım görüntüleme
- Son güncelleme bilgileri

## 🚀 Kurulum ve Çalıştırma

### Gereksinimler
- Node.js (v16 veya üzeri)
- npm veya yarn

### 1. Gerekli Paketleri Yükle

Projeye eklenen paketleri yüklemek için:

```bash
npm install
# veya
yarn install
```

**Yeni Eklenen Paketler:**
- `leaflet`: Harita kütüphanesi
- `react-leaflet`: React Leaflet entegrasyonu
- `@types/leaflet`: TypeScript tip tanımları

### 2. Geliştirme Sunucusunu Başlat

```bash
npm run dev
# veya
yarn dev
```

### 3. Uygulamaya Erişim

Tarayıcınızda şu adrese gidin:
```
http://localhost:5173/dijiboard
```

## 📱 Kullanım Kılavuzu

### Kullanıcı İşlemleri

1. **Harita Gezinme**: Mouse ile haritayı kaydırın, zoom yapın
2. **Marker İnceleme**: Harita üzerindeki renkli marker'lara tıklayın
3. **Detay Görüntüleme**: Popup'ta dijiboard detaylarını inceleyin
4. **WhatsApp İletişim**: Müsait dijiboard'lar için "WhatsApp ile İletişim" butonuna tıklayın

### Admin İşlemleri

1. **Admin Panel Erişimi**: Sağ üst köşedeki "Admin Panel" butonuna tıklayın
2. **Giriş**: Şifre: `admin123`
3. **Yeni Dijiboard Ekleme**: "Yeni Dijiboard" butonunu kullanın
4. **Durum Güncelleme**: Dijiboard listesinde durum seçiciyi kullanın
5. **Düzenleme/Silme**: Edit ve çöp kutusu butonlarını kullanın

## 🗂️ Proje Yapısı

```
src/
├── components/
│   ├── DijiboardMap.tsx         # Ana harita komponenti
│   ├── AdminPanel.tsx           # Admin yönetim paneli
│   └── Layout.tsx               # Ana layout (güncellenmiş)
├── data/
│   └── dijiboards.ts           # Dijiboard verileri ve yardımcı fonksiyonlar
├── types/
│   └── dijiboard.ts            # TypeScript tip tanımları
└── pages/
    └── Dijiboard.tsx           # Ana dijiboard sayfası
```

## 🎨 Özelleştirme

### Environment Variables ile Konfigürasyon

**Artık tüm ayarlar environment variables ile yapılıyor!**

#### Local Development için .env dosyası oluşturun:
```bash
# saitamanot/.env dosyası oluşturun
VITE_WHATSAPP_NUMBER=+905442906327
VITE_ADMIN_PASSWORD=admin123
VITE_MAP_CENTER_LAT=37.0662
VITE_MAP_CENTER_LNG=37.3833
VITE_MAP_DEFAULT_ZOOM=13
VITE_MAP_MIN_ZOOM=10
VITE_MAP_MAX_ZOOM=18
VITE_ENABLE_LOCATION_SELECTION=true
```

#### Production Deployment (Vercel/Netlify):
Environment variables otomatik olarak `vercel.json` dosyasından alınır.

**Detaylı konfigürasyon için `ENV_CONFIG.md` dosyasına bakın.**

### Yeni Dijiboard Ekleme
Admin paneli üzerinden veya doğrudan `src/data/dijiboards.ts` dosyasını düzenleyerek:

```typescript
{
  id: "DB009",
  lat: 37.0720,
  lng: 37.3890,
  address: "Yeni Mahalle, Yeni Sokak",
  status: "empty",
  size: "5x3m",
  price: "4.500₺/ay",
  lastUpdated: "2025-01-15",
  description: "Açıklama"
}
```

## 💾 Veri Saklama

- Dijiboard verileri tarayıcının `localStorage`'ında saklanır
- İlk açılışta örnek veriler otomatik yüklenir
- Admin paneli üzerinden yapılan değişiklikler kalıcı olarak saklanır

## 🌐 Canlı Demo

Uygulamayı çalıştırdıktan sonra şu özelliklerle test edebilirsiniz:

1. **8 Örnek Dijiboard**: Şehitkamil'in farklı noktalarında
2. **3 Farklı Durum**: Müsait, kiralı, bakımda örnekleri
3. **Gerçekçi Veriler**: Adres, fiyat, boyut bilgileri
4. **Çalışan WhatsApp Entegrasyonu**: +90 544 290 63 27

## 🔧 Teknik Detaylar

- **Framework**: React 18 + TypeScript
- **Styling**: Tailwind CSS + shadcn/ui
- **Harita**: Leaflet + React Leaflet
- **State Management**: React Hooks + localStorage
- **Icons**: Lucide React
- **Build Tool**: Vite

## 📝 Notlar

- Leaflet CSS'i otomatik olarak yüklenir
- Marker iconları SVG olarak dinamik oluşturulur
- Responsive tasarım mobil cihazlarda optimize edilmiştir
- WhatsApp entegrasyonu tüm platformlarda çalışır

## 🐛 Sorun Giderme

**Harita Görünmüyor:**
- Leaflet paketlerinin doğru yüklendiğinden emin olun
- Konsol hatalarını kontrol edin

**Admin Panel Açılmıyor:**
- Şifrenin doğru girildiğinden emin olun: `admin123`

**WhatsApp Linki Çalışmıyor:**
- Tarayıcınızın popup'ları engellediğini kontrol edin

## 🤝 Katkıda Bulunma

1. Projeyi fork edin
2. Feature branch oluşturun (`git checkout -b feature/amazing-feature`)
3. Değişikliklerinizi commit edin (`git commit -m 'Add amazing feature'`)
4. Branch'inizi push edin (`git push origin feature/amazing-feature`)
5. Pull Request açın

## 📄 Lisans

Bu proje MIT lisansı altında lisanslanmıştır.

---

**İletişim**: +90 544 290 63 27 (WhatsApp)
**Geliştirici**: Dijiboard Yönetim Sistemi 