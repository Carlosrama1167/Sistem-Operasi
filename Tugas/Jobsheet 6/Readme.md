# Sistem Operasi

<h4>Nama : Carlos Fadellilah Rama<h4>
<h4>NIM : 254107020064<h4>
<h4>Kelas : TI-1H<h4>

## Tugas Pendahuluan

### Praktikum 6.1 — Melihat Proses dan Thread

Latihan 6.1
Jalankan ps aux dan amati outputnya:
1. Berapa total proses yang berjalan? Proses apa yang memiliki PID
terkecil?
- PID terkecil biasanya adalah 1
![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/latihan%206.1.1.png)
2. Jalankan pstree -p dan temukan proses bash Anda. Proses apa yang
menjadi induk (PPID) dari bash tersebut? login
![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/latihan%206.1.2.png)
3. Bandingkan output ps aux dan ps aux -L. Apa perbedaan yang Anda
lihat?
- ps aux hanya menampilkan proses , sedangkan ps aux -L menampilkan detail thread di dalam setiap proses yang ditandai dengan kolom LWP (Light-Weight Process ID)
![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/latihan%206.1.3.png)
![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/latihan%206.1.1.png)

### Praktikum 6.2 — Mengamati Siklus Hidup Proses

Latihan 6.2
1. Jalankan sleep 120 & dan amati kolom STAT pada ps aux. Kondisi
apa yang ditampilkan? Mengapa proses sleep berada di kondisi tersebut?
- Kondisinya adalah S (Sleeping). Proses ini menunggu waktu habis (event) dan tidak membutuhkan CPU saat sedang menunggu.
![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/latihan%206.2.1.png)
2. Jalankan beberapa perintah yang berhasil dan yang gagal, lalu catat exit
code masing-masing. Pola apa yang Anda temukan? pol 0
![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/latihan%206.2.2.png)

### Praktikum 6.3 — Mengatur Prioritas Proses

Latihan 6.3
1. Jalankan nice -n 5 sleep 200 & dan verifikasi nilai NI-nya dengan
ps.
![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/latihan%206.3.1.png)
2. Ubah nilai nice menjadi 10 menggunakan renice, lalu verifikasi kembali.
![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/latihan%206.3.2.png)
3. Coba ubah nilai nice menjadi -5 tanpa sudo. Apa yang terjadi? Mengapa
Linux membatasi hal ini untuk user biasa?
- Akan muncul pesan "Permission denied". Hanya user root yang bisa memberikan nilai nice negatif (prioritas lebih tinggi).
![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/latihan%206.3.3.png)

### Praktikum 6.4 — Mengirim Sinyal ke Proses

Latihan 6.4
1. Jalankan sleep 400 &, kirim SIGSTOP, dan amati perubahan kolom
STAT. Kondisi apa yang muncul?

![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/latihan%206.4.1.png)
2. Kirim SIGCONT dan verifikasi proses kembali berjalan.

![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/latihan%206.4.2.png)
3. Hentikan proses dengan SIGTERM lalu verifikasi sudah tidak ada. Kapan
Anda memilih SIGKILL daripada SIGTERM?
- Gunakan SIGKILL (9) hanya jika proses "macet" dan tidak merespons SIGTERM (15)

### Praktikum 6.5 — Manajemen Job Foreground dan Background

Latihan 6.5
1. Jalankan top di foreground. Apa yang terjadi di terminal?
- program berjalan terus
![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/latihan%206.5.1.png)
2. Tekan Ctrl+Z dan cek statusnya dengan jobs. Kondisi apa yang
ditampilkan?
![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/latihan%206.5.2.png)
3. Pindahkan ke background dengan bg. Apakah top dapat berjalan dengan
baik di background? Mengapa?
- Tidak, top akan berhenti (T) karena ia adalah program interaktif yang membutuhkan input terminal.
4. Kembalikan ke foreground dengan fg, lalu keluar dengan q .
![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/latihan%206.5.1.png)
![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/latihan%206.5.2.png)

### Praktikum 6.6 — Pemantauan Proses

