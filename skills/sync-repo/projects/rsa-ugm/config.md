# Konfigurasi Sinkronisasi Spesifik Proyek: RSA-UGM

Dokumen ini merupakan Panduan Prosedur Operasional Standar (SOP) untuk AI setiap kali menjalankan perintah `/sync-repo` pada iterasi proyek RSA-UGM ke depannya.

## 1. Pemetaan Repositori (Topologi)
- **Hulu (Source of Truth):** `https://github.com/PMLD-RSA/backend-rsa-ugm` (Backend)
- **Jembatan (Master Docs):** `https://github.com/Avin1731/frontend-documentation-rsa-ugm`
- **Hilir 1 (Mobile Staging):** `https://github.com/Avin1731/frontend-mobile-rsa-ugm`
- **Hilir 2 (Web Staging):** `https://github.com/Avin1731/frontend-web-rsa-ugm`

## 2. Fase 1: Discovery & Audit (Membaca & Membandingkan)
Setiap kali siklus sync dimulai (karena ada *update* dari tim BE/FE):
1. **Wajib Gali Mendalam:** AI tidak boleh hanya membaca `README`. Gali spesifikasi teknis asli di repo Hulu (seperti file `openapi.yaml`, file skema database, atau *routes*) untuk mendapatkan realita API Contract yang 100% akurat (termasuk REST & WebSocket).
2. **Audit 3 Arah:** Bandingkan *source code* dan *log commit* terbaru dari BE (Hulu) dengan Master Docs (Jembatan) dan Staging (Hilir). Periksa bagian *Architecture, Scope, Security AAA, Action, Guideline,* dan *Requirements*.
3. **Laporan Transparan:** Buat laporan detail yang menjabarkan *semua* temuan (apa yang baru di BE, apa yang tertinggal di FE/Docs, atau fitur apa yang terhapus). JANGAN ASAL MENIMPA (OVERWRITE).

## 3. Fase 2: Brainstorming & Resolusi Konflik (Menunggu Arahan Lead)
- Setelah memberikan laporan Audit, **AI WAJIB BERHENTI DAN MENUNGGU**.
- Lead Developer (User) akan memberikan instruksi resolusi (misal: "Selaraskan fitur X dengan BE", "Tetap pertahankan fitur Y di FE", atau "Tambahkan panduan Z").
- AI dilarang berasumsi atau mengubah dokumen *Master Docs* sebelum mendapatkan **ACC** atau arahan dari Lead.

## 4. Fase 3: Eksekusi Master Docs (Penyelarasan Jembatan)
Setelah mendapat persetujuan:
1. Update seluruh file di repo Master Docs (`Scope.md`, `Security-AAA.md`, dll) sesuai kesepakatan resolusi.
2. Jika ada *update API/Event baru* dari Backend, ekstrak data tersebut dan perbarui file `api-contract.md` secara mendetail (meliputi endpoint, payload Zod/schema, dan format response) ke folder dokumentasi `web/` dan `mobile/`.

## 5. Fase 4: Distribusi ke Hilir (Staging)
Tujuan akhir siklus ini adalah menyiapkan repo Staging agar *developer/AI* bisa langsung mengoding berdasarkan *update* terbaru:
1. **Copy API Contract:** Letakkan/perbarui file `api-contract.md` secara fisik di *root directory* repo Web Staging dan Mobile Staging.
2. **Generate DEV_INSTRUCTIONS.md:** Buatkan instruksi *Roadmap Scaffolding* yang logis dan *actionable* berdasarkan realita dokumen terbaru. Jangan hanya memberi daftar aturan; berikan langkah-langkah kerja (mulai dari membaca requirements, menyambung API, hingga aturan spesifik iterasi saat ini).

---
*Konfigurasi ini memastikan bahwa kapan pun tim Backend melakukan perombakan besar, AI dapat secara dinamis mengaudit, melaporkan, dan mengeksekusi sinkronisasi dengan standar presisi yang sama seperti iterasi pertama, tanpa perlu di-prompt panjang lebar dari awal.*
