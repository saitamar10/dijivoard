# Saitama Notion Blog

Modern, minimalist ve Notion API entegrasyonlu kişisel blog sistemi. Saitama temasıyla tasarlanmış, güçlü ve basit bir blog platformu.

## 🚀 Özellikler

- **Notion API Entegrasyonu**: Notion veritabanlarından dinamik içerik çekme
- **Page ID Tabanlı**: Sadece environment variables ile kolay kurulum
- **Modern UI**: Shadcn/ui bileşenleri ile profesyonel tasarım
- **Responsive**: Mobil ve masaüstü uyumlu
- **Vercel Optimized**: u.map sorunu çözülmüş, hızlı deployment
- **TypeScript**: Tip güvenli kod yapısı
- **Tailwind CSS**: Utility-first CSS framework

## 🛠️ Teknolojiler

- **Frontend**: React 18, TypeScript, Vite
- **UI**: Shadcn/ui, Tailwind CSS, Lucide Icons
- **Backend**: Notion API
- **Deployment**: Vercel
- **Routing**: React Router DOM

## 📦 Kurulum

### 1. Projeyi Klonlayın

```bash
git clone <repository-url>
cd saitama-notion-tales
```

### 2. Bağımlılıkları Yükleyin

```bash
npm install
```

### 3. Environment Variables

`.env` dosyasını oluşturun:

```env
NOTION_TOKEN="secret_xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
NOTION_DATABASE_ID="xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
```

### 4. Geliştirme Sunucusunu Başlatın

```bash
npm run dev
```

## 🚀 Deployment

Detaylı deployment rehberi için [DEPLOYMENT_GUIDE.md](./DEPLOYMENT_GUIDE.md) dosyasını inceleyin.

### Hızlı Vercel Deployment

1. GitHub'a push edin
2. Vercel'e import edin
3. Environment variables ekleyin
4. Deploy edin!

## 📁 Proje Yapısı

```
src/
├── components/          # React bileşenleri
│   ├── ui/             # Shadcn/ui bileşenleri
│   ├── Layout.tsx      # Ana layout
│   └── WeeklyNewsletter.tsx
├── pages/              # Sayfa bileşenleri
│   ├── Index.tsx       # Ana sayfa
│   ├── Blog.tsx        # Blog listesi
│   ├── BlogPost.tsx    # Blog yazısı
│   └── ...
├── lib/                # Utility fonksiyonlar
│   ├── notion.ts       # Notion API entegrasyonu
│   └── utils.ts        # Yardımcı fonksiyonlar
└── assets/             # Statik dosyalar
```

## 🎨 Özelleştirme

### Tema Renkleri

`tailwind.config.ts` dosyasından renkleri özelleştirebilirsiniz.

### Site Ayarları

`src/lib/notion.ts` dosyasındaki `SITE_CONFIG` objesini düzenleyin:

```typescript
export const SITE_CONFIG = {
  name: "Saitama Kişisel Blog",
  description: "Bu sitede kişisel blog yazıları ve haberler bulunur",
  logo: "logo-url",
  databaseId: "database-id"
};
```

## 📊 Notion Database Yapısı

### Ana Blog Database

| Property | Type | Açıklama |
|----------|------|----------|
| Title | Title | Yazı başlığı |
| Summary | Rich Text | Yazı özeti |
| Content | Rich Text | Yazı içeriği |
| Date | Date | Yayın tarihi |
| Type | Select | Post, CV, Kitap, Proje |
| Category | Select | Kategori |
| Tags | Multi-select | Etiketler |
| Status | Status | Draft, Published |
| Slug | Rich Text | URL slug |
| Icon | Files & media | Yazı ikonu |

## 🔧 Geliştirme

### Komutlar

```bash
npm run dev          # Geliştirme sunucusu
npm run build        # Production build
npm run preview      # Build önizleme
npm run lint         # ESLint kontrolü
```

### Yeni Sayfa Ekleme

1. `src/pages/` dizininde yeni component oluşturun
2. `src/App.tsx` dosyasına route ekleyin
3. Navigation menüsünü güncelleyin

## 🐛 Sorun Giderme

### Build Hataları

- `npm install` çalıştırın
- Node.js versiyonunu kontrol edin (18+)
- Environment variables'ı kontrol edin

### Notion API Hataları

- Token'ın doğru olduğundan emin olun
- Database'in integration'a bağlı olduğunu kontrol edin
- Database ID'sinin doğru olduğunu kontrol edin

## 📝 Lisans

MIT License

## 🤝 Katkıda Bulunma

1. Fork edin
2. Feature branch oluşturun (`git checkout -b feature/amazing-feature`)
3. Commit edin (`git commit -m 'Add amazing feature'`)
4. Push edin (`git push origin feature/amazing-feature`)
5. Pull Request oluşturun

## 📞 İletişim

Herhangi bir sorun veya öneriniz için issue oluşturun.

---

**"Ben sadece hobi olarak geliştirici yaptım. Ama zamanla bu hobi hayatımın merkezine oturdu. Tıpkı Saitama'nın gücü gibi, kod yazmak da basit görünür - ama derinliği sonsuz."**

