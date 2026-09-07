<p align="center">
  <img src="https://raw.githubusercontent.com/jadipetani/be-jadipetani/main/docs/logo-jadipetani.jpg" alt="Jadipetani Logo" width="120" />
</p>

<h1 align="center">🌾 Jadipetani</h1>

<p align="center">
  <strong>Platform Magang & Pekerjaan Pertanian Berbasis AI</strong><br/>
  Menjembatani petani/perusahaan agribisnis dengan pelajar/pemuda yang ingin berkarier di sektor pertanian Indonesia.
</p>

<p align="center">
  <a href="https://fe-jadipetani.vercel.app">🌐 Live Demo</a> •
  <a href="https://github.com/jadipetani/be-jadipetani">⚙️ Backend Repo</a> •
  <a href="https://github.com/jadipetani/fe-jadipetani">🎨 Frontend Repo</a>
</p>

---

## 📖 Tentang Jadipetani

Jadipetani adalah platform digital yang menghubungkan **petani/perusahaan agribisnis** dengan **pelajar/pemuda** melalui:

- **Program Magang Terstruktur** — Kurikulum mingguan yang di-generate AI (Gemini API)
- **AI Logbook** — Catatan refleksi mingguan dengan analisis & umpan balik otomatis dari AI
- **Sertifikat Digital** — Sertifikat kompetensi & transkrip nilai dalam format PDF
- **Job Connector** — Lowongan kerja profesional dengan pembayaran Placement Fee via Midtrans
- **Evaluasi Berbasis AI** — Ringkasan narasi kompetensi peserta magang secara otomatis

---

## 🏗️ Arsitektur & Tech Stack

| Layer | Teknologi |
|-------|-----------|
| **Frontend** | React 18, Vite 5, Tailwind CSS 3, Zustand, Axios, React Router v7 |
| **Backend** | Node.js 20+, Express.js 5, Prisma ORM 5, PostgreSQL (Supabase) |
| **AI** | Google Gemini API (`@google/generative-ai`) |
| **Storage** | Supabase Storage (CV, Portofolio, Logbook Docs, Sertifikat) |
| **Payment** | Midtrans Snap (Sandbox & Production) |
| **Email** | Resend API |
| **PDF** | PDFKit |
| **Deployment** | Frontend: Vercel — Backend: Railway |

---

## 🚀 Panduan Instalasi & Menjalankan Aplikasi

### Prasyarat

- **Node.js** ≥ 20.x (Backend) / ≥ 18.x (Frontend)
- **npm** ≥ 9.x
- **PostgreSQL** (disarankan via Supabase)
- **Git**

---

### 1. Backend (`be-jadipetani`)

```bash
# Clone repository
git clone https://github.com/jadipetani/be-jadipetani.git
cd be-jadipetani

# Install dependencies
npm install

# Salin dan isi environment variables
cp .env.example .env
# Edit .env sesuai konfigurasi (lihat tabel di bawah)

# Generate Prisma Client
npm run prisma:generate

# Jalankan migrasi database
npm run prisma:migrate

# Isi data demo (seeding)
npm run prisma:seed

# Jalankan server development
npm run dev
```

Server backend aktif di `http://localhost:5000`.

#### Environment Variables Backend

| Variable | Deskripsi | Wajib |
|----------|-----------|-------|
| `NODE_ENV` | `development` / `production` | ✅ |
| `PORT` | Port server (default: `5000`) | ✅ |
| `DATABASE_URL` | Connection string PostgreSQL (Transaction Pooler) | ✅ |
| `DIRECT_URL` | Connection string PostgreSQL (Session Pooler) | ✅ |
| `JWT_ACCESS_SECRET` | Secret key access token (min 32 chars) | ✅ |
| `JWT_REFRESH_SECRET` | Secret key refresh token (min 32 chars) | ✅ |
| `FRONTEND_URL` | URL frontend (untuk CORS & email links) | ✅ |
| `SUPABASE_URL` | URL proyek Supabase | ✅ |
| `SUPABASE_SERVICE_KEY` | Service role key Supabase | ✅ |
| `GEMINI_API_KEY` | API Key Google Gemini AI Studio | ✅ |
| `MIDTRANS_SERVER_KEY` | Server Key Midtrans | ✅ |
| `MIDTRANS_CLIENT_KEY` | Client Key Midtrans | ✅ |
| `MIDTRANS_IS_PRODUCTION` | `false` = Sandbox | ✅ |
| `RESEND_API_KEY` | API Key Resend Email Service | ✅ |

