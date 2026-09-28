# Panduan Kontribusi — MyLaprak

Terima kasih telah tertarik untuk berkontribusi! Panduan ini menjelaskan cara menambahkan gaya matkul baru agar plugin `make-laprak` bisa menyesuaikan format laporan untuk mata kuliah Anda.

---

## 🎯 Cara Berkontribusi: Menambahkan Gaya Matkul Baru

### Langkah 1 — Siapkan Contoh Laporan `.tex`

Kumpulkan minimal **1 file `.tex`** laporan praktikum yang sudah pernah Anda kumpulkan dan nilainya bagus. Semakin banyak contoh, semakin presisi AI memahami gaya penulisan Anda.

**Tips:**
- File `.tex` sebaiknya hanya berisi **body** laporan (mulai dari `\chapter{Dasar Teori}` sampai `\end{thebibliography}`), bukan preamble (`\documentclass`, `\usepackage`, dll).
- Beri nama file secara berurutan: `MATKUL1.tex`, `MATKUL2.tex`, dst.
- Nama file harus mencerminkan urutan kronologis (pertemuan 1, 2, 3...).

### Langkah 2 — Buat Folder Matkul

Buat folder baru di dalam `skills/make-laprak/matkul/`:

```
skills/make-laprak/matkul/<NAMA_MATKUL>/
├── <NAMA_MATKUL>.md       ← Pedoman formatting (lihat Langkah 3)
├── <NAMA_MATKUL>1.tex     ← Contoh laporan #1
├── <NAMA_MATKUL>2.tex     ← Contoh laporan #2 (opsional)
└── <NAMA_MATKUL>3.tex     ← Contoh laporan #3 (opsional)
```

Contoh untuk mata kuliah "Pemrograman Berorientasi Objek":
```
skills/make-laprak/matkul/PBO/
├── PBO.md
├── PBO1.tex
└── PBO2.tex
```

### Langkah 3 — Buat File Pedoman `.md`

File `.md` adalah panduan yang akan dibaca AI saat menulis laporan. Anda bisa:

**Opsi A (Otomatis):** Gunakan skill `/breakdown-matkul` untuk mengekstrak pedoman secara otomatis dari file `.tex` Anda. AI akan menganalisis pola dan menghasilkan file `.md` terstandar.

**Opsi B (Manual):** Tulis sendiri file `.md` mengikuti template di bawah ini.

---

## 📄 Template File Pedoman `.md`

Gunakan struktur berikut sebagai kerangka. Isi setiap bagian berdasarkan pola yang Anda temukan di file `.tex` Anda:

```markdown
# Pedoman Penulisan Laporan Mata Kuliah [NAMA_MATKUL]

Dokumen ini adalah panduan **wajib baca** bagi AI sebelum menyusun laporan.
Diekstrak dari [N] laporan riil: `file1.tex`, `file2.tex`, dst.

> **ATURAN UTAMA:** Jangan mengarang format sendiri. Ikuti pola di bawah ini.

---

## 1. Struktur Bab (Wajib, Urut)
<!-- Daftar \chapter, \section, \subsection yang konsisten di semua referensi -->

## 2. Dasar Teori
<!-- Aturan penulisan: gaya naratif, sitasi, penggunaan gambar ilustrasi -->

## 3. Hasil dan Pembahasan — Tata Letak Gambar
<!-- Dokumentasikan gaya figure yang dipakai (beri label: Gaya A/B/C) -->
<!-- Sertakan contoh kode LaTeX -->
<!-- Sertakan tabel panduan lebar gambar jika ada variasi -->

## 4. Kesimpulan
<!-- Format: enumerate atau paragraf? Seberapa detail? -->

## 5. Tautan Repositori (jika ada)
<!-- Di mana source code dicantumkan? Section sendiri atau di daftar pustaka? -->

## 6. Daftar Pustaka
<!-- Format: thebibliography+cite ATAU enumerate+ref? -->
<!-- Sertakan contoh kode LaTeX -->

## 7. Konvensi Penulisan LaTeX
<!-- Italic, monospace, escape characters, clearpage, dll -->

## 8. Instruksi Adaptasi untuk AI
<!-- Panduan kapan menggunakan gaya mana -->
```

---

## 🔀 Alur Git untuk Kontribusi

1. **Fork** repositori ini.
2. Buat branch baru: `feat/add-matkul-<nama>` (misal: `feat/add-matkul-pbo`).
3. Tambahkan folder matkul + file `.tex` + file `.md`.
4. Commit dan buat **Pull Request** ke branch `dev`.
5. Tunggu review dan merge.

---

## ⚠️ Hal yang Perlu Diperhatikan

- **Jangan mengubah** file `SKILL.md` utama (`skills/make-laprak/SKILL.md`) kecuali ada bug atau perbaikan workflow.
- **Jangan mengubah** pedoman matkul milik orang lain tanpa persetujuan.
- File `.tex` referensi sebaiknya **sudah dianonimkan** (hapus nama asli, NIM, dll) sebelum di-push ke repositori publik.
- Pastikan file `.md` mengikuti template di atas agar konsisten antar matkul.

---

## 💡 Tips

- Mulai dengan 1 file `.tex` saja. Anda bisa menambahkan lebih banyak referensi seiring waktu.
- Gunakan `/breakdown-matkul` setiap kali menambahkan `.tex` baru agar `.md` selalu ter-update.
- Perhatikan evolusi gaya penulisan Anda — `.tex` terbaru biasanya yang paling matang.
