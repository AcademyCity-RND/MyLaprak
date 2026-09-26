# Pedoman Penulisan Laporan Mata Kuliah KEPL

Dokumen ini adalah panduan **wajib baca** bagi AI sebelum menyusun Laporan Praktikum KEPL (Konstruksi dan Evolusi Perangkat Lunak). Panduan diekstrak dari 3 laporan riil: `KEPL1.tex` (Pertemuan 1), `KEPL2.tex` (Pertemuan 2), dan `KEPL3.tex` (Pertemuan 3).

> **ATURAN UTAMA:** Jangan mengarang format sendiri. Ikuti pola di bawah ini secara ketat.

---

## 1. Struktur Bab (Wajib, Urut)

```
\chapter{Dasar Teori}
\chapter{Hasil dan Pembahasan}
\chapter{Kesimpulan}
\chapter{Daftar Pustaka}
```

- Di dalam setiap `\chapter`, gunakan `\section`, `\subsection`, dan `\subsubsection` secara hierarkis.
- Gunakan `\clearpage` di antara section besar untuk menjaga kerapian halaman.

---

## 2. Dasar Teori

- Tulis secara akademis, naratif, dan *to the point*.
- Bagi per topik teknologi utama menggunakan `\section` dan `\subsection`.
- **WAJIB** sisipkan gambar ilustrasi konsep (diagram arsitektur, alur kerja) di dalam Dasar Teori, bukan hanya teks.
- **WAJIB** gunakan sitasi. Format sitasi mengikuti format Daftar Pustaka yang dipilih (lihat Bagian 6).
- Istilah asing ditulis dalam `\textit{...}` (*italic*).
- Nama perintah/file/variabel ditulis dalam `\texttt{...}` (monospace).

---

## 3. Hasil dan Pembahasan — Tata Letak Gambar

Ini adalah bagian terpenting. Anda punya **3 gaya valid** yang sudah terbukti diterima. Pilih secara dinamis sesuai konteks:

### Gaya A — Analitis Terpisah (dari KEPL1)
Cocok untuk: gambar tunggal yang butuh penjelasan teknis mendalam (misal: konfigurasi, error log).

```latex
\begin{figure}[H]
    \centering
    \includegraphics[width=0.6\textwidth]{gambar.png}
    \caption{Judul Gambar}
    \label{fig:label}
\end{figure}
Penjelasan Gambar:
\begin{itemize}
    \item Poin analisis pertama.
    \item Poin analisis kedua.
\end{itemize}
```

**Aturan Gaya A:**
- Lebar standar: `0.6\textwidth`.
- Teks `Penjelasan Gambar:` (tanpa bold/italic) ditulis **tepat di bawah** `\end{figure}`.
- Isi `\itemize` harus analitis, bukan mengulang caption.

### Gaya B — Naratif Dikelompokkan (dari KEPL2)
Cocok untuk: langkah berurutan yang padat (misal: tahap Build lalu Test).

```latex
Paragraf naratif menjelaskan konteks sebelum gambar ditampilkan...

\begin{figure}[H]
    \centering
    \includegraphics[width=0.9\textwidth]{gambar1.png}
    \caption{Judul Gambar 1}

    \vspace{0.5cm}

    \includegraphics[width=0.9\textwidth]{gambar2.png}
    \caption{Judul Gambar 2}
\end{figure}
```

**Aturan Gaya B:**
- Lebar standar: `0.9\textwidth`.
- Penjelasan berupa **paragraf naratif sebelum figure**, bukan itemize sesudahnya.
- Maksimal 2 gambar per blok `figure`, dipisahkan `\vspace{0.5cm}`.

### Gaya C — Naratif Individual (dari KEPL3)
Cocok untuk: gambar individual namun penjelasannya berbentuk naratif mengalir (bukan poin-poin).

```latex
Paragraf naratif yang menjelaskan konteks teknis secara mendalam...

\begin{figure}[H]
    \centering
    \includegraphics[width=0.6\textwidth]{gambar.png}
    \caption{Judul Gambar}
\end{figure}
```

**Aturan Gaya C:**
- Lebar bervariasi sesuai konten gambar (lihat tabel di bawah).
- Penjelasan ditulis sebagai **paragraf naratif sebelum figure**.
- Setiap gambar berdiri sendiri dalam satu blok `figure`.

