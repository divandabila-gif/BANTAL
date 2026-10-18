# Panduan Memasang Aplikasi Cek BANTAL

Paket ini berisi dua versi aplikasi dengan isi yang sama, yaitu pengingat obat berbasis waktu salat, kuesioner Cek BANTAL, pusat peringatan berwarna, dan riwayat 14 hari.

| Versi | Folder | Alarm saat HP terkunci | Kebutuhan |
|---|---|---|---|
| APK Android (disarankan) | `android/` | Ya, memakai alarm sistem Android | Akun GitHub gratis, 10–15 menit sekali saja |
| Aplikasi web terpasang (PWA) | `web/` | Terbatas, hanya saat aplikasi terbuka | Hosting gratis (Netlify atau GitHub Pages) |

Seluruh langkah di bawah tidak memerlukan biaya.

## A. Membuat file APK Android lewat GitHub (gratis)

1. Buat akun di https://github.com, lalu klik **New repository**. Beri nama misalnya `cek-bantal`, pilih **Public**, lalu klik **Create repository**.
2. Di halaman repository yang masih kosong, klik **uploading an existing file**. Ekstrak file zip ini di komputer, lalu seret **seluruh isi** folder `cek-bantal-app` (folder `.github`, `android`, `web`, dan file ini) ke halaman tersebut, kemudian klik **Commit changes**.
   Catatan: folder `.github` tersembunyi di beberapa komputer. Di Windows, aktifkan *View → Hidden items*. Di Mac, tekan `Cmd + Shift + .`. Tanpa folder ini, APK tidak akan dibangun.
3. Buka tab **Actions**. Proses "Bangun APK Cek BANTAL" akan berjalan otomatis selama sekitar 5–8 menit. Jika diminta, klik **I understand my workflows, go ahead and enable them**, lalu pilih alur tersebut dan klik **Run workflow**.
4. Setelah muncul tanda centang hijau, klik nama proses tersebut. Di bagian **Artifacts**, unduh **CekBANTAL-APK**. Hasilnya berupa file zip berisi `app-debug.apk`.
5. Kirim `app-debug.apk` ke HP pasien, misalnya lewat WhatsApp sebagai dokumen atau Google Drive. Ketuk file tersebut di HP, lalu izinkan **Instal dari sumber tidak dikenal** ketika diminta.
6. Saat aplikasi dibuka pertama kali, pilih **Izinkan** untuk notifikasi.

### Pengaturan HP agar alarm tidak dimatikan sistem

Banyak HP Android di Indonesia (Xiaomi, Oppo, Vivo, Realme, Samsung) mematikan alarm aplikasi untuk menghemat baterai. Lakukan langkah berikut sekali di HP pasien:

- **Pengaturan → Aplikasi → Cek BANTAL → Notifikasi:** pastikan semua aktif.
- **Baterai / Penghemat daya:** pilih **Tidak dibatasi** atau **Tanpa pembatasan**.
- **Mulai otomatis (Autostart):** aktifkan. Opsi ini umumnya ada di Xiaomi, Oppo, dan Vivo.
- Setelah itu, buka **Alarm & Atur → Tes alarm obat** untuk memastikan alarm berbunyi.

## B. Versi aplikasi web terpasang (alternatif)

1. Buka https://app.netlify.com/drop dan daftar gratis.
2. Seret folder `web` ke halaman tersebut. Netlify akan memberikan alamat seperti `https://nama-acak.netlify.app`.
3. Buka alamat tersebut di Chrome pada HP pasien. Ketuk menu **⋮** lalu pilih **Tambahkan ke layar utama** atau **Instal aplikasi**.
4. Ikon Cek BANTAL akan muncul seperti aplikasi biasa dan tetap bisa dibuka tanpa internet.

## Catatan penting

- Data pasien hanya tersimpan di HP pasien sendiri dan tidak dikirim ke server mana pun. Data akan hilang jika aplikasi dihapus.
- Daftar obat bawaan hanya contoh. Ganti sesuai resep lewat menu **Alarm & Atur** sebelum diserahkan ke pasien.
- APK ini adalah versi uji (debug). APK ini aman untuk dipasang langsung, tetapi belum bisa diunggah ke Play Store. Untuk Play Store diperlukan akun pengembang Google dengan biaya pendaftaran satu kali.
- Ambang hijau, kuning, dan merah adalah alat bantu skrining, bukan alat diagnosis. Sebaiknya ditinjau dokter pembimbing sebelum dipakai ke pasien.
- Untuk mengubah isi aplikasi, cukup ubah `web/index.html` di GitHub. APK baru akan dibangun otomatis.
