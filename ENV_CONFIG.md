# 🔧 Environment Variables Konfigürasyonu

Bu dokümanda Dijiboard Yönetim Sistemi için kullanılan environment variables açıklanmıştır.

## 📋 Environment Variables Listesi

### 🔗 İletişim Ayarları

#### `VITE_WHATSAPP_NUMBER`
- **Açıklama**: WhatsApp iletişim numarası
- **Varsayılan**: `+905442906327`
- **Format**: `+90XXXXXXXXXX` (ülke kodu ile birlikte)
- **Örnek**: `VITE_WHATSAPP_NUMBER=+905551234567`

### 🔐 Güvenlik Ayarları

#### `VITE_ADMIN_PASSWORD`
- **Açıklama**: Admin paneli giriş şifresi
- **Varsayılan**: `admin123`
- **Güvenlik**: Production'da mutlaka değiştirin
- **Örnek**: `VITE_ADMIN_PASSWORD=MySecurePassword123!`

### 🗺️ Harita Ayarları

#### `VITE_MAP_CENTER_LAT`
- **Açıklama**: Harita merkez enlem koordinatı
- **Varsayılan**: `37.0662` (Gaziantep Şehitkamil)
- **Format**: Decimal derece
- **Örnek**: `VITE_MAP_CENTER_LAT=37.0662`

#### `VITE_MAP_CENTER_LNG`
- **Açıklama**: Harita merkez boylam koordinatı  
- **Varsayılan**: `37.3833` (Gaziantep Şehitkamil)
- **Format**: Decimal derece
- **Örnek**: `VITE_MAP_CENTER_LNG=37.3833`

#### `VITE_MAP_DEFAULT_ZOOM`
- **Açıklama**: Harita varsayılan zoom seviyesi
- **Varsayılan**: `13`
- **Aralık**: 1-20 (1: dünya görünümü, 20: sokak detayı)
- **Örnek**: `VITE_MAP_DEFAULT_ZOOM=15`

#### `VITE_MAP_MIN_ZOOM`
- **Açıklama**: Minimum zoom seviyesi (ne kadar uzaklaşılabilir)
- **Varsayılan**: `10`
- **Aralık**: 1-20
- **Örnek**: `VITE_MAP_MIN_ZOOM=8`

#### `VITE_MAP_MAX_ZOOM`
- **Açıklama**: Maksimum zoom seviyesi (ne kadar yaklaşılabilir)
- **Varsayılan**: `18`
- **Aralık**: 1-20
- **Örnek**: `VITE_MAP_MAX_ZOOM=20`

#### `VITE_ENABLE_LOCATION_SELECTION`
- **Açıklama**: Harita üzerinde lokasyon seçimi özelliği
- **Varsayılan**: `true`
- **Değerler**: `true` / `false`
- **İşlev**: Admin panelinde haritaya tıklayarak yeni dijiboard ekleme
- **Örnek**: `VITE_ENABLE_LOCATION_SELECTION=false`

## 🔧 Farklı Şehirler İçin Konfigürasyon

### İstanbul
```env
VITE_MAP_CENTER_LAT=41.0082
VITE_MAP_CENTER_LNG=28.9784
VITE_MAP_DEFAULT_ZOOM=12
```

### Ankara
```env
VITE_MAP_CENTER_LAT=39.9334
VITE_MAP_CENTER_LNG=32.8597
VITE_MAP_DEFAULT_ZOOM=12
```

### İzmir
```env
VITE_MAP_CENTER_LAT=38.4192
VITE_MAP_CENTER_LNG=27.1287
VITE_MAP_DEFAULT_ZOOM=12
```

### Antalya
```env
VITE_MAP_CENTER_LAT=36.8969
VITE_MAP_CENTER_LNG=30.7133
VITE_MAP_DEFAULT_ZOOM=13
```

## 🌐 Deployment Konfigürasyonları

