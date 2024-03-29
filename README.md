# MONITORING SERVICE (SAWANGAN)
Monitoring virtual machine menggunakan Node Exporter, Prometheus dan Grafana
![image](https://github.com/eprilian/monitoring-system/assets/57064161/60d970f3-7eb4-426c-80ce-144c8d444268)


Pada project ini, yang saya gunakan adalah:
- Ubuntu Server 22.04 LTS
- SSH Server
- Docker
- Node Exporter
- Prometheus
- Grafana

![image](https://brandslogos.com/wp-content/uploads/images/large/ubuntu-logo.png)
![image](https://brandslogos.com/wp-content/uploads/images/large/docker-logo-1.png)
![image](https://github.com/eprilian/monitoring-system/assets/57064161/14005cfd-6a9c-43e1-985d-c77e117609a0)
![image](https://miro.medium.com/v2/resize:fit:1400/1*4M4OghuybPhjRsLxhrNsGA.png)

Tujuan dari final project ini adalah membuat sebuah sistem monitoring yang mampu untuk memonitoring kinerja sebuah virtual machine atau baremetal
, mula dari kinerja hardware , untilitas network serta uptimenya.

# LANGKAH KONFIGURASI DOCKER PADA UBUNTU 22.04

Pertama yang saya lakukan adalah menginstall Ubuntu 22.04 Server LTS, pada Software Virtualisasi seperti VirtualBox dan VMware Workstation. Setelah 
Ubuntu terpasang, selanjutnya adalah melakukan update package dari repositori dengan perintah:
- apt update && apt upgrade -y

Setelah proses update selesai, install Docker menggunakan scrip install berikut:
https://get.docker.com/

Lakukan download dengan menggunakan curl, apabila belum terinstall maka install dengan menggunakan perintah dan lanjutkan proses download script install dockernya
- apt install curl 
- curl -fsSL https://get.docker.com -o get-docker.sh

Lalu jalankan script tadi dengan perintah berikut, dan tunggu proses installasi hingga selesai
- sh ./get-docker.sh

Setelah docker terinstall pada Ubuntu, selanjutnya adalah melakukan konfigurasi Node Exporter, Prometheus serta Grafana

# LANGKAH KONFIGURASI NODE EXPORTER DI UBUNTU 22.04
Untuk langkah langkah - langkah konfigurasi node exporter pada Ubuntu, dapat dilihat pada link berikut:
https://docs.google.com/document/d/1Ly9XL__PGCQof6Hn-sBCnjCgMosF7i6bYmb070s2M8M/edit?usp=sharing


# LANGKAH KONFIGURASI PROMETHEUS DAN GRAFANA DASHBOARD PADA UBUNTU 22.04
Langkah dan konfigurasi Prometheus dan Grafana dapat dilihat pada link berikut:
https://docs.google.com/document/d/1T_DAHmvpCBJMEBenIKXKmBj5r7wStknPOxubX0jpq80/edit?usp=sharing


# SETUP DASHBOARD MONITORING
Untuk setup dashboard monitoring pada Grafana dapat di lihat pada link di bawah:
https://docs.google.com/document/d/1vzMAUPl3qRoiqxyIZH4qPUl200Ti009Vsf5Yp7E55Ik/edit?usp=sharing


# Konfigurasi Tunnel dengan Cloudflare Tunnel agar dapat di akses dari luar (opsional)
Konfigurasi ini bertujuan untuk membuat Grafana (Monitoring Dashboard) dapat diakses dari luar dengan 
menggunakan bantuan dari cloudflare tunnel. Konfigurasinya dapat dilihat pada link di bawah:
https://docs.google.com/document/d/1L5xBk1A1VIlkqnVrzxJvPot600xB6k86ixTlhnV3PBg/edit?usp=sharing

# Install Cockpit Web UI Control Panel (opsional)
Cockpit digunakan untuk mempermudah dalam melakukan management vm kita lewat web browser. Dengan Cockpit,
kita dapat manage vm dengan lebih mudah. Untuk lebih detail, dapat mengakses link dari Cockpit Project di
https://cockpit-project.org/

Install Cockpit pada Ubuntu
- apt update
- apt install cockpit
- systemctl enable cockpit
- systemctl start cockpit

Setelah proses install selesai dan tidak ada error, dapat dicoba dengan akses <ip-server>:9090
Berikut adalah contoh dahboard login dari cockpit yang telah saya tunnel dengan CLoudflare
![image](https://github.com/eprilian/monitoring-system/assets/57064161/f6428272-d072-4a90-b249-65ef315ca536)
