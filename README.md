# 🛡️ Ubuntu Security Hardening: Lynis & Fail2Ban

![Ubuntu](https://img.shields.io/badge/OS-Ubuntu_Server-orange)
![Lynis](https://img.shields.io/badge/Security-Lynis_Audit-blue)
![Fail2Ban](https://img.shields.io/badge/Protection-Fail2Ban-red)

> Studi kasus Proyek 3: Hardening Sistem Linux dan Audit Keamanan

## 🛡️ Anggota Tim

**Nama Tim:** Kelompok 3

Daftar Kontributor:
* **[Grayesi Silitonga]** - (NIM: 2201020130)
* **[Yohani Natalia Simanullang]** - (NIM: 2201020092)
* **[Winda Aulia Ariyani]** - (NIM: 2201020083)
* **[Enjelita Br Ginting]** - (NIM: 2201020035)

## 📋 Dokumentasi Per-Minggu 
-  [Minggu 1](#Minggu_1)  Instalasi Linux (VM) Baseline Audit
![Minggu 1](./Minggu%201/lynis_baseline.png)

- [Minggu 2](#Minggu_2) Konfigurasi User &amp; Permission Management

- [Minggu 3](#Minggu_3) Konfigurasi Firewall (UFW / iptables)
  
- [Minggu 4](#Minggu_4) Hardening SSH + fail2ban
  
- [Minggu 5](#Minggu_5) Audit ulang &amp; scoring keamanan (Lynis)
  
- [Minggu 6](#Minggu_6) Dokumentasi &amp; presentasi

---

## 🧐 Tentang Proyek
Repository ini mendokumentasikan proses *hardening* pada sistem operasi Ubuntu. Tujuan utamanya adalah:
1. Meningkatkan keamanan OS dan mengaudit kerentanan konfigurasi.

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