### Panduan Pemilihan Lebar Gambar

| Konten Gambar | Lebar |
|---|---|
| Potongan kode/script pendek | `0.5\textwidth` – `0.6\textwidth` |
| Struktur folder/hierarki | `0.55\textwidth` |
| Screenshot terminal/log | `0.6\textwidth` – `0.8\textwidth` |
| Screenshot UI halaman web | `0.8\textwidth` – `0.9\textwidth` |
| Diagram arsitektur/alur | `0.7\textwidth` – `0.9\textwidth` |
| Dashboard/panel admin | `0.8\textwidth` – `0.9\textwidth` |

### Gambar Berdampingan (Side-by-Side)
Jika ada 2 gambar yang perlu dibandingkan secara langsung:

```latex
\begin{figure}[H]
    \centering
    \begin{minipage}[b]{0.48\textwidth}
        \centering
        \includegraphics[width=\textwidth]{gambar_kiri.png}
    \end{minipage}
    \hfill
    \begin{minipage}[b]{0.48\textwidth}
        \centering
        \includegraphics[width=\textwidth]{gambar_kanan.png}
    \end{minipage}
    \caption{Judul Gabungan (Kiri: X, Kanan: Y)}
    \label{fig:label}
\end{figure}
```

---

## 4. Kesimpulan

- Gunakan `\begin{enumerate}` untuk menyusun poin-poin kesimpulan.
- Setiap poin harus **substansial dan spesifik** terhadap apa yang dikerjakan di praktikum, bukan generik.
- Boleh juga berupa satu paragraf solid jika konteksnya sederhana (lihat KEPL2).

---

## 5. Tautan Repositori (Opsional)

Jika ada source code, bisa ditempatkan di:
- Section terpisah di akhir Hasil dan Pembahasan (`\section{Tautan Repositori Kode Sumber}`), ATAU
- Di dalam item Daftar Pustaka sebagai entri terakhir.

---

## 6. Daftar Pustaka — Pilih Salah Satu Format

### Format A: thebibliography (dari KEPL1)
```latex
\renewcommand{\bibname}{Daftar Pustaka}
\begin{thebibliography}{9}
\bibitem{label} Penulis. \textit{Judul}. Penerbit, Tahun. URL.
\end{thebibliography}
```
Dipanggil di teks dengan: `\cite{label}`

### Format B: enumerate (dari KEPL2/KEPL3) — **DIREKOMENDASIKAN**
```latex
\chapter{Daftar Pustaka}
\begin{enumerate}
    \item \label{label} Penulis. \textit{Judul}. Platform, Tahun. URL.
\end{enumerate}
```
Dipanggil di teks dengan: `[\ref{label}]`

> **Pilih satu format dan gunakan secara konsisten di seluruh dokumen.**
> Format B direkomendasikan karena digunakan di 2 dari 3 laporan terakhir.

---

## 7. Konvensi Penulisan LaTeX

- Istilah asing: `\textit{...}` — contoh: `\textit{deployment}`, `\textit{pipeline}`
- Nama file/perintah: `\texttt{...}` — contoh: `\texttt{ci.yml}`, `\texttt{npm test}`
- Semua figure wajib menggunakan `[H]` untuk posisi tetap.
- Gunakan `\allowbreak` di dalam `\texttt{...}` untuk URL/path panjang.
- Escape karakter khusus: `\_` untuk underscore, `\&` untuk ampersand.

---

## 8. Instruksi Adaptasi untuk AI

Saat mengerjakan laporan KEPL:
1. Baca `inisiasi.txt` secara mendalam terlebih dahulu.
2. **Jangan mencampur gaya** dalam satu subsection. Pilih satu gaya (A/B/C) per subsection dan konsisten.
3. Jika inisiasi.txt memberikan penjelasan panjang per gambar → gunakan **Gaya A**.
4. Jika penjelasan singkat dan gambar berurutan → gunakan **Gaya B** atau **Gaya C**.
5. Sesuaikan lebar gambar berdasarkan tabel panduan, bukan asal pilih 0.9 untuk semua.
6. Gunakan **Format B** (enumerate) untuk Daftar Pustaka kecuali user meminta sebaliknya.
7. Selalu perhatikan pola dari file `.tex` referensi terbaru sebagai acuan utama gaya penulisan.
