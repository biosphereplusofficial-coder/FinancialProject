# LabERP — Dashboard Keuangan Proyek

Dashboard keuangan proyek berbasis web yang fetch data langsung dari Google Sheets.

## 🔗 Live Dashboard
> Akan aktif di: `https://biosphereplusofficial-coder.github.io/FinancialProject/`

## 📊 Data Source
Google Sheets: [LabERP Spreadsheet](https://docs.google.com/spreadsheets/d/1zxSk7IMrsak7yViHrbexFG1VAKmRO0Ezm0aGzNq3wTg)

## ✨ Fitur
- **Revenue** — Total termin yang sudah lunas (dengan filter tahun)
- **Potensi Revenue** — Total nilai kontrak semua proyek
- **Profit Aktual** — Revenue dikurangi realisasi biaya
- **Potensi Profit** — Nilai kontrak dikurangi total anggaran
- Monitoring pinjaman investor & sisa hutang
- Status termin & retensi
- Transaksi terbaru & pending approval
- Saldo rekening per akun
- Filter per tahun & per proyek

## 🔄 Auto Update
Dashboard di-deploy ulang otomatis via GitHub Actions:
- Setiap push ke branch `main`
- Setiap 6 jam sekali (scheduled)
- Manual via tab Actions → Run workflow

## ⚙️ Setup Google Sheets (WAJIB)

Agar data live bisa diambil, spreadsheet harus di-set **public**:

1. Buka spreadsheet di Google Sheets
2. Klik **Share** → **Change to anyone with the link**
3. Set permission: **Viewer**
4. Klik **Done**

> Jika belum public, dashboard akan tampil menggunakan data demo.

## 🛠 Setup GitHub Pages

1. Buka repo → **Settings** → **Pages**
2. Source: **Deploy from a branch** → pilih `gh-pages` (atau **GitHub Actions**)
3. Kalau pakai workflow Actions: pilih **GitHub Actions** sebagai source

## 📁 Struktur File
```
├── index.html          # Dashboard utama
├── .github/
│   └── workflows/
│       └── deploy.yml  # Auto-deploy setiap 6 jam
└── README.md
```

## 🎨 Sheet yang Digunakan
| Sheet | GID | Konten |
|-------|-----|--------|
| Projects | 1978030258 | Master data proyek |
| Budget | 543642149 | RAB & realisasi anggaran |
| Transaksi | 1162847060 | Jurnal harian |
| Termin | 683807027 | Jadwal & status penagihan |
| Kontrak | 1359150712 | Detail kontrak & retensi |
| Pinjaman | 421562363 | Modal investor |
| ProfitSharing | 2010155024 | Distribusi laba |
| Akun | 1111734438 | Saldo rekening |

---
*LabERP v1.0 — Built with Chart.js & PapaParse*