---

### 2. Frontend (`fe-jadipetani`)

```bash
# Clone repository
git clone https://github.com/jadipetani/fe-jadipetani.git
cd fe-jadipetani

# Install dependencies
npm install

# Salin dan isi environment variables
cp .env.example .env
# Edit .env sesuai konfigurasi

# Jalankan development server
npm run dev
```

Aplikasi frontend aktif di `http://localhost:5173`.

#### Environment Variables Frontend

| Variable | Deskripsi | Wajib |
|----------|-----------|-------|
| `VITE_API_BASE_URL` | URL Backend API (contoh: `http://localhost:5000/api`) | ✅ |
| `VITE_MIDTRANS_CLIENT_KEY` | Client Key Midtrans Snap | ✅ |
| `VITE_MIDTRANS_ENV` | `sandbox` atau `production` | ✅ |

> ⚠️ **JANGAN** memasukkan server key, JWT secret, atau secret backend apapun di environment frontend.

---

## 🧪 Spesifikasi Lingkungan Pengujian

| Komponen | Spesifikasi |
|----------|-------------|
| **OS** | Windows 11 / macOS 14+ / Ubuntu 22.04 |
| **Node.js** | v20.18.0 |
| **npm** | v10.8.2 |
| **Database** | PostgreSQL 15 (Supabase Connection Pooler) |
| **Browser** | Google Chrome 130+ / Firefox 131+ / Edge 130+ |
| **Backend URL (Dev)** | `http://localhost:5000/api` |
| **Frontend URL (Dev)** | `http://localhost:5173` |
| **Backend URL (Prod)** | `https://be-jadipetani-production.up.railway.app/api` |
| **Frontend URL (Prod)** | `https://fe-jadipetani.vercel.app` |
| **Midtrans** | Sandbox Mode |
| **Supabase** | Free Tier Project |

---

## 🔐 Akun Demo

Akun berikut tersedia setelah menjalankan `npm run prisma:seed` di backend:

| Role | Email | Password | Keterangan |
|------|-------|----------|------------|
| **Petani (FARMER)** | `petani@jadipetani.com` | `farmer123` | Pak Budi Sugiharto — Lembang, Bandung Barat |
| **Pelajar (STUDENT)** | `pelajar@jadipetani.com` | `student123` | Ahmad Rizky — IPB University |

---

## 📂 Struktur Repository

```
jadipetani/
├── .github/            ← README organisasi (file ini)
├── be-jadipetani/      ← Backend API (Express.js + Prisma + PostgreSQL)
└── fe-jadipetani/      ← Frontend App (React + Vite + Tailwind CSS)
```

---

## 🔒 Keamanan

- **Password**: Hashing `bcrypt` dengan 12 salt rounds
- **Autentikasi**: JWT Access Token (1 jam) + Refresh Token di httpOnly Cookie (30 hari)
- **Rate Limiting**: 10 req/15 menit (auth) — 100 req/15 menit (global API)
- **Payment**: Verifikasi SHA512 signature Midtrans + Idempotency check
- **Upload File**: Validasi MIME type, maks 5MB, penamaan UUID v4, penyimpanan privat Supabase Storage

---

## 📄 Lisensi

Proyek ini dikembangkan untuk keperluan akademik.