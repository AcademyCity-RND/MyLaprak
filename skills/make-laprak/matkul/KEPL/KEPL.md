# Pedoman Penulisan Laporan Mata Kuliah KEPL
Dokumen ini merupakan panduan spesifik untuk AI dalam menyusun Laporan Praktikum mata kuliah Konstruksi dan Evolusi Perangkat Lunak (KEPL). Panduan ini diekstrak dari contoh laporan riil (`KEPL.tex`). 

Selalu patuhi aturan berikut saat *user* meminta laporan untuk matkul KEPL:

## 1. Struktur Bab dan Sub-bab
Laporan KEPL umumnya memiliki hierarki baku berikut:
- **Bab 1: Dasar Teori** (`\chapter{Dasar Teori}`)
- **Bab 2: Hasil dan Pembahasan** (`\chapter{Hasil dan Pembahasan}`)
  - **Hasil Praktikum** (`\section{Hasil Praktikum}`)
  - (Opsional, tergantung tugas) **Tautan Repositori Kode Sumber** (`\section{Tautan Repositori Kode Sumber}`)
- **Bab 3: Kesimpulan** (`\chapter{Kesimpulan}`)
- **Daftar Pustaka** (`\begin{thebibliography}`)

## 2. Gaya Penulisan Dasar Teori
- Tuliskan landasan teori secara akademis dan *to the point*.
- Bagi menjadi sub-bab (`\section`) sesuai dengan topik teknologi atau konsep utama yang dibahas di praktikum (misal: Git, GitHub, Laravel, CI/CD).
- **WAJIB** menggunakan sitasi/kutipan pada akhir kalimat penjelasan menggunakan perintah `\cite{kunci_sitasi}`. Jangan lupa siapkan daftar pustakanya di bagian paling bawah.

## 3. Gaya Penulisan Hasil dan Pembahasan (Crucial)
Ini adalah inti dari laporan KEPL. Format penggabungan gambar dan penjelasannya sangat spesifik:
- Kelompokkan gambar-gambar yang memiliki konteks sama ke dalam `\subsection` atau `\subsubsection` yang rapi.
- Setiap gambar di-*insert* menggunakan *environment* `\begin{figure}[H]`, lengkap dengan `\caption` dan `\label`. Lebar standar gambar adalah `0.6\textwidth` atau menyesuaikan jika gambar berpasangan.
- **Tepat di bawah tag `\end{figure}`**, Anda WAJIB menambahkan teks `Penjelasan Gambar:` (tanpa dicetak tebal/miring).
- Tepat di bawah teks tersebut, buatlah rincian penjelasan menggunakan poin-poin `\begin{itemize}`.
- Isi *itemize* (poin-poin penjelasan) harus menjelaskan **apa yang terjadi di gambar tersebut secara analitis**, bukan sekadar mengulang judul gambar. 

*Contoh Format Kode:*
```latex
\begin{figure}[H]
    \centering
    \includegraphics[width=0.6\textwidth]{"nama_gambar.png"}
    \caption{Judul Gambar}
    \label{fig:label_gambar}
\end{figure}
Penjelasan Gambar:
\begin{itemize}
    \item Poin analisis pertama terkait proses yang terjadi di gambar.
    \item Poin analisis kedua yang lebih mendalam.
\end{itemize}
```

## 4. Kesimpulan
- Kesimpulan harus ditulis menggunakan penomoran `\begin{enumerate}`.
- Isi kesimpulan adalah rangkuman dari *best practices* atau esensi praktikum yang dilakukan (berdasarkan Bab Hasil dan Pembahasan). Jangan membuat kesimpulan yang terlalu umum.

## 5. Daftar Pustaka
- Gunakan *environment* standar `\begin{thebibliography}{9}`.
- Format penulisan referensi menggunakan gaya APA sederhana atau format standar buku/jurnal teknis.
- Pastikan semua kunci sitasi (`\bibitem{...}`) cocok persis dengan yang dipanggil di Bab Dasar Teori (`\cite{...}`).

---
**Instruksi untuk AI:** Saat mengerjakan laporan KEPL, selalu baca `inisiasi.txt` dari user, lalu terjemahkan penjelasan user tersebut ke dalam format `itemize` di bawah gambar sesuai kaidah di atas!
