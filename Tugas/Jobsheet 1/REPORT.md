# Sistem Operasi

<h4>Nama : Carlos Fadellilah Rama<h4>
<h4>NIM : 254107020064<h4>
<h4>Kelas : TI-1H<h4>

## 1.10 Latihan

### 1.10.1. Latihan Konseptual

#### Latihan 1.1
  Jelaskan 5 fungsi utama sistem operasi dengan contoh konkret dari minimal 2
OS berbeda (Windows, macOS, atau Linux)
1. Manajemen Proses (Process Management)
OS bertanggung jawab mengatur aplikasi mana yang sedang berjalan, memprioritaskannya, dan menghentikannya jika diperlukan. Ini memastikan CPU tidak kewalahan saat menjalankan banyak tugas sekaligus.

Windows: Menggunakan Task Manager untuk memantau aplikasi. Contohnya, saat Chrome "not responding", Anda bisa melakukan End Task.

Linux: Menggunakan perintah top atau htop di terminal. Linux sangat efisien dalam mengelola background processes (daemon) yang berjalan tanpa antarmuka grafis.

2. Manajemen Memori Utama (RAM Management)
OS mengatur alokasi RAM untuk setiap program. Jika RAM penuh, OS akan mengelola pemindahan data ke memori virtual agar sistem tidak macet.

Windows: Menggunakan fitur Superfetch/SysMain yang memuat aplikasi yang sering digunakan ke RAM agar lebih cepat dibuka.

Linux: Memiliki manajemen Swap Space yang sangat fleksibel, di mana pengguna bisa mengatur partisi khusus di disk untuk membantu RAM saat beban kerja sangat tinggi.

3. Manajemen File (File Management)
Fungsi ini mengatur bagaimana data disimpan, diatur dalam folder, diberi izin akses, dan dimanipulasi (salin, hapus, pindah).

Windows: Menggunakan sistem file NTFS. Contoh konkretnya adalah fitur File Explorer dan sistem "drive letters" (C:, D:, dst).

Linux: Menggunakan sistem file seperti Ext4. Berbeda dengan Windows, Linux mengatur semuanya dalam satu pohon hierarki tunggal yang dimulai dari root (/), tanpa drive letters.

4. Manajemen Perangkat Keras (I/O Management)
OS bertindak sebagai mediator antara aplikasi dan perangkat keras seperti printer, mouse, atau kartu grafis melalui bantuan driver.

Windows: Sangat bergantung pada instalasi driver manual atau lewat Windows Update. Contohnya, saat Anda mencolokkan mouse baru, Windows akan otomatis mencari driver di database miliknya.

Linux: Sebagian besar driver sudah terintegrasi langsung di dalam Kernel. Contohnya, hampir semua printer atau webcam bisa langsung digunakan (plug-and-play) tanpa perlu mengunduh driver dari website manufaktur.

5. Keamanan dan Kontrol Akses
OS melindungi data dari pengguna yang tidak berwenang dan memastikan bahwa sebuah program tidak merusak file sistem yang krusial.

Windows: Memiliki fitur User Account Control (UAC) yang memunculkan jendela konfirmasi saat Anda ingin menginstal software baru.

Linux: Menggunakan sistem izin yang sangat ketat (Read, Write, Execute). Contoh konkretnya adalah penggunaan perintah sudo (SuperUser Do) setiap kali ingin melakukan perubahan sistem di terminal.

#### Latihan 1.2
  Kapan sebaiknya menggunakan Windows vs Linux vs macOS? Analisis
berdasarkan use case: gaming, development, server, creative work, dan enterprise
1. Gaming (Pemenang: Windows)
Meskipun Linux dan macOS telah berkembang pesat, Windows tetap menjadi raja yang tak tergoyahkan di dunia gaming.

Windows: Memiliki dukungan DirectX dan library driver GPU paling mutakhir. Hampir semua anti-cheat game kompetitif (seperti Valorant atau CoD) hanya berjalan di Windows.

Linux: Berkat Proton (SteamOS), ribuan game Windows kini bisa jalan di Linux dengan performa luar biasa. Namun, game dengan anti-cheat ketat masih sering bermasalah.

macOS: Sangat terbatas. Meski chip Apple Silicon (M1/M2/M3) sangat bertenaga, library game yang dioptimalkan untuk Mac masih sangat sedikit.

2. Development (Pemenang: Linux & macOS)
Untuk urusan coding, lingkungan yang mirip dengan server (Unix-based) adalah standar industri.

