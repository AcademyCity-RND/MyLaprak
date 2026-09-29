# Pedoman Penulisan Laporan Mata Kuliah PPG

Dokumen ini adalah panduan **wajib baca** bagi AI sebelum menyusun Laporan Praktikum PPG (Pemrograman Permainan / Game).
Diekstrak dari 3 laporan riil: `PPG1.tex` (Pertemuan 1), `PPG2.tex` (Pertemuan 2), dan `PPG3.tex` (Pertemuan 3).

> **ATURAN UTAMA:** Jangan mengarang format sendiri. Ikuti pola di bawah ini secara ketat.

> **PERBEDAAN KUNCI DENGAN MATKUL LAIN:** Laporan PPG **TIDAK MEMILIKI** bab Dasar Teori dan **TIDAK MEMILIKI** bab Kesimpulan. Jangan pernah menambahkan kedua bab tersebut kecuali pengguna secara eksplisit memintanya.

---

## 1. Struktur Bab (Wajib, Urut)

```
\chapter{Dokumentasi Praktikum}
  \section{Hasil Praktikum}
    \subsection{...}           ← Kelompokkan berdasarkan tema/fase praktikum
      \subsubsection{...}      ← Opsional, untuk sub-topik dalam satu fase
  \section{Hasil Akhir}        ← Bagian terpisah khusus hasil final/verifikasi
    \subsection{...}
\chapter{Daftar Pustaka}
```

**Catatan penting:**
- Selalu gunakan `\chapter{Dokumentasi Praktikum}` sebagai bab utama (bukan "Hasil dan Pembahasan").
- Selalu pisahkan `\section{Hasil Praktikum}` (proses/langkah kerja) dan `\section{Hasil Akhir}` (verifikasi/output final).
- Gunakan `\clearpage` sebelum `\section{Hasil Akhir}`.
- Subsection diberi nama deskriptif sesuai topik, bukan nomor generik.

---

## 2. Tata Letak Gambar — Satu Gaya Konsisten

Laporan PPG menggunakan **satu gaya tunggal** untuk seluruh dokumen. Tidak ada variasi gaya A/B/C.

### Pola Wajib: Gambar Individual + Keterangan Itemize

```latex
\begin{figure}[H]
    \centering
    \includegraphics[width=0.6\textwidth]{1.png}
    \caption{Judul Deskriptif Gambar}
    \label{fig:1}
\end{figure}
Keterangan Gambar :
\begin{itemize}
    \item Poin penjelasan pertama.
    \item Poin penjelasan kedua.
\end{itemize}
```

**Aturan ketat:**
- Lebar gambar: **selalu `0.6\textwidth`** (sangat konsisten di semua referensi). Satu-satunya pengecualian yang ditemukan adalah `0.4\textwidth` untuk gambar panel kecil/sempit (misal: daftar fungsi di sidebar).
- Label `Keterangan Gambar :` (dengan spasi sebelum titik dua) ditulis **tepat di bawah** `\end{figure}`.
- Variasi label yang juga valid (dari evolusi gaya): `Penjelasan :` atau `Penjelasan Antarmuka Utama Unreal :` — namun `Keterangan Gambar :` adalah yang paling konsisten.
- Setiap gambar WAJIB punya `\label{fig:N}` dengan N = nomor gambar.
- Setiap gambar berdiri sendiri dalam satu blok `figure` (tidak pernah digabung).

### Panduan Lebar Gambar

| Konten Gambar | Lebar |
|---|---|
| Semua jenis (standar) | `0.6\textwidth` |
| Panel kecil/sempit (sidebar, daftar fungsi) | `0.4\textwidth` |

---

## 3. Gaya Penjelasan Gambar

Isi itemize di bawah gambar memiliki dua pola yang berevolusi:

### Pola 1 — Deskriptif Langsung (PPG1 awal, PPG3)
Langsung menjelaskan apa yang terjadi/dilakukan:
```latex
Keterangan Gambar :
\begin{itemize}
    \item Membuat proyek baru menggunakan template \textbf{Third Person}.
    \item Penamaan proyek disesuaikan dengan format yang telah ditentukan.
\end{itemize}
```

### Pola 2 — Terstruktur Cara+Fungsi (PPG2, PPG1 tengah)
Memisahkan *cara melakukan* dan *fungsi/tujuannya*:
```latex
Penjelasan :
\begin{itemize}
    \item \textbf{Cara:} Klik kanan pada Event Graph dan cari Print String.
    \item \textbf{Fungsi:} Berfungsi untuk menampilkan pesan teks ke layar saat permainan dijalankan.
\end{itemize}
```

