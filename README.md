# 🛡️ Studi kasus Proyek 3 : Hardening Sistem Linux dan Audit Keamanan

![Ubuntu](https://img.shields.io/badge/OS-Ubuntu_Server-orange)
![Lynis](https://img.shields.io/badge/Security-Lynis_Audit-blue)
![Fail2Ban](https://img.shields.io/badge/Protection-Fail2Ban-red)

## 🛡️ Anggota Tim Kelompok 3
* **2201020130**  Grayesi Silitonga
* **2201020091**  Yohani Natalia Simanullang
* **2201020083**  Winda Aulia Ariyani
* **2201020035**  Enjelita Br Ginting

## 📋 Dokumentasi Setiap Minggu 
-  [Minggu 1](#Minggu_1)  **Instalasi Linux (VM) Baseline Audit**

```javascript
# Clone repository Lynis
git clone https://github.com/CISOfy/lynis

# Masuk ke direktori
cd lynis && chmod +x lynis

# Jalankan audit sistem
sudo ./lynis audit system
```
-  Perintah untuk menginstal dan menjalankan audit sistem
![Minggu 1](./Minggu%201/lynis_baseline.png)

- [Minggu 2](#Minggu_2) **Konfigurasi User &amp; Permission Management**
- Cek Konfigurasi
  
```javascript
# Instal UFW (jika belum ada)
sudo apt install ufw

# Atur kebijakan default (Tolak masuk, Izinkan keluar)
sudo ufw default deny incoming
sudo ufw default allow outgoing

# Izinkan akses SSH pada Port Custom (2222)
# Catatan: Sesuaikan dengan port SSH yang akan digunakan
sudo ufw allow 2222/tcp

# Aktifkan Firewall
sudo ufw enable

# Cek status aturan
sudo ufw status verbose
```
![Minggu 2](./Minggu%202/atur_konfigurasi.jpg)

- [Minggu 3](#Minggu_3) **Konfigurasi Firewall (UFW / iptables)**
- Cek SSH

```javascript
sudo nano /etc/ssh/sshd_config

//cuplikan code
Port 2222                 # Ubah port default (22) ke 2222 (Security by Obscurity)
PermitRootLogin no        # Matikan login root
PubkeyAuthentication yes  # Wajibkan penggunaan SSH Key
PasswordAuthentication no # (Opsional) Matikan login password jika SSH Key sudah aktif

sudo systemctl restart ssh

```

![Minggu 3](./Minggu%203/mengaktifkan_ufw_dan_mengecek_status_rule.png)
![Minggu 3](./Minggu%203/atur_policy_default_dan_membuka_port_2222_untuk_ssh.png)

- [Minggu 4](#Minggu_4) **Hardening SSH + fail2ban**
  
```javascript
# Instal Fail2Ban
sudo apt update && sudo apt install fail2ban -y

# Salin konfigurasi default agar aman saat update
sudo cp /etc/fail2ban/jail.conf /etc/fail2ban/jail.local

# Edit konfigurasi jail.local
sudo nano /etc/fail2ban/jail.local

//TOML
[sshd]
enabled = true
port    = 2222            # Wajib sesuaikan dengan port SSH yang baru
logpath = %(sshd_log)s
backend = %(sshd_backend)s
maxretry = 3              # Blokir setelah 3x gagal login
bantime = 3600            # Blokir selama 1 jam

sudo systemctl enable fail2ban
sudo systemctl start fail2ban

```

![Minggu 4](./Minggu%204/konfigurasi_ssh_dan_statusnya.png)
![Minggu 4](./Minggu%204/instal_faillban.png)

- [Minggu 5](#Minggu_5) **Audit ulang &amp; scoring keamanan (Lynis)**

```javascript
# Cek status Fail2Ban (pastikan Jail SSH aktif)
sudo fail2ban-client status sshd

# Jalankan audit ulang dengan Lynis
cd lynis
sudo ./lynis audit system

```
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


