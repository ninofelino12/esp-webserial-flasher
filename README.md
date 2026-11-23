# ESP Web Flasher

Aplikasi statis satu halaman untuk mengunggah satu berkas firmware `.bin` ke ESP32/ESP8266 melalui Web Serial dan `esptool-js`, lalu membaca output konsol serial firmware secara real-time.

## Menjalankan

Buka `index.html` melalui GitHub Pages (HTTPS) di browser Chromium yang mendukung Web Serial, seperti Chrome atau Edge desktop. Pilih firmware `.bin`, tentukan alamat flash sesuai instruksi firmware, pilih baud rate, lalu tekan **Pilih port & flash** dan pilih port board. Jika board tidak tersambung, coba baud 115200 dan tahan tombol BOOT saat proses reset/koneksi.

Halaman ini tidak mengunggah firmware ke server. Peramban akan meminta akses serial melalui dialog izin. Jangan tutup tab atau cabut board selama proses penulisan. Setelah flash berhasil, port dibuka kembali otomatis untuk membaca log konsol pada baud rate yang dipilih. Gunakan tombol **Berhenti** untuk menutup pembacaan serial; tombol **Mulai pantau serial** dapat digunakan kembali selama port board sudah dipilih.

## Penting

Alamat `0x10000` adalah nilai awal umum untuk image aplikasi ESP32, tetapi bukan alamat universal. ESP8266, bootloader, tabel partisi, dan image gabungan dapat memerlukan alamat yang berbeda. Ikuti petunjuk pembuat firmware. Opsi hapus seluruh flash tidak aktif secara default; mengaktifkannya akan menghapus konfigurasi dan filesystem di perangkat.

Web Serial membutuhkan secure context dan dukungan browser. Dukungan pada ponsel/tablet berbeda-beda; gunakan komputer Chrome/Edge jika pemilih port tidak tersedia.

## GitHub Pages

Repo disajikan dari root branch `main`. Aktifkan Pages melalui **Settings → Pages → Deploy from a branch → main → /(root)** jika belum aktif.

Library flasher dimuat dari CDN `esm.sh` pada versi `esptool-js` 0.7.1. Koneksi internet diperlukan saat membuka halaman pertama kali.
