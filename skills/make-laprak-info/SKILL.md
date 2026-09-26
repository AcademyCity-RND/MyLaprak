---
name: make-laprak-info
description: >-
  Gunakan skill ini jika pengguna mengetik command "/make-laprak-info" atau meminta informasi tentang apa itu plugin/skill make-laprak.
---

# SYSTEM PROMPT: INFO PLUGIN MAKE-LAPRAK

Jika skill ini dipanggil, Anda WAJIB memberikan output teks penjelasan interaktif kepada pengguna mengenai plugin `make-laprak`.

## Instruksi Output
Berikan balasan dengan format Markdown yang rapi, mencakup poin-poin berikut (gunakan gaya bahasa yang ramah dan suportif):

1. **Apa itu `/make-laprak`?**
   Jelaskan bahwa ini adalah asisten AI (Plugin Antigravity) yang dirancang khusus untuk menyusun Laporan Praktikum tingkat Universitas berbasis LaTeX atau Markdown.

2. **Untuk Apa Fungsinya?**
   Jelaskan bahwa fungsinya adalah untuk mengotomatisasi kerangka laporan, merangkum modul, mengolah gambar *screenshot* (dari `inisiasi.txt`), dan menyusun dasar teori serta pembahasan secara terstruktur tanpa halusinasi.

3. **Cara Penggunaan & Struktur Folder**
   Jelaskan alur kerja dan penempatan folder yang benar, agar pengguna tidak bingung:
   - **TIDAK PERLU** menaruh file tugas di dalam folder sistem plugin.
   - Pengguna bebas membuat folder kerja pertemuan (misal `Praktikum-Minggu-1`) **di mana saja**.
   - Di dalam folder pertemuan tersebut, siapkan:
     1. File `inisiasi.txt` (Peta/penjelasan gambar).
     2. Modul praktikum PDF (Opsional).
     3. Folder `gambar/` atau `screenshot-hasil/` berisi *screenshot* bernomor (misal 1.png).
     4. (Opsional) File `template.tex` jika format laporannya berubah-ubah. (Jika formatnya menetap, AI akan mengambil otomatis dari memori plugin).
   - Setelah folder siap, pengguna tinggal menjalankan command `/make-laprak` di folder tersebut.
   - AI akan memandu penyusunan secara iteratif (Tahap 1-3), dan pada Tahap 4 AI akan **langsung/otomatis membuat file fisik `.tex`** di folder kerja pengguna.

4. **Link Dokumentasi / Repositori**
   Sertakan tautan resmi menuju repositori GitHub agar pengguna bisa membaca dokumentasi lengkapnya atau berkontribusi:
   `https://github.com/AcademyCity-RND/MyLaprak`

**Aksi Anda:** 
Langsung hasilkan teks tersebut kepada pengguna saat skill ini aktif. Jangan membuat aksi atau modifikasi file.
