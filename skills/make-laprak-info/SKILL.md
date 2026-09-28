---
name: make-laprak-info
description: >-
  Gunakan skill ini jika pengguna mengetik command "/make-laprak-info" atau meminta informasi tentang apa itu plugin/skill make-laprak.
---

# INSTRUKSI: TAMPILKAN TEKS DI BAWAH INI APA ADANYA

Jika skill ini dipanggil, Anda **WAJIB menyalin dan menampilkan** teks di bawah garis ini **persis seperti yang tertulis**. Jangan memodifikasi, memparafrase, atau menambahkan kata-kata sendiri. Jangan memodifikasi file apapun. Langsung tampilkan:

---

# 📋 Plugin `/make-laprak` — Panduan Penggunaan

## 1. Apa itu `/make-laprak`?

Plugin AI (Antigravity Skill) yang membantu menyusun **Laporan Praktikum** tingkat Universitas dalam format **LaTeX**. AI bekerja secara iteratif — selangkah demi selangkah, selalu meminta persetujuan (ACC) Anda sebelum lanjut.

## 2. Fitur Utama

- 📖 Membaca `inisiasi.txt` dan mencocokkan dengan screenshot bernomor.
- ✍️ Menyusun Dasar Teori, Hasil & Pembahasan, Kesimpulan, dan Daftar Pustaka.
- 🔍 Sitasi nyata — AI wajib mencari referensi via internet, bukan mengarang.
- 🎨 Format LaTeX otomatis menyesuaikan aturan per mata kuliah (misal: KEPL).
- 📄 **Auto-generate file `.tex`** langsung ke folder kerja Anda di tahap akhir.

## 3. Cara Menggunakan

**Anda TIDAK PERLU** menaruh file di folder plugin. Plugin adalah "otak" di latar belakang.

**Langkah-langkah:**
1. Buat folder kerja **di mana saja** (misal: `D:\Tugas\KEPL\Pertemuan-4\`).
2. Di dalamnya, siapkan:
   - `inisiasi.txt` — Catatan penjelasan Anda tentang setiap screenshot.
   - Folder `gambar/` — Screenshot bernomor (`1.png`, `2.png`, dst).
   - (Opsional) Modul PDF atau PPT pertemuan.
3. Buka workspace di folder tersebut, lalu ketik:
   > `/make-laprak buatkan laporan KEPL, saya sudah siapkan inisiasi.txt dan folder gambar`

## 4. Alur Kerja (5 Tahap)

| Tahap | Apa yang AI Lakukan | Aksi Anda |
|-------|---------------------|-----------|
| **1 — Inisiasi** | Membaca referensi + `inisiasi.txt`, merangkum pemahaman | Cek rangkuman → ACC |
| **2 — Outline** | Menyusun kerangka laporan (daftar bab/section) | Cek outline → ACC |
| **3a — Hasil & Pembahasan** | Menulis draf bab ini berdasarkan screenshot | Cek draf → ACC / revisi |
| **3b — Dasar Teori** | Menulis draf bab ini berdasarkan konteks praktikum | Cek draf → ACC / revisi |
| **4 — Finalisasi** | Menyusun Kesimpulan + Daftar Pustaka, lalu **langsung membuat file `.tex`** | Cek file → revisi jika perlu |

## 5. Skill Pendukung

- `/breakdown-matkul` — Mengekstrak pedoman formatting dari file `.tex` contoh menjadi file `.md` panduan. Gunakan saat menambahkan matkul baru.
- `/make-laprak-info` — Menampilkan panduan ini.

## 6. Menambahkan Mata Kuliah Baru

1. Taruh file `.tex` contoh laporan di `skills/make-laprak/matkul/<NAMA_MATKUL>/`.
2. Jalankan `/breakdown-matkul` untuk generate pedoman `.md` secara otomatis.
3. Selesai — `/make-laprak` akan otomatis mengenali matkul baru tersebut.

## 7. Dokumentasi & Kontribusi

- 📂 Repositori: [github.com/AcademyCity-RND/MyLaprak](https://github.com/AcademyCity-RND/MyLaprak)
- 📝 Panduan kontribusi: lihat file `CONTRIBUTING.md` di repositori.
