# QR Inspection System — Mobile Inspector

Aplikasi web mobile untuk petugas inspeksi. Dibuat sebagai aplikasi terpisah dari Admin Dashboard.

## Fitur tahap awal
- Login Supabase Auth.
- Membaca keanggotaan dan organisasi aktif.
- Membuka aset dari QR Token melalui URL `?token=<uuid>`.
- Scan QR dengan kamera (memerlukan HTTPS dan izin kamera), atau input token manual.
- Memuat template checklist aktif berdasarkan `asset_type` aset.
- Mengisi hasil item: OK / NG / NA dan catatan.
- Menyimpan header inspeksi, jawaban, lalu mengubah status menjadi `submitted`.

## Konfigurasi
Project URL dan Publishable Key Supabase sudah diisi pada `index.html`.
Jangan pernah memasukkan `service_role` atau secret key ke frontend.

## Deploy GitHub Pages
1. Buat repository GitHub baru bernama `qr-inspection-mobile`.
2. Upload `index.html` dan `README.md` ke root branch `main`.
3. Buka Settings → Pages.
4. Pilih Deploy from a branch → `main` → `/ (root)`.
5. Setelah deploy, URL yang diharapkan:
   `https://ekoardiyanto1999.github.io/qr-inspection-mobile/`

## Penting sebelum dipakai
- Akun petugas harus sudah terdaftar di Supabase Auth dan menjadi anggota aktif di `elodie_inspection_members`.
- Admin/Supervisor harus membuat template checklist aktif dan item checklist untuk setiap `asset_type`.
- Tahap ini belum membuat temuan (findings) otomatis untuk jawaban NG, belum mengunggah foto bukti, dan belum mengimplementasikan review Supervisor.
- Uji dahulu dengan akun Inspector dan satu aset uji. RLS tetap menjadi pengaman utama.
