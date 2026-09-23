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
- `skills/make-laprak/matkul/`: Folder berisi spesifikasi atau aturan per mata kuliah.
- `skills/make-laprak/template-general/`: Folder berisi *template* laporan kosong yang dapat Anda konfigurasi nanti.

## 🚀 Cara Menggunakan (Workflow Mingguan)

1. **Persiapan:** Masukkan modul PDF, kumpulkan *screenshot* bernomor di dalam `/screenshot-hasil/`, dan tulis `inisiasi.txt` (peta gambar) Anda di workspace Anda.
2. **Panggil AI:** Buka fitur *chat* pada Antigravity di dalam *workspace* Anda. Plugin ini otomatis terdeteksi.
3. **Ketik Perintah Dinamis Anda:**
   > *"Gunakan skill laporan-praktikum untuk membuatkan laporan. Sectionnya akan jadi 2 yaitu Hasil Praktikum dan Hasil Akhir. Lihat seluruh png yang ada di folder ini saja..."*
4. **Interaksi:** AI akan membaca `inisiasi.txt`, mengalokasikan teks untuk gambar yang belum ada, dan bekerja selangkah demi selangkah sesuai aturan di `SKILL.md`.