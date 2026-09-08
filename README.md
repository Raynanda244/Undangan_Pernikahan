# Undangan Pernikahan — Ray & Dinah

Website undangan pernikahan satu halaman (semua HTML, CSS, dan JavaScript
digabung dalam satu file `index.html` supaya gampang di-upload).

## 1. Cara upload ke GitHub Pages (gratis)

1. Buat akun GitHub kalau belum punya: https://github.com/join
2. Klik **New repository**. Beri nama bebas, misalnya `undangan-ray-dinah`.
   Pilih **Public**, lalu klik **Create repository**.
3. Di halaman repo, klik **Add file → Upload files**.
4. Upload file `index.html` (dan folder `assets` kalau ada foto/musik).
5. Klik **Commit changes**.
6. Masuk ke **Settings → Pages** (menu di sebelah kiri).
7. Di bagian **Branch**, pilih `main` dan folder `/ (root)`, lalu **Save**.
8. Tunggu 1–2 menit. Link undangan akan muncul di bagian atas halaman,
   formatnya seperti:
   `https://namakamu.github.io/undangan-ray-dinah/`
9. Itulah link yang bisa dibagikan ke tamu, bisa dibuka dari HP maupun
   komputer.

## 2. Yang perlu diedit sebelum dibagikan

Buka `index.html` dengan text editor (Notepad, VS Code, atau langsung edit
di GitHub dengan tombol pensil ✏️).

- **Foto** — cari tulisan `placehold.co` (ada beberapa), ganti dengan link
  foto asli kalian. Cara termudah: buat folder `assets/` di repo, upload
  foto ke sana, lalu ganti `src="https://placehold.co/..."` menjadi
  `src="assets/nama-file-foto.jpg"`.
- **Nama orang tua** — cari `(Nama Ayah)` dan `(Nama Ibu)`.
- **Alamat & nama gedung** — cari `Gedung Serbaguna (nama venue)` dan
  `Jl. Contoh Alamat No. 10, Depok, Jawa Barat`.
- **Jam & tanggal acara** — cari bagian `Akad Nikah` dan `Resepsi` untuk
  ubah jam tampilan, dan cari `EVENT_DATE_ISO` di bagian `<script>` untuk
  mengubah tanggal yang dipakai hitung mundur (format:
  `"2030-03-30T08:00:00+07:00"`).
- **Peta lokasi** — cari `google.com/maps?q=Depok` dan ganti kata
  `Depok,Jawa+Barat` dengan alamat lengkap venue kalian, atau tempel link
  "embed" dari Google Maps (Bagikan → Sematkan peta).

## 3. RSVP / Buku Tamu

Secara default, ucapan tamu disimpan di `localStorage` browser
masing-masing pengunjung — cocok untuk uji coba, tapi antar tamu **tidak**
saling melihat ucapan satu sama lain (karena situs ini statis, tanpa
server/database).

Supaya semua tamu bisa mengirim & melihat ucapan yang sama, sambungkan ke
layanan gratis **Formspree**:

1. Daftar di https://formspree.io (gratis untuk pemakaian dasar).
2. Buat form baru, salin endpoint-nya (contoh: `https://formspree.io/f/xxxxxxx`).
3. Di `index.html`, cari baris:
   ```js
   var FORM_ENDPOINT = "";
   ```
   Ganti jadi:
   ```js
   var FORM_ENDPOINT = "https://formspree.io/f/xxxxxxx";
   ```
4. Setiap ada tamu isi RSVP, kalian akan menerima notifikasi email/dashboard
   dari Formspree.

*(Menampilkan ucapan tamu secara real-time ke semua pengunjung butuh
penyimpanan terpusat, misalnya Google Sheet + Apps Script, atau layanan
seperti Supabase/Firebase — kalau mau, bisa saya bantu buatkan versi
lanjutannya.)*

## 4. Tentang proteksi klik kanan / copy

Situs ini menonaktifkan klik kanan, seleksi teks, dan beberapa shortcut
umum (F12, Ctrl+Shift+I, Ctrl+U, dll) untuk mencegah orang iseng.

**Penting untuk dipahami:** ini hanya penghalang ringan, bukan keamanan
sungguhan. Kode sumber sebuah halaman web pada dasarnya selalu bisa
dilihat siapa pun yang cukup niat (lewat cara lain di luar tombol
klik-kanan/shortcut biasa) — ini berlaku untuk semua website statis, bukan
cuma undangan ini. Jangan taruh data pribadi yang sensitif (nomor
rekening asli, dsb.) langsung di halaman ini kalau tidak perlu; kalau mau
menyertakan info rekening untuk amplop digital, sebaiknya hanya
ditampilkan sebagai gambar/teks biasa, bukan sebagai "rahasia" — anggap
saja siapa pun berpotensi melihatnya.

## 5. Coba dulu di komputer sendiri

Tinggal buka file `index.html` dengan cara diklik dua kali — akan terbuka
di browser tanpa perlu internet (kecuali untuk font & peta).
