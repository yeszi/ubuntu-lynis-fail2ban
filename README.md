# 🛡️ Ubuntu Security Hardening: Lynis & Fail2Ban

![Ubuntu](https://img.shields.io/badge/OS-Ubuntu_Server-orange)
![Lynis](https://img.shields.io/badge/Security-Lynis_Audit-blue)
![Fail2Ban](https://img.shields.io/badge/Protection-Fail2Ban-red)

> Studi kasus implementasi keamanan server menggunakan Lynis untuk vulnerability assessment dan Fail2Ban untuk pencegahan intrusi.

## 📋 Daftar Isi
- [Tentang Proyek](#tentang-proyek)
- [Lingkungan Sistem](#lingkungan-sistem)
- [Instalasi & Konfigurasi](#instalasi--konfigurasi)
- [Hasil Audit (Lynis)](#hasil-audit-lynis)
- [Pengujian Keamanan (Fail2Ban)](#pengujian-keamanan-fail2ban)
- [Kesimpulan](#kesimpulan)

---

## 🧐 Tentang Proyek
Repository ini mendokumentasikan proses *hardening* pada sistem operasi Ubuntu. Tujuan utamanya adalah:
1. Mengidentifikasi celah keamanan sistem menggunakan **Lynis**.
2. Memitigasi serangan *brute-force* pada SSH menggunakan **Fail2Ban**.

## 💻 Lingkungan Sistem
* **OS:** Ubuntu Server 20.04 LTS (Running on VirtualBox)
* **RAM:** 2GB
* **Tools:** Lynis v3.x, Fail2Ban v0.11

---

## ⚙️ Instalasi & Konfigurasi

### 1. Setup Lynis
Perintah untuk menginstal dan menjalankan audit sistem:

```bash
# Clone repository Lynis
git clone https://github.com/CISOfy/lynis

# Masuk ke direktori
cd lynis && chmod +x lynis

# Jalankan audit sistem
sudo ./lynis audit system
