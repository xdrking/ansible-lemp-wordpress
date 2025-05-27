# 🚀 Ansible LEMP + WordPress Installer

## 🌐 Language / Dil

[🇬🇧 English](#english-version) | [🇹🇷 Türkçe](#türkçe-versiyon)

---

## 📘 English Version

This Ansible playbook automates the setup of a full **LEMP stack (Linux, Nginx, MariaDB, PHP)** with **WordPress** on your target server.

---

## 📋 Requirements

* A target Linux server (Ubuntu 22.04/24.04 recommended)
* **Ansible** installed on the control machine
* SSH access to the target server
* Python 3.x on the control machine
* Environment variables set in a `.env` file (see Configuration)

---

## 📦 Installation

1. Clone the repository:

```bash
git clone https://github.com/your-username/ansible-lemp-wordpress.git
cd ansible-lemp-wordpress
```

2. Install required Python packages (if not already):

```bash
pip install requests urllib3
```

3. Install required Ansible collections:

```bash
ansible-galaxy collection install community.general
```

---

## ⚙️ Configuration

1. Copy `.env.sample` to `.env`:

```bash
cp .env.sample .env
```

2. Edit the `.env` file with your server and WordPress credentials:

```bash
DB_NAME=wordpress
DB_USER=wpuser
DB_PASS=wppass
WP_DIR=/var/www/htmls
```

3. Export the variables before running:

```bash
export $(grep -v '^#' .env | xargs)
```

---

## 🖥️ Inventory

Make sure your `inventory` file includes your target server:

```ini
[webservers]
your.webserver.ip ansible_user=root ansible_ssh_pass=your_ssh_password
```

---

## 🚀 Usage

To install LEMP + WordPress:

```bash
ansible-playbook -i inventory lemp_wordpress.yml
```

By default, this playbook sets up:

* Nginx
* MariaDB
* PHP
* WordPress (latest)

You can customize the settings in `.env` as needed.

---

## 📁 Project Structure

```bash
ansible-lemp-wordpress/
├── .env.sample          # Sample environment variables
├── inventory            # Ansible inventory file
├── lemp_wordpress.yml   # Main Ansible playbook
├── README.md            # Project documentation
```

---

## 🛡️ Notes

* Do **not** commit your `.env` file to version control.
* This playbook assumes you are running it from a control machine (not on the target).
* Adjust PHP and WordPress configurations by editing the playbook.

---

## 🤝 Contributing

Fork this repository, make your changes, and open a pull request. Contributions are welcome!

---

## 📗 Türkçe Versiyon

# 🚀 Ansible LEMP + WordPress Kurucu

Bu Ansible playbook'u, hedef sunucunuza tam bir **LEMP yığını (Linux, Nginx, MariaDB, PHP)** ve **WordPress** kurulumunu otomatikleştirir.

---

## 📋 Gereksinimler

* Hedefte bir Linux sunucusu (Ubuntu 22.04/24.04 önerilir)
* Kontrol makinesinde **Ansible** yüklü olmalı
* Hedef sunucuya SSH erişimi
* Kontrol makinesinde Python 3.x
* Ortam değişkenlerini içeren `.env` dosyası (bkz: Yapılandırma)

---

## 📦 Kurulum

1. Repoyu klonlayın:

```bash
git clone https://github.com/your-username/ansible-lemp-wordpress.git
cd ansible-lemp-wordpress
```

2. Python bağımlılıklarını yükleyin:

```bash
pip install requests urllib3
```

3. Gerekli Ansible collection'ı yükleyin:

```bash
ansible-galaxy collection install community.general
```

---

## ⚙️ Yapılandırma

1. `.env.sample` dosyasını `.env` olarak kopyalayın:

```bash
cp .env.sample .env
```

2. `.env` dosyasını aşağıdaki bilgilerle düzenleyin:

```bash
DB_NAME=wordpress
DB_USER=wpuser
DB_PASS=wppass
WP_DIR=/var/www/html
```

3. Değişkenleri export edin:

```bash
export $(grep -v '^#' .env | xargs)
```

---

## 🖥️ Envanter

`inventory` dosyasınızı şu şekilde düzenleyin:

```ini
[webservers]
your.webserver.ip ansible_user=root ansible_ssh_pass=your_ssh_password
```

---

## 🚀 Kullanım

LEMP + WordPress kurmak için:

```bash
ansible-playbook -i inventory lemp_wordpress.yml
```

Bu playbook varsayılan olarak şunları kurar:

* Nginx
* MariaDB
* PHP
* WordPress (son sürüm)

Ayarları `.env` dosyasından düzenleyebilirsiniz.

---

## 📁 Proje Yapısı

```bash
ansible-lemp-wordpress/
├── .env.sample          # Örnek ortam değişkenleri
├── inventory            # Ansible envanter dosyası
├── lemp_wordpress.yml   # Ana Ansible playbook'u
├── README.md            # Proje dokümanı
```

---

## 🛡️ Notlar

* `.env` dosyasını kesinlikle versiyon kontrol sistemine commit etmeyin.
* Bu playbook kontrol makinesinden çalıştırılmak ücün tasarlanmıştır.
* PHP ya da WordPress ayarlarını playbook'tan düzenleyebilirsiniz.

---

## 🤝 Katkı

Projeye katkı sağlamak isterseniz, repoyu forklayıp pull request gönderebilirsiniz! ❤️
