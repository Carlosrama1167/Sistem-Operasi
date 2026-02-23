# Sistem Operasi

<h4>Nama : Carlos Fadellilah Rama<h4>
<h4>NIM : 254107020064<h4>
<h4>Kelas : TI-1H<h4>

## Praktikum 2.1 - identifikasi CPU dan Memori
 #### Langkah-langkah
 1. lscpu
 ![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/praktikum%202.1.1.png)

 2. free -h
 ![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/praktikum%202.1.2.png)
 
 3. sudo dmidecode -t system
 ![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/praktikum%202.1.3.png)

### Latihan 2.1
 1. jumlah CPU(s), core/thread : cpu = 25 | core/tread = 1
 2. total RAM : 1.9Gi
 3. total swap : 2.0Gi
 4. Jelaskan perbedaan RAM vs swap dalam 2–3 kalimat :
 RAM (Random Access Memory) adalah memori utama yang digunakan sistem untuk menyimpan data aktif dengan kecepatan akses yang sangat tinggi, sedangkan swap adalah area pada disk (penyimpanan sekunder) yang digunakan sebagai cadangan ketika RAM sudah penuh. Perbedaan utamanya terletak pada performa, di mana RAM jauh lebih cepat dibandingkan swap karena swap dibatasi oleh kecepatan baca-tulis perangkat penyimpanan.

## Praktikum 2.2 - Indentifikasi Perangkat PCI/USB dan Driver
 1. lspci
    ![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/praktikum%202.2.1.png)
   2. lspci -nnk
    ![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/praktikum%202.2.png)
   3. lspci -nnk | grep -A3 -i ethernet
   ![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/praktikum%202.2.3.png)
   4. lsusb
    ![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/praktikum%202.2.4.png)
   5. lsusb -t
    ![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/praktikum%202.2.5.png)
 ### Latihan 2.2
    Temukan 1 perangkat PCI (misal NIC) dan tuliskan: Vendor:Device ID (angka 
    heksadesimal), nama driver/modul kernel, dan deskripsi singkat fungsinya

   1. Vendor:Device ID: 8086:15b8
   2. Nama Driver/Modul: e1000e
   3. Deskripsi: Kartu jaringan (NIC) dari Intel yang berfungsi untuk menangani koneksi internet melalui kabel LAN.
    ![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/praktikum%202.2.png)

## Praktikum 2.3 — Identifikasi Storage dan Filesystem
   1. lsblk -f
    ![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/praktikum%202.3.1.png)
   2. sudo blkid
    ![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/praktikum%202.3.2.png)
   3. findmnt /
    ![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/praktikum%202.3.3.png)
## Praktikum 2.4 — Melihat Modul Aktif dan Informasinya
   1. uname -r
   ![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/praktikum%202.4.1.png)
   2. lsmod | head
   ![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/praktikum%202.4.2.png)
   3. modinfo loop
   ![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/praktikum%202.4.3.png)
   4. sudo modprobe loop
      lsmod | grep -i loop
      dmesg -T | tail -n 20
      ![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/praktikum%202.4.4.png)
## Praktikum 2.5 — Konfigurasi Auto-load dan Blacklist
   1. echo " loop " | sudo tee / etc / modules - load . d / loop . conf
   2. lsmod | grep -i loop
   
## Praktikum 2.6 — Mengenali Block vs Character Device
   1. ls -l / dev / sda
      ![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/praktikum%202.6.1.png)
   2. ls -l / dev / tty
      ![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/praktikum%202.6.2.png)
   3. lsblk
      ![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/praktikum%202.6.3.png)

 ### Latihan 2.3
    Dari output ls -l, jelaskan perbedaan penanda file untuk block device dan
    character device. (Hint: karakter pertama pada permission string)

   1. Jika karakter pertamanya adalah b, itu adalah Block Device (seperti penyimpanan data).
   2. Jika karakter pertamanya adalah c, itu adalah     Character Device (seperti input keyboard atau output teks).

## Praktikum 2.7 — Melihat Informasi udev
   1. udevadm info -- query = all -- name =/ dev / sda | head -n 30
   ![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/praktikum%202.7.1.png)
   2. sudo udevadm monitor
## Praktikum 2.8 — Membuat Workspace Praktikum
   1. mkdir -p ~/ praktikum - os / week02
      cd ~/ praktikum - os / week02
      pwd
       ![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/praktikum%202.8.1.png)
   2. touch notes . txt data . log config . txt
      ls - lah
       ![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/praktikum%202.8.2.png)
   3. echo " INFO : service started " >> data.log
   4. echo " WARN : disk usage high " >> data . log
      echo " ERROR : failed to connect " >> data . log
      cat data . log
      ![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/praktikum%202.8.3.png)
   5. less data . log
