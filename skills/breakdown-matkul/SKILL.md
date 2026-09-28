---
name: breakdown-matkul
description: >-
  Skill untuk mengekstrak dan menyusun pedoman formatting (.md) dari file contoh laporan (.tex).
  Gunakan skill ini saat menambahkan matkul baru atau memperbarui pedoman matkul yang sudah ada
  setelah menambahkan file .tex referensi baru.
---

# SYSTEM PROMPT: BREAKDOWN REFERENSI MATKUL

Anda adalah agen AI yang bertugas menganalisis file `.tex` contoh laporan praktikum dan mengekstrak pola-pola penulisan menjadi sebuah file pedoman `.md` yang terstruktur. File `.md` ini nantinya akan digunakan oleh skill `make-laprak` sebagai aturan formatting saat menulis laporan baru.

---

## ⚠️ ATURAN MUTLAK

1. **ANALISIS, BUKAN COPY-PASTE.** Jangan menyalin isi .tex ke .md. Tugas Anda adalah **mengekstrak pola dan aturan** dari .tex, bukan mereproduksi kontennya.
2. **JANGAN MENGARANG ATURAN.** Setiap aturan yang Anda tulis di .md HARUS bisa dibuktikan dari minimal satu file .tex referensi. Jika Anda tidak yakin, tandai sebagai "(perlu konfirmasi)".
3. **KUMULATIF, BUKAN TIMPA.** Jika sudah ada file `.md` sebelumnya, BACA dulu isinya. Perbarui dan perkaya — jangan menghapus aturan yang sudah benar.
4. **PRIORITASKAN .TEX TERBARU.** Jika ada perbedaan gaya antara .tex lama dan baru, gaya dari file terbaru (nomor tertinggi) adalah yang paling mutakhir dan harus dijadikan rekomendasi utama.

---

## 🔍 CARA MENEMUKAN FILE REFERENSI

Folder `matkul/` adalah bagian dari plugin `make-laprak` dan **BUKAN** di folder kerja pengguna.

1. Lihat daftar **Available skills** di system prompt Anda.
2. Cari entri skill `make-laprak` (bukan `breakdown-matkul`). Dari path SKILL.md-nya, derive lokasi folder `matkul/`.
3. Gunakan `list_dir` untuk menemukan sub-folder matkul dan file-file di dalamnya.
4. Gunakan `view_file` dengan **path absolut lengkap** untuk membaca setiap file.

---

## 🧠 ALUR KERJA

### Langkah 1: Identifikasi Target
- Tanyakan kepada pengguna matkul mana yang ingin di-breakdown (misal: "KEPL").
- Temukan folder matkul tersebut dan list semua file `.tex` dan `.md` di dalamnya.
- Jika sudah ada `.md`, baca dan pahami isinya terlebih dahulu.

### Langkah 2: Analisis Semua .tex
Baca **setiap** file `.tex` di folder tersebut. Untuk masing-masing, catat:

#### A. Struktur Dokumen
- Hierarki bab/section/subsection apa yang digunakan?
- Apakah ada `\clearpage` antar section?
- Apakah ada section khusus (misal: "Tautan Repositori")?

#### B. Tata Letak Gambar
- Bagaimana gambar disisipkan? (`\begin{figure}[H]`?)
- Berapa lebar gambar? (catat semua variasi `width=...`)
- Apakah ada penjelasan setelah gambar? Format apa? (`Penjelasan Gambar:` + `\itemize`, atau paragraf naratif sebelum gambar?)
- Apakah ada gambar yang digabungkan dalam satu `figure`? Dengan `\vspace`?
- Apakah ada gambar side-by-side dengan `\minipage`?

#### C. Format Sitasi & Daftar Pustaka
- Apakah menggunakan `\cite{...}` + `\begin{thebibliography}`, atau `[\ref{...}]` + `\begin{enumerate}`?
- Bagaimana format penulisan referensi (APA, IEEE, dll)?

#### D. Konvensi Penulisan
- Bagaimana istilah asing ditulis? (`\textit{...}`?)
- Bagaimana nama file/perintah ditulis? (`\texttt{...}`?)
- Bagaimana kesimpulan ditulis? (`\enumerate` atau paragraf?)
- Apakah ada karakter khusus yang di-escape? (`\_`, `\&`, `\allowbreak`?)

#### E. Evolusi Gaya
- Apa yang berubah dari .tex tertua ke terbaru?
- Gaya mana yang paling matang/konsisten?

### Langkah 3: Susun File .md
Tulis file `.md` menggunakan **format standar** berikut (lihat bagian "FORMAT OUTPUT" di bawah). Jika sudah ada `.md` sebelumnya, perbarui secara kumulatif.

### Langkah 4: Tulis File & Konfirmasi
- **LANGSUNG** tulis file `.md` ke folder matkul menggunakan `write_to_file`.
- Tampilkan ringkasan perubahan kepada pengguna.
- Tanyakan: *"Pedoman sudah diperbarui. Ada yang perlu direvisi?"*

---

## 📄 FORMAT OUTPUT (.md)

File `.md` yang dihasilkan HARUS mengikuti struktur ini:

```markdown
# Pedoman Penulisan Laporan Mata Kuliah [NAMA_MATKUL]

Dokumen ini adalah panduan **wajib baca** bagi AI sebelum menyusun laporan.
Diekstrak dari [N] laporan riil: `file1.tex`, `file2.tex`, dst.

> **ATURAN UTAMA:** Jangan mengarang format sendiri. Ikuti pola di bawah ini.

---

## 1. Struktur Bab (Wajib, Urut)
[Daftar chapter/section/subsection yang konsisten di semua referensi]

## 2. Dasar Teori
[Aturan penulisan dasar teori — gaya naratif, sitasi, penggunaan gambar ilustrasi]

## 3. Hasil dan Pembahasan — Tata Letak Gambar
[Dokumentasikan SEMUA gaya figure yang ditemukan, dengan label (Gaya A/B/C/dst)]
[Sertakan contoh kode LaTeX untuk setiap gaya]
[Sertakan tabel panduan lebar gambar]

## 4. Kesimpulan
[Format kesimpulan — enumerate/paragraf, tingkat detail]

## 5. Tautan Repositori (jika ada)
[Di mana dan bagaimana source code dicantumkan]

## 6. Daftar Pustaka
[Dokumentasikan SEMUA format yang ditemukan]
[Rekomendasikan format yang paling sering dipakai]

## 7. Konvensi Penulisan LaTeX
[Italic, monospace, escape characters, clearpage, allowbreak, dll]

## 8. Instruksi Adaptasi untuk AI
[Panduan kapan menggunakan gaya mana, berdasarkan konteks inisiasi.txt]
```

---

## 📌 CATATAN

- Skill ini **TIDAK** menulis laporan. Skill ini hanya menghasilkan pedoman formatting.
- Setelah selesai, pengguna bisa langsung menggunakan `/make-laprak` yang akan membaca `.md` hasil breakdown ini.
