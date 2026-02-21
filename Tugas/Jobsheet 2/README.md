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

 ### Latihan 2.2
    Temukan 1 perangkat PCI (misal NIC) dan tuliskan: Vendor:Device ID (angka 
    heksadesimal), nama driver/modul kernel, dan deskripsi singkat fungsinya

## Praktikum 2.3 — Identifikasi Storage dan Filesystem

## Praktikum 2.4 — Melihat Modul Aktif dan Informasinya

## Praktikum 2.5 — Konfigurasi Auto-load dan Blacklist

## Praktikum 2.6 — Mengenali Block vs Character Device

 ### Latihan 2.3
    Dari output ls -l, jelaskan perbedaan penanda file untuk block device dan
    character device. (Hint: karakter pertama pada permission string)

## Praktikum 2.7 — Melihat Informasi udev

## Praktikum 2.8 — Membuat Workspace Praktikum

## Praktikum 2.9 — Pencarian Pola dengan grep

 ### Latihan 2.4
    Gunakan grep untuk menampilkan hanya baris yang mengandung INFO atau
    WARN dari data.log. (Hint: gunakan grep -E dengan pola alternatif)

## Praktikum 2.10 — Substitusi dengan sed (Aman di File Latihan)

## Praktikum 2.11 — Ekstraksi Kolom dengan awk

## Praktikum 2.12 — Melihat Proses dengan ps

## Praktikum 2.13 — Monitoring Real-time dengan top

## Praktikum 2.14 — Menghentikan Proses dengan kill

## Praktikum 2.15 — Cek Disk, Load, dan Service

## Praktikum 2.16 — Monitoring Port dan Koneksi (Network Basics)

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