**Rekomendasi:** Gunakan **Pola 1** untuk langkah prosedural sederhana, dan **Pola 2** untuk penjelasan fitur/node/tool baru yang perlu diperkenalkan cara kerja dan tujuannya.

---

## 4. Section "Hasil Akhir"

- Selalu diawali `\clearpage` lalu `\section{Hasil Akhir}`.
- Boleh diawali kalimat pengantar singkat sebelum subsection (lihat PPG1: *"Bagian ini memaparkan hasil fungsional maupun modifikasi perbaikan..."*).
- Subsection diberi nama deskriptif yang mencerminkan solusi/hasil (contoh: "Implementasi Fisik Collision pada Tanjakan", "Kondisi Karakter Mati (OnDeath)").
- Gambar dan keterangan mengikuti pola yang sama seperti Hasil Praktikum.

---

## 5. Daftar Pustaka

Format yang digunakan: **enumerate + `\label` + `[\ref{...}]`**

```latex
\chapter{Daftar Pustaka}

\begin{enumerate}
    \item \label{epic} Epic Games. \textit{Unreal Engine 5 Documentation}. [Online]. Tersedia: \url{https://...}.

    \item \label{romero} M. Romero. \textit{Blueprints Visual Scripting for Unreal Engine 5}, 3rd ed. Birmingham, UK: Packt Publishing, 2022.
\end{enumerate}
```

**Catatan:**
- Di teks dipanggil dengan `[\ref{label}]`.
- Format penulisan mengikuti standar IEEE.
- Boleh ditambahkan komentar LaTeX (`%`) di atas setiap `\item` untuk menjelaskan relevansi referensi (lihat PPG2/PPG3).
- Referensi yang sangat umum dipakai di PPG: dokumentasi Epic Games, buku Romero (Blueprint), Gregory (Game Engine Architecture), Akenine-Möller (Rendering).

---

## 6. Konvensi Penulisan LaTeX

- Nama fitur/menu/tombol: `\textbf{...}` — contoh: `\textbf{Event Graph}`, `\textbf{Create}`
- Istilah teknis asing: `\textit{...}` — contoh: `\textit{viewport}`, `\textit{collision}`
- Nama file/perintah/kode: `\texttt{...}` (jarang dipakai di PPG, lebih dominan bold)
- Escape: `\_` untuk underscore (sangat sering: `BP\_BOX`, `BPC\_Health`)
- Semua figure wajib `[H]`
- `\clearpage` digunakan sebelum `\section{Hasil Akhir}`
- Notasi matematika inline: `$\geq$` untuk simbol ≥ (lihat PPG2)
- Tanda persen literal: `100\%`

---

## 7. Evolusi Gaya (PPG1 → PPG2 → PPG3)

- **PPG1:** Label keterangan bervariasi (`Keterangan Gambar :`, `Penjelasan :`, `Penjelasan Antarmuka Utama Unreal :`). Struktur: materi → hasil akhir. Banyak subsubsection.
- **PPG2:** Label stabil di `Penjelasan :`. Pola Cara+Fungsi dominan karena banyak memperkenalkan node Blueprint. Tidak ada subsubsection.
- **PPG3:** Kembali ke `Keterangan Gambar :`. Pola deskriptif langsung lebih banyak. Penjelasan lebih ringkas.

**Rekomendasi:** Ikuti gaya PPG3 (terbaru) — label `Keterangan Gambar :`, penjelasan ringkas. Gunakan pola Cara+Fungsi hanya saat memperkenalkan fitur/node baru.

---

## 8. Instruksi Adaptasi untuk AI

1. **JANGAN** menambahkan `\chapter{Dasar Teori}` atau `\chapter{Kesimpulan}` kecuali pengguna secara eksplisit meminta.
2. Selalu gunakan `\chapter{Dokumentasi Praktikum}` sebagai chapter utama.
3. Selalu pisahkan `\section{Hasil Praktikum}` dan `\section{Hasil Akhir}`.
4. Gunakan `0.6\textwidth` untuk semua gambar kecuali gambar panel sempit.
5. Setiap gambar berdiri sendiri — jangan pernah menggabungkan 2 gambar dalam satu `figure`.
6. Nama subsection harus deskriptif dan spesifik, bukan generik.
7. Jika `inisiasi.txt` memperkenalkan fitur/tool baru, gunakan pola Cara+Fungsi. Jika hanya langkah prosedural, gunakan pola deskriptif langsung.
8. Perhatikan pola dari `.tex` referensi terbaru (PPG3) sebagai acuan gaya terkini.
