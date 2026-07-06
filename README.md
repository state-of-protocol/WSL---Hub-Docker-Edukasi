# 🐳 WSL & Docker DevNode: Hub Edukasi & Pengurusan Sistem

[![GitHub Pages Deployment](https://img.shields.io/badge/GitHub--Pages-Live%20Deployment-emerald?style=for-the-badge&logo=github)](https://state-of-protocol.github.io/WSL---Hub-Docker-Edukasi/)
[![Environment](https://img.shields.io/badge/Environment-WSL2%20%7C%20Ubuntu-blue?style=for-the-badge&logo=linux)](https://learn.microsoft.com/en-us/windows/wsl/)
[![Platform](https://img.shields.io/badge/Platform-Docker%20Engine%20%28Native%29-cyan?style=for-the-badge&logo=docker)](https://www.docker.com/)
[![Shell](https://img.shields.io/badge/Shell-PowerShell%207-purple?style=for-the-badge&logo=powershell)](https://github.com/PowerShell/PowerShell)

Selamat datang ke **WSL & Docker DevNode** — Sebuah hab dokumentasi interaktif, modular, dan bertaraf enterprise yang dibina khusus untuk menyediakan persekitaran pembangunan (*development environment*) yang ringan, pantas, dan dioptimumkan sepenuhnya pada stesen kerja **Aiman@RafeeHP**.

Projek ini berfungsi sebagai rujukan harian terpantas untuk menguruskan **Windows Subsystem for Linux (WSL2)** dan **Docker Engine secara natif**, tanpa bergantung kepada aplikasi berat seperti Windows Docker Desktop.

---

## 🎯 Objektif & Falsafah Reka Bentuk

Dokumentasi ini dibangunkan berteraskan tiga (3) prinsip utama:
1. **Kejelasan Pendidikan (Clarity of Education):** Setiap arahan dipisahkan mengikut persekitaran eksekusi yang jelas (<span style="color:#a855f7">**PowerShell**</span> vs <span style="color:#10b981">**Ubuntu Terminal**</span>) bagi mengelakkan kekeliruan sintaks.
2. **Kecekapan Storan & RAM:** Memaksimumkan keupayaan memori hos dengan teknik penutupan sesi (*shutdown clean*) dan pembersihan sisa cache NVMe secara agresif.
3. **Aksesibiliti Responsif (Mobile-First Architecture):** Antara muka dokumentasi yang dibina menggunakan Tailwind CSS v4 kini dilengkapi dengan menu navigasi melintang (*horizontal scrollable rows*) untuk paparan optimum pada skrin telefon pintar anda.

---

## 🗂️ Peta Jalan & Seni Bina Dokumentasi (Struktur Modular)

Sistem rujukan ini dipecahkan kepada modul-modul khusus bagi memandu aliran kerja anda secara bertingkat:

```yaml
📦 Edukasi-WSL-Hub-Docker
 ├── 📄 index.html          # 0. Proses Mula (Penyediaan PowerShell 7 Admin)
 ├── 📄 wsl.html            # 1. Pengurusan WSL2 (Kawalan Sesi & Kitaran RAM)
 ├── 📄 docker-setup.html   # 2. Setup Docker (Pemasangan Daemon Natif pada Linux)
 ├── 📄 docker-manage.html  # 3. Urus Container (Rangkaian, Port Forwarding & Volum)
 ├── 📄 docker-cleanup.html # 4. Pembersihan Bersih (Nuke Sisa Pepejal NVMe m.2)
 ├── 📄 problems.html       # 5. Masalah Lazim & Solusi (Diagnosis Ralat & Isu Port)
 ├── 📄 qa.html             # 6. Soalan & Jawapan (Teori Kontena & Pemetaan Memori)
 └── 📄 quick_reference.html# ⚡ Rujukan Pantas (All-in-One Cheat Sheet Hub)
💻 Aliran Kerja Utama & Sintaks Harian (Quick Reference)
🧩 0. Fasa Permulaan & Semakan Status
Sebelum meluncurkan subsistem, pastikan integriti virtualisasi Windows berada dalam keadaan aktif melalui PowerShell 7 (Run as Administrator):

PowerShell
# Semak status semasa integrasi WSL & versi kernel
wsl --status

# Masuk ke dalam pengedaran (distro) Ubuntu sasaran
wsl -d Ubuntu
🧠 1. Optimasi Memori (Pembersihan RAM Hos)
Sesi Linux yang terbiar lama boleh memakan cache RAM Windows hos. Lakukan rutin penutupan total apabila selesai sesi pengekodan:

PowerShell
# Keluar daripada sesi shell Ubuntu
exit

# Matikan seluruh subsistem WSL2 serta-merta untuk membebaskan RAM
wsl --shutdown
🐳 2. Pengendalian Servis Docker (Tanpa Docker Desktop)
Oleh kerana enjin Docker berjalan secara natif di dalam Ubuntu, servis latar belakang perlu diuruskan menggunakan pengurus sistem init:

Bash
# Hidupkan daemon perkhidmatan Docker Engine
sudo service docker start

# Semak status kesihatan daemon Docker
sudo service docker status
🧹 3. Operasi Pembersihan Agresif (Disyorkan)
Bagi memastikan pemacu NVMe m.2 anda tidak dipenuhi imej terbiar (dangling images) dan volum terbuang:

Bash
# Padam keseluruhan kontena, imej, rangkaian, dan volum yang tidak aktif
docker system prune -a --volumes -f
🚀 Pembangunan, Penyepaduan Berterusan & Deployment (CI/CD)
Repository ini menggunakan automasi GitHub Actions menerusi fail konfigurasi pages-build-deployment untuk mengkompilasi komponen HTML dan meluncurkannya terus ke halaman penyiaran GitHub Pages.

🛠️ Pengurusan Ralat Paip Talian (Pipeline Troubleshooting)
Sekiranya binaan (build) gagal disebabkan gangguan pelayan atau isyarat pusing balik (deployment failed):

Kaedah UI: Pergi ke tab Actions di halaman repository ➡️ Pilih larian aliran kerja terkini yang gagal ➡️ Klik butang Re-run jobs di penjuru kanan atas.

Kaedah Trigger Git (Empty Commit): Cetuskan semula binaan baharu secara paksa melalui terminal dengan menghantar komit kosong:

Bash
git commit --allow-empty -m "Cetus semula talian paip GitHub Pages"
git push origin main
🔖 Topik & Tag Rujukan
#education #development #coding #server-dock #wsl2 #ubuntu #powershell-7 #docker-engine #ci-cd #github-pages #sysadmin #devops-learning

📝 Nota Penyelenggaraan Sistem: Dokumentasi ini dikemas kini secara berkala dan disesuaikan mengikut evolusi perkakasan serta seni bina sistem state-of-protocol
