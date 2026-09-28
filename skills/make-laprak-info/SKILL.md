---
name: make-laprak-info
description: >-
  Gunakan skill ini jika pengguna mengetik command "/make-laprak-info" atau meminta informasi tentang apa itu plugin/skill make-laprak.
---

# SYSTEM PROMPT: INFO PLUGIN MAKE-LAPRAK

Jika skill ini dipanggil, Anda WAJIB memberikan output teks penjelasan kepada pengguna mengenai plugin `make-laprak`. Langsung hasilkan teks berikut, jangan memodifikasi file apapun.

## Instruksi Output

Berikan balasan dengan format Markdown yang rapi, mencakup poin-poin berikut:

1. **Apa itu `/make-laprak`?**
   Ini adalah plugin AI (Antigravity Skill) yang dirancang khusus untuk menyusun Laporan Praktikum tingkat Universitas dalam format LaTeX. Plugin ini bekerja secara iteratif — AI akan memandu Anda tahap demi tahap dan selalu meminta persetujuan (ACC) sebelum melanjutkan.

2. **Fitur Utama**
   - Membaca `inisiasi.txt` (catatan Anda) dan mencocokkan dengan screenshot bernomor.
   - Menyusun Dasar Teori, Hasil dan Pembahasan, Kesimpulan, dan Daftar Pustaka secara terstruktur.
   - Menggunakan referensi sitasi nyata (bukan karangan) dengan fitur pencarian internet.
   - Menyesuaikan format LaTeX dengan aturan spesifik per mata kuliah (misal: KEPL).
   - **Otomatis meng-generate file `.tex`** di folder kerja Anda pada tahap akhir.

3. **Cara Penggunaan & Struktur Folder Kerja**
   - **TIDAK PERLU** menaruh file tugas di dalam folder plugin. Plugin bertindak sebagai "otak" di latar belakang.
   - Buat folder kerja **di mana saja** (misal: `D:\Tugas\KEPL\Pertemuan-4\`).
   - Di dalam folder tersebut, siapkan:
     1. `inisiasi.txt` — Catatan/peta penjelasan Anda tentang setiap screenshot.
     2. Folder `gambar/` — Screenshot bernomor (misal: `1.png`, `2.png`, dst).
     3. (Opsional) Modul PDF atau PPT pertemuan.
   - Buka workspace/terminal di folder tersebut, lalu ketik perintah Anda. Contoh:
     > `/make-laprak buatkan laporan KEPL, saya sudah siapkan inisiasi.txt dan folder gambar`

4. **Alur Kerja (5 Tahap)**
   - **Tahap 1:** AI membaca referensi dan `inisiasi.txt`, lalu merangkum pemahaman → minta ACC.
   - **Tahap 2:** AI menyusun kerangka/outline laporan → minta ACC.
   - **Tahap 3a:** AI menulis draf *Hasil dan Pembahasan* → minta ACC untuk revisi.
   - **Tahap 3b:** AI menulis draf *Dasar Teori* → minta ACC untuk revisi.
   - **Tahap 4:** AI menyusun Kesimpulan + Daftar Pustaka, lalu **langsung membuat file `.tex`** di folder Anda.

5. **Menambahkan Mata Kuliah Baru**
   Jika ingin menambahkan aturan untuk matkul lain, buat folder baru di `skills/make-laprak/matkul/<NAMA_MATKUL>/` dan isi dengan:
   - File `.tex` contoh laporan (sebagai referensi gaya penulisan).
   - File `.md` berisi pedoman formatting yang diekstrak dari contoh tersebut.

6. **Link Dokumentasi**
   Repositori: `https://github.com/AcademyCity-RND/MyLaprak`
