# Panduan Kompilasi & Pembuatan File APK PT.SJI Slip Gaji

Folder ini (`sji/apk/`) berisi seluruh source code resmi proyek **Android Studio WebView App** untuk sistem **PT.SJI Industrial Payroll**.

---

## 📱 Spesifikasi Aplikasi Android
- **Nama Aplikasi**: PT.SJI Slip Gaji
- **Package Name**: `com.ptsji.payroll`
- **Min SDK**: Android 7.0 (API 24) - Kompatibel dengan 99%+ perangkat Android yang beredar
- **Target SDK**: Android 14 (API 34)
- **Fitur Utama Android**:
  - **Full Web App Wrapper**: Tampilan native responsif penuh layar tanpa bilah alamat browser.
  - **Cleartext HTTP Permitted**: Mendukung akses ke IP lokal server (contoh: `http://192.168.1.16/sji/`) maupun domain HTTPS online.
  - **File Upload Support (`onShowFileChooser`)**: HRD atau karyawan dapat mengunggah file Excel, dokumen, atau gambar profil langsung dari galeri/pengelola file HP.
  - **Download Manager**: Mengunduh berkas template `.xlsx`, `.csv`, dan bukti cetak slip gaji langsung ke folder `Downloads` di HP Android dengan notifikasi unduhan.
  - **Pull-To-Refresh**: Tarik layar ke bawah untuk memuat ulang data slip gaji terbaru.
  - **Smart Back Button**: Menekan tombol kembali di HP akan menavigasikan riwayat halaman web, dan menekan 2 kali berturut-turut untuk keluar.
  - **Offline/Error Screen**: Tampilan industrial elegan jika HP kehilangan koneksi Wi-Fi/data ke server.

---

## 🛠️ Cara Membangun (Build) File `.apk` Menggunakan Android Studio

1. **Buka Android Studio**:
   - Jika belum memiliki Android Studio, Anda dapat mengunduhnya secara gratis di [developer.android.com/studio](https://developer.android.com/studio).
2. **Buka Proyek**:
   - Pilih menu **File > Open...**
   - Arahkan ke folder: `c:\Users\qrsre\.gemini\antigravity\scratch\sji\apk`
   - Klik **OK** dan tunggu proses sinkronisasi Gradle (Sync) selesai.
3. **Mengubah URL Server (Jika Diperlukan)**:
   - Buka file: `app/src/main/res/values/strings.xml`
   - Ubah nilai `server_url` sesuai IP Wi-Fi komputer Anda atau domain hosting website Anda:
     ```xml
     <!-- Contoh jika menggunakan IP Wi-Fi lokal komputer Anda saat ini -->
     <string name="server_url">http://192.168.1.16/sji/</string>

     <!-- Atau jika website sudah di-online-kan di hosting/domain -->
     <!-- <string name="server_url">https://payroll.ptsji.com/</string> -->
     ```
4. **Generate File APK**:
   - Di menu atas Android Studio, klik:  
     **Build > Build Bundle(s) / APK(s) > Build APK(s)**
   - Tunggu sekitar 1–2 menit hingga muncul notifikasi di pojok kanan bawah:  
     `APK(s) generated successfully for module 'app'`
   - Klik tulisan **locate** pada notifikasi tersebut. File `app-debug.apk` Anda sudah siap!
5. **Kirim & Pasang di HP Android**:
   - Kirim file `.apk` tersebut ke HP karyawan (via WhatsApp, kabel USB, Google Drive, atau dibagikan langsung).
   - Di HP Android, klik file APK tersebut untuk menginstal (*Izinkan instalasi dari sumber tidak dikenal jika diminta*).
   - Aplikasi **PT.SJI Slip Gaji** siap digunakan!

---

## 🌐 Catatan Penting Akses Jaringan Lokal (Wi-Fi)
- Saat menguji aplikasi menggunakan server lokal XAMPP (Apache):
  1. Pastikan Apache & MySQL di XAMPP Control Panel komputer Anda dalam status **Running**.
  2. Pastikan HP Android dan Komputer terhubung ke **jaringan Wi-Fi yang sama**.
  3. Pastikan firewall Windows mengizinkan Apache (port 80) diakses dari perangkat lain pada jaringan lokal.