Latihan 6.6
1. Gunakan ps aux –sort=%mem untuk menemukan proses yang menggunakan memori paling banyak di VM Anda. Proses apa itu?
![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/latihan%206.6.1.png)
2. Di dalam top, tekan 1 . Apa yang berubah pada tampilan? Mengapa
informasi ini berguna?
-  Informasi ini sangat berguna untuk mendeteksi apakah beban kerja sistem terbagi rata atau ada satu core yang bekerja terlalu berat (bottleneck) sementara core lainnya menganggur.
3. Di dalam htop, navigasikan ke proses sshd menggunakan tombol panah.
Tekan F9 dan amati opsi sinyal yang tersedia.
![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/latihan%206.6.2.png)

### 1.8 Latihan

Latihan 6.A
Eksplorasi Proses Sistem
1. Jalankan ps aux –forest dan temukan proses dengan PID 1. Apa
nama dan fungsi proses tersebut dalam sistem Linux modern?
- i sistem Linux modern (seperti Ubuntu Server Anda), PID 1 biasanya adalah systemd. Fungsinya adalah sebagai proses induk pertama yang dilahirkan saat booting dan bertanggung jawab mengelola layanan sistem lainnya.
![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/latihan%206a.1.png)
2. Hitung berapa proses yang dimiliki oleh user root dan berapa yang
dimiliki oleh user Anda. Mengapa root memiliki lebih banyak proses?
- User root memiliki lebih banyak proses karena ia menjalankan layanan sistem (daemon), manajemen perangkat keras, dan tugas latar belakang yang menjaga stabilitas server.
![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/latihan%206a.2.png)
3. Temukan semua proses yang berada dalam kondisi S. Mengapa sebagian
besar proses di sistem berada dalam kondisi ini?
- Sebagian besar proses berada dalam kondisi S karena mereka sedang menunggu event atau input (seperti menunggu permintaan jaringan atau input keyboard) dan tidak memerlukan CPU saat sedang menunggu.
![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/latihan%206a.3.png)

Latihan 6.B
Simulasi Manajemen Job
1. Jalankan tiga perintah sleep dengan durasi 100, 200, dan 300 detik di
background. Verifikasi ketiganya dengan jobs.
- Tanda & menjalankan perintah di background sehingga terminal tetap bisa digunakan. Perintah jobs akan menampilkan daftar ketiga proses tersebut dengan nomor job [1], [2], dan [3]
![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/latihan%206b.1.png)
2. Bawa job kedua ke foreground, jeda dengan Ctrl+Z , lalu kembalikan
ke background dengan bg.
- Gunakan perintah jobs untuk memastikan statusnya kembali menjadi running di background. 
![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/latihan%206b.2.png)
3. Hentikan job pertama dengan kill %1. Tampilkan kembali daftar job.
Berapa job yang tersisa?
- Job [1] (sleep 100) akan dihentikan. Daftar jobs sekarang hanya akan menyisakan 2 job (job [2] dan [3]).
![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/latihan%206b.3.png)

Latihan 6.C
Prioritas dan Sinyal
1. Jalankan dua proses sleep: satu dengan nice +5 dan satu dengan nice
+15. Verifikasi nilai NI keduanya dengan ps.
- Nilai nice menentukan prioritas; semakin rendah nilainya (mendekati -20), semakin tinggi prioritasnya. Kolom NI pada ps akan menunjukkan angka 5 dan 15.

2. Gunakan renice untuk mengubah nice proses pertama menjadi +10.
Proses mana yang kini lebih diprioritaskan scheduler?
3. Kirim SIGSTOP ke salah satu proses, verifikasi kondisi T-nya, lalu kirim
SIGCONT. Akhiri semua proses percobaan dengan pkill sleep.
Langkah-langkah:
- SIGSTOP: kill -SIGSTOP <PID> (atau nomor job, misal kill -19 %1). Kondisi pada kolom STAT akan berubah menjadi T (Stopped).
- SIGCONT: kill -SIGCONT <PID> (atau kill -18 %1). Kondisi STAT akan kembali ke S (Sleeping).
- Pembersihan: Ketik pkill sleep untuk menghentikan semua proses percobaan sekaligus berdasarkan namanya.
- Tips Keamanan: Ingatlah bahwa user biasa hanya bisa menaikkan nilai nice (menurunkan prioritas). Hanya root yang bisa memberikan nilai negatif untuk memberikan prioritas tertinggi.