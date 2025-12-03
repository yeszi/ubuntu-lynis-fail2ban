# 🛡️ Ubuntu Security Hardening: Lynis & Fail2Ban

![Ubuntu](https://img.shields.io/badge/OS-Ubuntu_Server-orange)
![Lynis](https://img.shields.io/badge/Security-Lynis_Audit-blue)
![Fail2Ban](https://img.shields.io/badge/Protection-Fail2Ban-red)

> **Studi kasus Proyek 3**: Hardening Sistem Linux dan Audit Keamanan

## 🛡️ Anggota Tim
**Nama Tim** Kelompok 3 :
* **Grayesi Silitonga** - 2201020130
* **Yohani Natalia.S** - 2201020091
* **Winda Aulia Ariyani** - 2201020083
* **Enjelita Br Ginting** - 2201020035

## 📋 Dokumentasi Per-Minggu 
-  [Minggu 1](#Minggu_1)  Instalasi Linux (VM) Baseline Audit
![Minggu 1](./Minggu%201/lynis_baseline.png)

- [Minggu 2](#Minggu_2) Konfigurasi User &amp; Permission Management
![Minggu 2](./Minggu%202/atur_konfigurasi.jpg)

- [Minggu 3](#Minggu_3) Konfigurasi Firewall (UFW / iptables)
![Minggu 3](./Minggu%203/mengaktifkan_ufw_dan_mengecek_status_rule.png)
![Minggu 3](./Minggu%203/atur_policy_default_dan_membuka_port_2222_untuk_ssh.png)

- [Minggu 4](#Minggu_4) Hardening SSH + fail2ban
  ![Minggu 4](./Minggu%204/konfigurasi_ssh_dan_statusnya.png)
  ![Minggu 4](./Minggu%204/instal_faillban.png)

- [Minggu 5](#Minggu_5) Audit ulang &amp; scoring keamanan (Lynis)
![Minggu 5](./Minggu%205/audit_lynis.png)
![Minggu 5](./Minggu%205/setelah_hardening.jpg)

---

## 🧐 Tujuan Proyek
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
