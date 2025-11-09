# PlastiKo Management System (PKMS)

Sistem Manajemen Bioplastik PlastiKo adalah aplikasi web full-stack yang dirancang untuk mengelola produk bioplastik ramah lingkungan dengan fitur pelacakan QR Code dan dashboard admin yang komprehensif.

## 🌟 Fitur Utama

### Tampilan Publik
- **Desain Modern & Responsif**: Tema hijau muda dan putih yang mencerminkan keberlanjutan
- **Animasi Interaktif**: Perubahan warna kemasan untuk menunjukkan proses dekomposisi
- **QR Code Scanner**: Integrasi scanner untuk melacak produk dan informasi komposting
- **Product Showcase**: Tampilan produk dengan kartu yang menarik dan informatif
- **Responsive Design**: Optimal di desktop, tablet, dan mobile

### Dashboard Admin
- **Navigasi Samping Compact**: Sidebar yang efisien dengan menu terorganisir
- **Manajemen Produk**: CRUD operations untuk produk bioplastik
- **Manajemen Pengguna**: Kelola data pelanggan dan aktivitas mereka
- **QR Scan Tracking**: Pantai aktivitas pemindaian QR Code
- **Analitik Real-time**: Statistik produk populer dan lokasi scan
- **Pengaturan Sistem**: Konfigurasi aplikasi

### Sistem Pelacakan
- **QR Code Integration**: Setiap produk memiliki QR Code unik
- **Informasi Detail**: Material, panduan komposting, transparansi bahan
- **Lokasi Tracking**: Pemantauan lokasi pemindaian produk
- **Data Analytics**: Visualisasi data scan dan penggunaan produk

## 🛠 Teknologi yang Digunakan

### Frontend
- **Next.js 15** dengan App Router
- **TypeScript 5** untuk type safety
- **Tailwind CSS 4** untuk styling
- **shadcn/ui** untuk komponen UI
- **Framer Motion** untuk animasi
- **Lucide Icons** untuk ikon

### Backend
- **Node.js** dengan Next.js API Routes
- **Prisma ORM** untuk database management
- **SQLite** untuk database (development)
- **Nodemailer** untuk email notifications
- **QR Scanner** library untuk QR Code functionality

### Database Schema
```sql
Products (ID, Nama Produk, Deskripsi, Harga, Bahan Utama, Keunggulan)
Users (ID, Nama, Email, Telepon, Alamat)
QR_Scans (ID, ID Produk, Tanggal Pemindaian, Lokasi QR Code, Data yang Dipandai)
```

## 📱 Fitur Animasi Warna

Sistem menampilkan animasi perubahan warna kemasan:
1. **Hijau Terang** (0-1 bulan): Produk baru
2. **Hijau Muda** (1-2 bulan): Dekomposisi awal
3. **Kuning** (2-3 bulan): Dekomposisi aktif
4. **Oranye** (3-4 bulan): Dekomposisi lanjutan
5. **Coklat Tua** (4-6 bulan): Sepenuhnya terurai

## 📧 Email Notifications

Sistem mengirimkan notifikasi email otomatis:
- **Welcome Email**: Untuk pengguna baru
- **QR Scan Notification**: Konfirmasi pemindaian produk
- **Admin Notifications**: Alert untuk aktivitas penting

## 🚀 Instalasi & Setup

### Prerequisites
- Node.js 18+
- npm atau yarn

### Installation
```bash
# Clone repository
git clone <repository-url>
cd plastiko-management-system

# Install dependencies
npm install

# Setup database
npm run db:push

# Seed database dengan sample data
npx tsx prisma/seed.ts

# Jalankan development server
npm run dev
```

### Environment Variables
Buat file `.env` dengan konfigurasi berikut:
```env
# Database
DATABASE_URL="file:./dev.db"

# Email Configuration
SMTP_HOST="smtp.gmail.com"
SMTP_PORT="587"
SMTP_USER="your-email@gmail.com"
SMTP_PASS="your-app-password"
SMTP_FROM="PlastiKo <noreply@plastiko.id>"
ADMIN_EMAIL="admin@plastiko.id"
```

## 📂 Struktur Proyek

```
src/
├── app/
│   ├── admin/                 # Dashboard Admin
│   ├── api/                   # API Routes
│   │   ├── products/         # Product CRUD
│   │   ├── users/            # User Management
│   │   ├── qr-scans/         # QR Scan Tracking
│   │   └── notifications/    # Email Notifications
│   └── page.tsx              # Halaman Utama
├── components/
│   ├── ui/                   # shadcn/ui Components
│   ├── QRScanner.tsx         # QR Scanner Component
│   └── ColorChangeAnimation.tsx # Color Animation
├── lib/
│   ├── db.ts                 # Database Connection
│   └── email.ts              # Email Service
└── prisma/
    ├── schema.prisma         # Database Schema
    └── seed.ts               # Sample Data
```

## 🔧 API Endpoints

### Products
- `GET /api/products` - Get all products
- `POST /api/products` - Create new product
- `PUT /api/products/[id]` - Update product
- `DELETE /api/products/[id]` - Delete product

### Users
- `GET /api/users` - Get all users
- `POST /api/users` - Create new user

### QR Scans
- `GET /api/qr-scans` - Get all QR scans
- `POST /api/qr-scans` - Create new QR scan

### Notifications
- `POST /api/notifications` - Send email notification

## 🎨 Design Guidelines

### Color Scheme
- **Primary**: Green-600 (#16a34a)
- **Secondary**: Green-50 (#f0fdf4)
- **Accent**: Green-100 (#dcfce7)
- **Text**: Green-800 (#166534)

### Typography
- **Headings**: Font-bold dengan ukuran responsif
- **Body**: Text-gray-600 untuk deskripsi
- **Buttons**: Konsisten dengan green theme

### Components
- **Cards**: Border radius halus dengan shadow
- **Buttons**: Hover states dan loading states
- **Forms**: Validasi dan error handling
- **Navigation**: Responsive dengan mobile menu

## 🌐 Browser Support

- Chrome/Chromium 90+
- Firefox 88+
- Safari 14+
- Edge 90+

## 📱 Responsive Breakpoints

- **Mobile**: < 768px
- **Tablet**: 768px - 1024px
- **Desktop**: > 1024px

## 🔒 Security Features

- Input validation pada semua forms
- SQL injection prevention dengan Prisma
- XSS protection dengan Next.js
- CORS configuration
- Rate limiting pada API endpoints

## 🚀 Performance Optimizations

- Code splitting dengan Next.js
- Image optimization
- Lazy loading untuk components
- Database indexing
- Caching strategy

## 📈 Monitoring & Analytics

- Error tracking dengan console logging
- Performance monitoring
- User behavior analytics
- QR scan tracking

## 🤝 Contributing

1. Fork repository
2. Create feature branch
3. Commit changes
4. Push to branch
5. Create Pull Request

## 📄 License

MIT License - see LICENSE file for details

## 📞 Support

Untuk bantuan atau pertanyaan:
- Email: support@plastiko.id
- Website: https://plastiko.id
- Documentation: https://docs.plastiko.id

---

**PlastiKo** - Solusi Bioplastik Berkelanjutan untuk Masa Depan yang Lebih Hijau 🌱