### Vercel (Otomatik)
```json
// vercel.json içinde tanımlı
{
  "env": {
    "VITE_WHATSAPP_NUMBER": "+905442906327",
    "VITE_ADMIN_PASSWORD": "admin123",
    "VITE_MAP_CENTER_LAT": "37.0662",
    "VITE_MAP_CENTER_LNG": "37.3833",
    "VITE_MAP_DEFAULT_ZOOM": "13",
    "VITE_MAP_MIN_ZOOM": "10", 
    "VITE_MAP_MAX_ZOOM": "18",
    "VITE_ENABLE_LOCATION_SELECTION": "true"
  }
}
```

### Netlify
```bash
# Netlify dashboard > Site settings > Environment variables
VITE_WHATSAPP_NUMBER=+905442906327
VITE_ADMIN_PASSWORD=MySecurePassword123
VITE_MAP_CENTER_LAT=37.0662
VITE_MAP_CENTER_LNG=37.3833
VITE_MAP_DEFAULT_ZOOM=13
VITE_MAP_MIN_ZOOM=10
VITE_MAP_MAX_ZOOM=18
VITE_ENABLE_LOCATION_SELECTION=true
```

### Local Development (.env)
```bash
# .env dosyası oluşturun (saitamanot klasörü içinde)
VITE_WHATSAPP_NUMBER=+905442906327
VITE_ADMIN_PASSWORD=admin123
VITE_MAP_CENTER_LAT=37.0662
VITE_MAP_CENTER_LNG=37.3833
VITE_MAP_DEFAULT_ZOOM=13
VITE_MAP_MIN_ZOOM=10
VITE_MAP_MAX_ZOOM=18
VITE_ENABLE_LOCATION_SELECTION=true
```

## 🛠️ Özellik Kontrolleri

### Location Selection Devre Dışı Bırakma
```env
VITE_ENABLE_LOCATION_SELECTION=false
```
- Admin panelinde harita tıklama devre dışı kalır
- Sadece manuel koordinat girişi ile dijiboard eklenir

### Zoom Kısıtlamaları
```env
VITE_MAP_MIN_ZOOM=12
VITE_MAP_MAX_ZOOM=16
```
- Kullanıcılar belirli zoom aralığında sınırlı kalır
- Şehir odaklı görünüm için ideal

### WhatsApp Entegrasyonu Değiştirme
```env
VITE_WHATSAPP_NUMBER=+905551234567
```
- Müşteri iletişimi için farklı numara kullanılabilir
- Format: +90 ile başlamalı

## 🔍 Koordinat Bulma Araçları

### Online Araçlar
- [LatLong.net](https://www.latlong.net/)
- [GPS Coordinates](https://gps-coordinates.org/)
- [Google Maps](https://maps.google.com) (sağ tık > koordinatlar)

### Manuel Koordinat Belirleme
1. Google Maps'te istediğiniz bölgeyi bulun
2. Sağ tıklayın ve koordinatları kopyalayın
3. Değerleri `VITE_MAP_CENTER_LAT` ve `VITE_MAP_CENTER_LNG`'ye yazın

## ⚠️ Güvenlik Uyarıları

### Production Ortamı
- **Admin şifresini mutlaka değiştirin**
- **WhatsApp numarasını doğrulayın**
- **Koordinatları test edin**

### Environment Variable Güvenliği
- `VITE_` prefix'li değişkenler client-side'da görünür
- Gerçek secret'ları environment variable olarak kullanmayın
- Admin şifresi sadece demo amaçlı, gerçek auth sistemi kullanın

## 🧪 Test Konfigürasyonları

### Development
```env
VITE_ADMIN_PASSWORD=dev123
VITE_MAP_DEFAULT_ZOOM=15
VITE_ENABLE_LOCATION_SELECTION=true
```

### Staging
```env  
VITE_ADMIN_PASSWORD=staging456
VITE_MAP_DEFAULT_ZOOM=13
VITE_ENABLE_LOCATION_SELECTION=false
```

### Production
```env
VITE_ADMIN_PASSWORD=SecureProductionPassword789!
VITE_MAP_DEFAULT_ZOOM=13
VITE_ENABLE_LOCATION_SELECTION=true
``` 