## Praktikum 2.9 — Pencarian Pola dengan grep
   1. grep " ERROR " data . log
   2. grep -i " error " data . log
   3. grep -n " WARN " data . log
      ![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/praktikum%202.9.1.png)
   4. grep -v " INFO " data . log
      ![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/praktikum%202.9.2.png)

 ### Latihan 2.4
    Gunakan grep untuk menampilkan hanya baris yang mengandung INFO atau
    WARN dari data.log. (Hint: gunakan grep -E dengan pola alternatif)
   ![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/praktikum%202.9.3.png)
## Praktikum 2.10 — Substitusi dengan sed (Aman di File Latihan)
   1. cat > config . txt << ’EOF ’
      PORT =8080
      MODE = dev
      SERVICE_NAME = myserver
      EOF
      cat config . txt
      ![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/praktikum%202.10.1.png)
   2. sed ’s/ MODE =dev/ MODE = prod /’ config . txt
      ![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/praktikum%202.10.2.png)
   3. sed -i ’s/ MODE =dev/ MODE = prod /’ config . txt
      cat config . txt
      ![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/praktikum%202.10.3.png)
   4. sed -i ’s/ myserver / node /g’ config . txt
      cat config . txt
      ![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/praktikum%202.10.4.png)
## Praktikum 2.11 — Ekstraksi Kolom dengan awk
   1. df -h
   ![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/praktikum%202.11.1.png)
   2. df -h | awk ’NR ==1 { print $1 , $5 , $6} NR >1 { print $1 ,$5 , $6}’
   ![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/praktikum%202.11.2.png)
   3. df -h | awk ’NR ==1 || ($5+0) > 80 { print $1 , $5 , $6}’
   ![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/praktikum%202.11.3.png)
## Praktikum 2.12 — Melihat Proses dengan ps
   1. ps aux | head
   ![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/praktikum%202.12.1.png)
   2. ps aux | grep -i sshd
   ![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/praktikum%202.12.2.png)
## Praktikum 2.13 — Monitoring Real-time dengan top
   1. top
   ![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/praktikum%202.13.1.png)
## Praktikum 2.14 — Menghentikan Proses dengan kill
   1. sleep 300 &
   2. ps aux | grep -E " sleep 300 " | grep -v grep
   3. kill < PID_ANDA >
   4. ps aux | grep -E " sleep 300 " | grep -v grep
   5. kill -9 < PID_ANDA >
## Praktikum 2.15 — Cek Disk, Load, dan Service
   1. df -h
   2. sudo du -sh /var/* 2>/dev/null | sort -h | tail -n 10
   3. uptime
   4. systemctl --failed
   5. journalctl -xe | tail -n 50
## Praktikum 2.16 — Monitoring Port dan Koneksi (Network Basics)
   1. ip a
   2. ip r
   3. sudo ss -tulpn
 ### Latihan 2.5
    Pilih satu port yang listening dari output ss -tulpn(misal port 22), lalu
    tuliskan service/proses yang membukanya. Jelaskan kegunaan port tersebut
    secara singkat.

## 1.9 Latihan

 ### Latihan 2.A
    Jalankan lspci -nnk. Pilih 1 perangkat PCI dan tuliskan: nama perangkat,
    ID vendor:device, dan kernel driver in use.
 ### Latihan 2.B
    Tentukan device root filesystem dengan findmnt /. Lalu cocokkan dengan
    lsblk -f dan tuliskan tipe filesystem serta UUID-nya.
 ### Latihan 2.C
    Buat file server.log berisi minimal 10 baris dengan variasi kata: INFO,
    WARN, ERROR. Gunakan grep untuk menampilkan hanya baris ERROR.
 ### Latihan 2.D
    Gunakan sed untuk mengganti semua kata server menjadi node pada file
    latihan. Tunjukkan sebelum dan sesudah.
 ### Latihan 2.E
    Gunakan df -h lalu awk untuk menampilkan filesystem yang penggunaan disk
    di atas 70%.
 ### Latihan 2.F
    Jalankan sleep 600 &. Temukan PID-nya dengan ps. Hentikan dengan
    SIGTERM. Jelaskan beda SIGTERM vs SIGKILL.
 ### Latihan 2.G
    Gunakan systemctl –failed. Jika tidak ada yang gagal, pilih satu service
    aktif (misal ssh) dan tampilkan status serta 30 baris log terakhirnya.
