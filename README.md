# MyLaprak - Antigravity Plugin

Repositori ini adalah sebuah **Plugin Antigravity** yang menyediakan _Skill_ khusus untuk membantu Anda menyusun Laporan Praktikum secara interaktif, terstruktur, dan siap pakai.

## 📦 Instalasi Plugin

Karena repositori ini sudah diatur sebagai plugin untuk Antigravity, Anda bisa menginstalnya dengan mengkloning repositori ini ke dalam direktori konfigurasi `.agents/plugins/` di proyek/workspace Anda, atau ke konfigurasi global `~/.gemini/config/plugins/`.

**Contoh Instalasi ke Workspace Lokal:**
```bash
# 1. Pindah ke root folder proyek/workspace laporan Anda
cd /path/ke/Laporan-Kuliah-Workspace

# 2. Buat folder untuk plugins jika belum ada
mkdir -p .agents/plugins/

# 3. Kloning repositori ini
git clone https://github.com/AcademyCity-RND/MyLaprak.git .agents/plugins/MyLaprak
```

## 👥 Menambahkan Kontributor (Co-Author) Otomatis
Sebagai wujud apresiasi, jika Anda menggunakan repositori ini, Anda bisa menyetel agar nama kreator (`Avin1731`) ditambahkan secara otomatis sebagai **Co-author** pada setiap `git commit` yang Anda buat.

Kami sudah menyediakan script instalasi untuk mengonfigurasi Git Template:

- **Windows:** Jalankan klik ganda pada `scripts/setup-contributor.bat` atau jalankan via terminal.
- **Linux/Mac:** Jalankan via terminal `bash scripts/setup-contributor.sh`.

## 📂 Struktur Folder Plugin

- `plugin.json`: File manifest yang mendeklarasikan folder ini sebagai plugin.
- `skills/make-laprak/SKILL.md`: File instruksi AI (Prompt Utama).
- `skills/make-laprak-info/SKILL.md`: File instruksi AI khusus untuk menampilkan dokumentasi bantuan (`/make-laprak-info`).
- `skills/make-laprak/matkul/`: Folder berisi spesifikasi atau aturan per mata kuliah.
- `skills/make-laprak/template-general/`: Folder berisi *template* laporan kosong yang dapat Anda konfigurasi nanti.

## 🚀 Cara Menggunakan (Workflow Mingguan)

1. **Persiapan:** Masukkan modul PDF, kumpulkan *screenshot* bernomor di dalam `/screenshot-hasil/`, dan tulis `inisiasi.txt` (peta gambar) Anda di workspace Anda.
2. **Panggil AI:** Buka fitur *chat* pada Antigravity di dalam *workspace* Anda. Plugin ini otomatis terdeteksi.
3. **Ketik Perintah Dinamis Anda:**
   > *"/make-laprak tolong buatkan laporan praktikum untuk matkul Jaringan. Section pembahasannya dibagi jadi 2 yaitu Hasil Praktikum (untuk gambar 1-10) dan Hasil Akhir (untuk gambar 11-12). Analisis semua screenshot di folder screenshot-hasil dan cocokkan dengan deskripsi di file inisiasi.txt."*
4. **Interaksi:** AI akan membaca `inisiasi.txt`, mengalokasikan teks untuk gambar yang belum ada, dan bekerja selangkah demi selangkah sesuai aturan di `SKILL.md`.

## ℹ️ Informasi Tambahan
Jika Anda lupa atau ingin mengecek panduan pemakaian dengan cepat, Anda bisa memanggil:
> *"/make-laprak-info"*
AI akan langsung merespons dengan penjelasan fungsionalitas dan instruksi dari plugin ini.

---

## 🗺️ Roadmap & Checklist Pengembangan (Universal AI Support)
Daftar tugas untuk versi mendatang jika ingin membuat repositori ini *100% Universal* dan bisa digunakan di berbagai AI Agent selain Antigravity (seperti Cursor, Claude Code, GitHub Copilot Workspace):

- [ ] **Cross-Platform Adapters (Entry Points):**
  - Buat file `.cursorrules` (untuk Cursor) yang mengarahkan AI membaca `skills/make-laprak/SKILL.md`.
  - Buat file `CLAUDE.md` (untuk Claude Code) dengan instruksi serupa.
  - Buat file `.github/copilot-instructions.md` (untuk GitHub Copilot).
- [ ] **Agnostic Core Prompts:** Memisahkan *prompt* murni dari folder `skills/` ke folder netral seperti `core/` agar bahasanya tidak terikat satu platform saja.
- [ ] **Fallback Script Pencari Jurnal:** Membuat *script* Python/Node (misal `scripts/search_jurnal.py`) sebagai pengganti fitur *Web Search* bagi AI yang tidak punya fitur bawaan pencarian internet.
- [ ] **Integrasi MCP (Model Context Protocol):** Membuat konfigurasi server MCP untuk pencarian jurnal ilmiah agar menjadi kapabilitas *native* yang terstandarisasi di semua platform AI.
- [ ] **Universal Setup Script:** Membuat file instalasi (misal `install.sh` / `install.bat`) yang menanyakan AI apa yang dipakai pengguna, lalu mengatur letak *symlink* atau folder secara otomatis.