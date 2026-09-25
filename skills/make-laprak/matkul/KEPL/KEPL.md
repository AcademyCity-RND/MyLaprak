# Pedoman Penulisan Laporan Mata Kuliah KEPL
Dokumen ini merupakan panduan spesifik untuk AI dalam menyusun Laporan Praktikum mata kuliah Konstruksi dan Evolusi Perangkat Lunak (KEPL). Panduan ini diekstrak dari contoh laporan riil (`KEPL1.tex` dan `KEPL2.tex`). 

Selalu patuhi aturan berikut saat *user* meminta laporan untuk matkul KEPL:

## 1. Struktur Bab dan Sub-bab
Laporan KEPL umumnya memiliki hierarki baku berikut:
- **Bab: Dasar Teori** (`\chapter{Dasar Teori}`)
- **Bab: Hasil dan Pembahasan** (`\chapter{Hasil dan Pembahasan}`)
  - Gunakan `\section`, `\subsection`, hingga `\subsubsection` secara terstruktur untuk mengelompokkan tahapan pengerjaan.
- **Bab: Kesimpulan** (`\chapter{Kesimpulan}`)
- **Daftar Pustaka** (`\chapter{Daftar Pustaka}` atau `\begin{thebibliography}`)

## 2. Gaya Penulisan Dasar Teori
- Tuliskan landasan teori secara akademis, mengalir (*narrative*), dan *to the point*.
- Bagi menjadi sub-bab (`\section` atau `\subsection`) sesuai dengan topik teknologi utama.
- **WAJIB** menggunakan sitasi/kutipan pada akhir kalimat penjelasan. Anda bisa menggunakan format `\cite{...}` atau format referensi manual `[\ref{...}]` bergantung pada cara Anda menyusun Daftar Pustaka nanti.

## 3. Tata Letak Gambar & Penjelasan (Hasil dan Pembahasan)
Anda memiliki dua opsi gaya visual yang valid dari referensi riil. Gunakan secara dinamis berdasarkan seberapa padat langkah yang ada:

### Gaya A: Analitis & Terpisah (Referensi KEPL1)
Cocok untuk gambar tunggal yang butuh penjelasan teknis mendalam.
- Gambar ditaruh menggunakan `\begin{figure}[H]` dengan `width=0.6\textwidth`.
- **Tepat di bawah tag `\end{figure}`**, tambahkan teks `Penjelasan Gambar:` (tanpa *bold*).
- Lalu jelaskan analisisnya menggunakan poin-poin `\begin{itemize}`.

### Gaya B: Naratif & Dikelompokkan (Referensi KEPL2)
Cocok untuk langkah berurutan (misal: tahap *Build*, lalu *Test*).
- Penjelasan ditulis dalam bentuk **paragraf naratif tepat sebelum gambar** dipanggil.
- Jika ada 2 gambar yang saling berkaitan erat, gabungkan ke dalam **satu blok `figure`** untuk menghemat ruang, pisahkan menggunakan `\vspace{0.5cm}`.
- Gunakan lebar `width=0.9\textwidth`.

*Contoh Format Kode Gaya B (Gambar Digabung):*
```latex
Tahap Build dan Test dikonfigurasi khusus untuk menyetel environment pengujian agar sesuai...

\begin{figure}[H]
    \centering
    \includegraphics[width=0.9\textwidth]{"gambar_build.png"}
    \caption{Konfigurasi tahap Build}
    
    \vspace{0.5cm}
    
    \includegraphics[width=0.9\textwidth]{"gambar_test.png"}
    \caption{Konfigurasi tahap Test}
\end{figure}
```

## 4. Kesimpulan
- Kesimpulan ditulis secara komprehensif, bukan terlalu umum.
- Jika berupa poin, gunakan penomoran `\begin{enumerate}`. Namun, format paragraf tunggal yang solid juga diizinkan.
- Kesimpulan harus mencakup *best practices* atau esensi arsitektur/teknologi dari praktikum (misal: CI/CD, Branch Protection, dsb).

## 5. Daftar Pustaka
Anda bisa menggunakan salah satu dari dua format valid ini (pilih salah satu dan konsisten):
- **Format Bawaan:** `\begin{thebibliography}{9}` lalu gunakan `\bibitem{label}`. Di teks dipanggil dengan `\cite{label}`.
- **Format Enumerate:** `\chapter{Daftar Pustaka}` diikuti `\begin{enumerate}` lalu `\item \label{label} Deskripsi buku/web`. Di teks dipanggil dengan `[\ref{label}]`.

---
**Instruksi untuk AI:** Saat mengerjakan laporan KEPL, baca `inisiasi.txt` secara mendalam. Jika penjelasannya singkat, Anda bisa menggabungkan beberapa gambar dalam satu `figure` (Gaya B). Jika penjelasannya panjang per gambar, pecah dan gunakan `itemize` (Gaya A)!
