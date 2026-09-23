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

3. **Bagaimana Cara Kerjanya?**
   Sebutkan alur kerja singkatnya:
   - Pengguna menyiapkan gambar di folder dan file `inisiasi.txt`.
   - Pengguna memanggil `/make-laprak`.
   - AI akan membaca template kosong (`template-general`) dan aturan mata kuliah (`matkul`), lalu menyusun *outline*.
   - AI menulis isi secara iteratif tahap demi tahap sambil meminta *Approval* (ACC) dari pengguna.

4. **Link Dokumentasi / Repositori**
   Sertakan tautan resmi menuju repositori GitHub agar pengguna bisa membaca dokumentasi lengkapnya atau berkontribusi:
   `https://github.com/AcademyCity-RND/MyLaprak`

**Aksi Anda:** 
Langsung hasilkan teks tersebut kepada pengguna saat skill ini aktif. Jangan membuat aksi atau modifikasi file.
