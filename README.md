# 🛡️ Ubuntu Security Hardening: Lynis & Fail2Ban

![Ubuntu](https://img.shields.io/badge/OS-Ubuntu_Server-orange)
![Lynis](https://img.shields.io/badge/Security-Lynis_Audit-blue)
![Fail2Ban](https://img.shields.io/badge/Protection-Fail2Ban-red)

> Studi kasus implementasi keamanan server menggunakan Lynis untuk vulnerability assessment dan Fail2Ban untuk pencegahan intrusi.

## 📋 Dokumentasi Per-Minggu 
-  [Minggu 1](#Minggu_1)  Instalasi Linux (VM) Baseline Audit
![Minggu 1](./Minggu%201/lynis_baseline.png)

- [Minggu 2](#Minggu_2) Konfigurasi User &amp; Permission Management
![Minggu 2](./Minggu%202/)

- [Minggu 3](#Minggu_3)
- [Minggu 4](#Minggu_4)
- [Minggu 5](#Minggu_5)
- [Minggu 6](#Minggu_6)

---

## 🧐 Tentang Proyek
Repository ini mendokumentasikan proses *hardening* pada sistem operasi Ubuntu. Tujuan utamanya adalah:
1. Mengidentifikasi celah keamanan sistem menggunakan **Lynis**.
2. Memitigasi serangan *brute-force* pada SSH menggunakan **Fail2Ban**.

## 💻 Lingkungan Sistem
* **OS:** Ubuntu Server 20.04 LTS (Running on VirtualBox)
* **RAM:** 8GB
* **Tools:**  Lynis v3.0.9, Fail2Ban v0.11

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
