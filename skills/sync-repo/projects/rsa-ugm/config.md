# Konfigurasi Proyek: RSA-UGM

## 1. Pemetaan Repositori
- **Hulu (Backend / Source of Truth):** `https://github.com/PMLD-RSA/backend-rsa-ugm`
- **Jembatan (Master Documentation):** `https://github.com/Avin1731/frontend-documentation-rsa-ugm`
- **Hilir 1 (Mobile Staging):** `https://github.com/Avin1731/frontend-mobile-rsa-ugm`
- **Hilir 2 (Web Staging):** `https://github.com/Avin1731/frontend-web-rsa-ugm`

## 2. Aturan & Batasan Khusus (Rules)
- **Otomasi Dibatalkan:** Proyek ini 100% murni untuk *Monitoring & Alerting*. Tidak boleh ada elemen UI atau dokumentasi yang membahas *Pump Control*, *Actuator*, atau *Automation*.
- **Otentikasi:** Tidak menggunakan *MFA (Multi-Factor Authentication)*. Otorisasi Frontend (Mobile & Web) hanya berdasarkan *Role-Based Access Control (RBAC)*.
- **Tech Stack Komunikasi:** Menggunakan `WebSocket` (contoh: `partysocket`) untuk menangkap data *real-time* dari BE.
- **Fokus Sinkronisasi:** Menyebarkan format *API Contract* dan *Conventional Commits Guideline* ke repo Hilir dalam bentuk file `DEV_INSTRUCTIONS.md`.
