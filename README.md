# MyLaprak - Antigravity Plugin

Repositori ini adalah **Plugin Antigravity** yang menyediakan _Skill_ AI khusus untuk menyusun Laporan Praktikum secara interaktif, terstruktur, dan siap pakai dalam format LaTeX.

## 📦 Instalasi Plugin

Kloning repositori ini ke direktori plugin Antigravity:

**Instalasi Global (berlaku untuk semua workspace):**
```bash
git clone https://github.com/AcademyCity-RND/MyLaprak.git ~/.gemini/config/plugins/make-laprak
```

**Instalasi Lokal (per workspace):**
```bash
mkdir -p .agents/plugins/
git clone https://github.com/AcademyCity-RND/MyLaprak.git .agents/plugins/make-laprak
```

## 📂 Struktur Folder Plugin

```
MyLaprak/
├── plugin.json                          # Manifest plugin
├── README.md                            # Dokumentasi ini
├── CONTRIBUTING.md                      # Panduan kontributor
├── scripts/                             # Script utilitas (co-author, dll)
├── skills/
│   ├── make-laprak/                     # Skill utama — menulis laporan
│   │   ├── SKILL.md                     # Instruksi AI (System Prompt)
│   │   ├── matkul/                      # Referensi per mata kuliah
│   │   │   └── KEPL/                    # Contoh: mata kuliah KEPL
│   │   │       ├── KEPL.md              # Pedoman formatting AI
│   │   │       ├── KEPL1.tex            # Contoh laporan riil #1
│   │   │       ├── KEPL2.tex            # Contoh laporan riil #2
│   │   │       └── KEPL3.tex            # Contoh laporan riil #3
│   │   └── template-general/            # Template umum (reserved)
│   ├── breakdown-matkul/                # Skill breakdown .tex → .md
│   │   └── SKILL.md
│   └── make-laprak-info/                # Skill info/bantuan
│       └── SKILL.md
```

## 🚀 Cara Menggunakan

> **PENTING:** Anda **TIDAK PERLU** menaruh file tugas di dalam folder plugin ini. Plugin bertindak sebagai "otak" di latar belakang.

### Langkah 1 — Siapkan Folder Kerja
Buat folder kerja pertemuan **di mana saja** (misal: `D:\Tugas\KEPL\Pertemuan-4\`).

### Langkah 2 — Isi Folder Kerja
Di dalam folder tersebut, siapkan:
- `inisiasi.txt` — Catatan/peta penjelasan Anda tentang setiap screenshot.
- Folder `gambar/` — Screenshot bernomor (misal: `1.png`, `2.png`, dst).
- (Opsional) Modul PDF atau PPT pertemuan.

### Langkah 3 — Panggil AI
Buka workspace/terminal di folder tersebut, lalu ketik perintah. Contoh:
```
/make-laprak buatkan laporan KEPL, saya sudah siapkan inisiasi.txt dan folder gambar
```

### Langkah 4 — Ikuti Alur Iteratif
AI akan bekerja dalam **5 tahap** dan selalu meminta persetujuan (ACC) Anda:
1. **Tahap 1 — Inisiasi:** AI membaca referensi dan merangkum pemahaman.
2. **Tahap 2 — Outline:** AI menyusun kerangka laporan.
3. **Tahap 3a — Hasil dan Pembahasan:** AI menulis draf bab ini.
4. **Tahap 3b — Dasar Teori:** AI menulis draf bab ini.
5. **Tahap 4 — Finalisasi:** AI menyusun Kesimpulan + Daftar Pustaka, lalu **langsung membuat file `.tex`** di folder Anda.

## 🎨 Menambahkan Gaya Matkul Baru

Ingin agar AI menyesuaikan gaya penulisan untuk matkul lain? Tambahkan folder baru:

```
skills/make-laprak/matkul/<NAMA_MATKUL>/
├── <NAMA_MATKUL>.md      # Pedoman formatting (wajib)
├── contoh1.tex            # Contoh laporan riil (minimal 1)
└── contoh2.tex            # (opsional, semakin banyak semakin presisi)
```

AI akan otomatis mendeteksi dan mempelajari gaya penulisan dari file `.tex` referensi Anda. Semakin banyak contoh, semakin adaptif AI terhadap ciri khas penulisan Anda.

## 👥 Kontributor (Co-Author) Otomatis

Jika Anda menggunakan repositori ini, Anda bisa menyetel agar nama kreator ditambahkan sebagai Co-author otomatis pada setiap commit:

- **Windows:** Jalankan `scripts/setup-contributor.bat`
- **Linux/Mac:** Jalankan `bash scripts/setup-contributor.sh`

## ℹ️ Bantuan Cepat

Ketik `/make-laprak-info` untuk melihat panduan penggunaan langsung di chat.

---

## 🗺️ Roadmap

- [ ] Cross-Platform Adapters (`.cursorrules`, `CLAUDE.md`, `.github/copilot-instructions.md`)
- [ ] Agnostic Core Prompts (pisahkan prompt dari folder `skills/`)
- [ ] Fallback Script Pencari Jurnal (`scripts/search_jurnal.py`)
- [ ] Integrasi MCP untuk pencarian jurnal ilmiah
- [ ] Universal Setup Script (`install.sh` / `install.bat`)