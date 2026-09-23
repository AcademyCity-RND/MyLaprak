# Konfigurasi Proyek: RSA-UGM

## 1. Pemetaan Repositori
- **Hulu (Backend / Source of Truth):** `https://github.com/PMLD-RSA/backend-rsa-ugm`
- **Jembatan (Master Documentation):** `https://github.com/Avin1731/frontend-documentation-rsa-ugm`
- **Hilir 1 (Mobile Staging):** `https://github.com/Avin1731/frontend-mobile-rsa-ugm`
- **Hilir 2 (Web Staging):** `https://github.com/Avin1731/frontend-web-rsa-ugm`

## 2. Aturan Tambahan
- Repositori Hilir dipecah menjadi dua platform (Web dan Mobile). Keduanya merujuk pada Master Documentation yang sama.
- Backend merupakan *source of truth* untuk API dan *database schema*.
- Fokus penyelarasan (Tahap 3): Menghasilkan paket file `README.md`, `requirements-be.md`, dan `DEV_INSTRUCTIONS.md` (atau semacamnya) untuk dikirim ke Hilir 1 dan Hilir 2.
