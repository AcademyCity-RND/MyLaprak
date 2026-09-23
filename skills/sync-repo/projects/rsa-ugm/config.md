# Konfigurasi Sinkronisasi Spesifik Proyek: RSA-UGM

Dokumen ini merupakan panduan spesifik (*Project Config*) untuk AI yang menjalankan skill `/sync-repo` pada proyek RSA-UGM. AI wajib membaca, memahami, dan mematuhi seluruh konteks di bawah ini saat menyelaraskan dokumentasi dan repositori.

## 1. Topologi & Pemetaan Repositori
Proyek ini mengadopsi pola "Hulu - Jembatan - Hilir".
- **Hulu (Backend / Source of Truth):** `https://github.com/PMLD-RSA/backend-rsa-ugm`
- **Jembatan (Master Documentation):** `https://github.com/Avin1731/frontend-documentation-rsa-ugm`
- **Hilir 1 (Mobile Staging):** `https://github.com/Avin1731/frontend-mobile-rsa-ugm`
- **Hilir 2 (Web Staging):** `https://github.com/Avin1731/frontend-web-rsa-ugm`

## 2. Instruksi Audit & Triangulasi (Perbandingan 3 Arah)
Setiap kali melakukan sinkronisasi, AI **wajib** membaca seluruh isi repo, *log commit* terbaru, dan membandingkan *requirements*, *main context*, *architecture*, *scope*, *security AAA*, *action*, dan *guideline* antara BE, FE, dan Master Docs.
- **Jangan asal menimpa (overwrite).**
- Berikan laporan perbandingan mendetail: *"Di BE dijelaskan begini, di FE begini, di Docs begini."*
- Jabarkan seluruh informasi yang terlewat atau tidak sinkron meskipun tidak ada perubahan besar, agar pengawas (Lead) yakin tidak ada informasi (*blind spot*) yang tertinggal.

## 3. Konvensi Arsitektur & Teknologi (Tech Stack Rules)
Dalam setiap pembaruan dokumentasi, AI harus mempertahankan aturan arsitektur berikut:
1. **Status Otomasi POMPA = DIBATALKAN.** Sistem ini murni **Monitoring & Alerting**. Dilarang mengusulkan, menyisipkan, atau menyetujui fitur *Pump Control*, *Actuator*, atau *Automation* (Hysteresis rule, Emergency Stop, dll).
2. **Koneksi Realtime (WebSocket):** Frontend wajib menggunakan *library* yang cocok dan selaras dengan Backend (misalnya `partysocket` atau *native* `WebSocket` API) karena BE menggunakan `@fastify/websocket`.
3. **MFA (Multi-Factor Authentication) WAJIB ADA.** Meskipun sistem hanya untuk monitoring, lapisan keamanan *Login* harus tetap menyertakan skema MFA, jangan dihapus dari spesifikasi keamanan (Security-AAA).

## 4. Standar Distribusi ke Repositori Hilir (Staging)
Tujuan akhir dari *skill* ini adalah mendistribusikan *requirements* ke Repositori Staging agar *developer* FE bisa langsung *coding*. Saat meng-update Repo Staging (Hilir), AI harus memastikan ketersediaan file-file berikut:
1. **Pecahan Dokumen API Contract:** AI harus mengambil spesifikasi API dari BE (input, output, response, WebSocket events) dan menjabarkannya ke dalam file `api-contract.md` secara spesifik di dalam folder `web/` dan `mobile/` pada Master Docs.
2. **File `DEV_INSTRUCTIONS.md`:** AI harus membungkus seluruh aturan kerja (termasuk *API Contract*, larangan fitur otomasi, standar *Conventional Commits*) ke dalam file `DEV_INSTRUCTIONS.md` dan menaruhnya di akar (root) direktori Repositori Staging (Web & Mobile). File ini berfungsi sebagai referensi instan bagi *developer* (atau AI lain) agar tidak perlu instruksi *prompt* panjang lebar saat eksekusi *coding*.

---
**Catatan untuk AI:** Konfigurasi ini adalah terjemahan langsung dari jalan pikiran dan *intent* (niat) Lead Developer. Semua aturan di atas adalah **harga mati** untuk iterasi pengembangan RSA-UGM selanjutnya.
