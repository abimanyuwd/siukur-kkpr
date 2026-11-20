# SIUKUR-KKPR Web Wrapper (GitHub & Vercel)

Tautan pembungkus modern (*web wrapper*) untuk Web App Google Apps Script **SIUKUR-KKPR** (Sistem Informasi Pengukuran & Kesesuaian Kegiatan Pemanfaatan Ruang).

---

## 🌟 Fitur Utama Wrapper
- **Layar Penuh Responsif (100dvh):** Menyesuaikan otomatis dengan layar HP (Android & iPhone) tanpa terpotong bilah alamat browser.
- **Izin Sensor Aktif:** Dilengkapi izin kamera dan penanda lokasi GPS (`geolocation; camera`) agar formulir pengukuran dapat bekerja optimal.
- **Splash Screen Elegan:** Menampilkan layar loading berkelas saat Web App sedang memuat.
- **Tombol Darurat (Fallback):** Tersedia tombol pembuka otomatis jika pengguna mengalami kendala koneksi.

---

## 🚀 Panduan Deploy ke Vercel (Gratis & Cepat)

### Langkah 1: Upload Projek ke GitHub
1. Buka [GitHub.com](https://github.com) dan buat repositori baru (misal: `siukur-kkpr`).
2. Masukkan semua berkas dari folder ini (`index.html`, `vercel.json`, `README.md`) ke repositori GitHub Anda.
   *(Bisa menggunakan Git CLI, aplikasi GitHub Desktop, atau langsung upload berkas di website GitHub).*

### Langkah 2: Hubungkan ke Vercel
1. Buka [Vercel.com](https://vercel.com) dan login menggunakan akun GitHub Anda.
2. Klik tombol **"Add New..."** lalu pilih **"Project"**.
3. Cari repositori **`siukur-kkpr`** yang baru Anda buat, lalu klik **"Import"**.
4. Pada bagian pengaturan proyek, biarkan semua pengaturan default (Framework Preset: *Other*).
5. Klik **"Deploy"**.
6. Dalam hitungan detik, Anda akan mendapatkan URL kustom gratis yang rapi dan aman, misalnya:
   `https://siukur-kkpr.vercel.app`

---

## ⚠️ Pengaturan Wajib di Google Apps Script (`code.gs`)
Agar Google mengizinkan aplikasinya disematkan di dalam iframe Vercel / GitHub Pages tanpa kendala *"Refused to connect"*, pastikan kode backend `doGet()` di editor Google Apps Script Anda memiliki baris `.setXFrameOptionsMode(HtmlService.XFrameOptionsMode.ALLOWALL)`:

```javascript
function doGet() {
  return HtmlService.createHtmlOutputFromFile('index') // atau nama file antarmuka Anda
    .setXFrameOptionsMode(HtmlService.XFrameOptionsMode.ALLOWALL)
    .setTitle('SIUKUR-KKPR');
}
```

> **Catatan Penting:** Setelah memperbarui kode di atas pada editor Google Apps Script, pastikan klik **Terapkan (Deploy)** > **Kelola Penerapan (Manage Deployments)** > Edit ke **Versi Baru (New Version)** agar perubahannya aktif secara publik.
