# SIUKUR-KKPR Web Wrapper (GitHub & Vercel)

Tautan pembungkus resmi (*web wrapper*) untuk Web App Google Apps Script **SIUKUR-KKPR** (Sistem Informasi Uji Kesesuaian dan Pengukuran Ruang).

---

## 🌟 Fitur Utama Wrapper
- **Identitas & Logo Resmi:** Menampilkan logo resmi SIUKUR-KKPR (peta Indonesia, theodolite, tata ruang hijau, pin lokasi) pada Splash Screen dan Favicon tab browser.
- **Layar Penuh Responsif (100dvh):** Menyesuaikan otomatis dengan layar HP (Android & iPhone) tanpa terpotong bilah alamat browser.
- **Izin Sensor Aktif:** Dilengkapi izin kamera dan penanda lokasi GPS (`geolocation; camera`) agar formulir survei/pengukuran dapat bekerja optimal.
- **Splash Screen Elegan:** Menampilkan layar loading berkelas dengan nuansa Slate/Navy yang adem saat Web App sedang memuat.
- **Tombol Darurat (Fallback):** Tersedia tombol pembuka otomatis jika pengguna mengalami kendala koneksi internet.

---

## 📁 Struktur Berkas Repositori
Pastikan berkas-berkas berikut ada di dalam folder proyek Anda sebelum di-push ke GitHub:
1. `index.html` : Halaman pembungkus utama aplikasi.
2. `logo.png` (atau `logo.jpg`): Berkas gambar logo resmi SIUKUR-KKPR.
3. `vercel.json` : Konfigurasi rute statis & security headers Vercel.
4. `README.md` : Petunjuk dokumentasi proyek ini.

---

## 🚀 Panduan Update ke GitHub & Vercel

1. Simpan gambar logo resmi ke dalam folder ini dengan nama **`logo.png`** (atau `logo.jpg`).
2. Masukkan / commit pembaruan berkas (`index.html`, `logo.png`, `README.md`) ke repositori GitHub Anda.
3. Vercel akan secara otomatis mendeteksi perubahan tersebut dan melakukan **Redeploy** dalam hitungan detik!
4. Buka kembali tautan Vercel Anda (misal: `https://siukur-kkpr.vercel.app`), logo dan nama resmi baru sudah langsung aktif!

---

## ⚠️ Pengaturan Wajib di Google Apps Script (`code.gs`)
Pastikan fungsi `doGet()` di Google Apps Script Anda memuat baris:

```javascript
function doGet() {
  return HtmlService.createHtmlOutputFromFile('index')
    .setXFrameOptionsMode(HtmlService.XFrameOptionsMode.ALLOWALL)
    .setTitle('SIUKUR-KKPR');
}
```
*(Setelah itu klik Deploy > Manage Deployments > Edit ke Versi Baru).*