Linux: "Rumah" bagi para pengembang. Sangat efisien untuk manajemen paket (package manager), pengembangan backend, dan Docker. Gratis dan sangat bisa dikustomisasi.

macOS: Standar emas untuk pengembang mobile (Wajib jika ingin membuat aplikasi iOS/Swift) dan web. Menawarkan stabilitas Unix dengan antarmuka yang sangat halus.

Windows: Mengandalkan WSL2 (Windows Subsystem for Linux) yang memungkinkan Anda menjalankan kernel Linux di dalam Windows. Ini adalah jalan tengah terbaik jika Anda butuh Windows tapi ingin gaya kerja Linux.

3. Server (Pemenang: Linux)
Dalam infrastruktur cloud dunia (AWS, Google Cloud, Azure), Linux mendominasi hampir 90% pasar.

Linux: Sangat ringan karena bisa berjalan tanpa antarmuka grafis (Headless). Keamanannya sangat ketat dan tidak memerlukan biaya lisensi.

Windows Server: Digunakan di lingkungan korporat yang bergantung pada ekosistem Microsoft, seperti Active Directory atau database SQL Server.

macOS: Hampir tidak pernah digunakan untuk server skala besar karena batasan lisensi hardware Apple.

4. Creative Work (Pemenang: macOS & Windows)
Pekerjaan kreatif membutuhkan stabilitas warna dan dukungan software profesional.

macOS: Favorit desainer grafis, editor video, dan produser musik. Software seperti Final Cut Pro dan Logic Pro hanya ada di sini. Manajemen warna (color management) Apple adalah yang terbaik di kelasnya.

Windows: Pilihan utama untuk 3D Rendering dan Animasi (Blender, Maya, 3ds Max) karena dukungan GPU NVIDIA yang lebih fleksibel dibanding Mac.

Linux: Mulai digunakan di studio film besar untuk efek visual (VFX), namun software populer seperti Adobe Creative Cloud tidak bisa berjalan di sini.

5. Enterprise / Office (Pemenang: Windows)
Untuk lingkungan kantor dengan ratusan karyawan, manajemen pusat adalah kunci.

Windows: Integrasi Microsoft 365 dan sistem manajemen perangkat keras yang matang membuatnya menjadi standar perkantoran dunia.

macOS: Sering digunakan oleh eksekutif atau startup karena citra premium dan kemudahan manajemen lewat sistem Mobile Device Management (MDM).

Linux: Jarang digunakan di meja kantor biasa karena kurva pembelajaran yang tinggi bagi pengguna awam, kecuali di perusahaan teknologi khusus.

### 1.10.2. Latihan Praktikal

#### Latihan 1.3
Install Ubuntu Server 22.04 LTS di VirtualBox dengan langkah berikut:
1. Download Ubuntu Server ISO dari website resmi

![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](gambar/gambar%201.3.1.png)

2. Create VM baru di VirtualBox (RAM: 2GB, Disk: 25GB)
3. Install dengan automatic partitioning (guided)
5. Buat user account dengan password yang kuat
6. Reboot dan login ke sistem
7. Dokumentasikan proses instalasi dengan screenshot key steps
   
#### Latihan 1.4
Setelah instalasi Ubuntu Server, lakukan tasks berikut:
1. Update package list: sudo apt update
2. Upgrade packages: sudo apt upgrade
3. Install neofetch: sudo apt install neofetch
4. Jalankan neofetch dan screenshot hasilnya
5. Check disk usage dengan df -h
6. Check memory dengan free -h
7. Dokumentasikan output dari setiap command
   
#### Latihan 1.5
Eksplorasi sistem yang baru diinstall:
1. Tampilkan informasi OS: cat /etc/os-release
2. Tampilkan versi kernel: uname -r
3. List partisi: lsblk
4. Check network connectivity: ping -c 4 google.com
5. Install dan jalankan htop untuk melihat resource usage
6. Buat laporan singkat tentang konfigurasi sistem Anda


### 1.10.3. Latihan Refleksi

#### Latihan 1.6
Ceritakan pengalaman Anda dengan sistem operasi:
1. Sistem operasi apa yang Anda gunakan sehari-hari? (Windows, macOS,
Linux, atau lainnya)
2. Berapa lama Anda menggunakan sistem operasi tersebut?
3. Apa yang Anda sukai dari sistem operasi tersebut?
4. Apa tantangan atau masalah yang pernah Anda hadapi?
5. Apakah Anda pernah menggunakan sistem operasi lain? Bandingkan
pengalaman Anda.
6. Setelah mempelajari bab ini, apakah ada sistem operasi lain yang ingin
Anda coba? Mengapa?

