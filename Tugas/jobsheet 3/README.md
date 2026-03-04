# Sistem Operasi

<h4>Nama : Carlos Fadellilah Rama<h4>
<h4>NIM : 254107020064<h4>
<h4>Kelas : TI-1H<h4>

## Latihan 3.1
Buatlah script yang:
1. Menampilkan daftar 10 file terbesar di direktori /var/log/
![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/latihan%203.1.1.png)
2. Menyimpan hasilnya ke file large-logs.txt
![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/latihan%203.1.2.png)
3. Menampilkan output juga di terminal menggunakan tee
![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/latihan%203.1.3.png)
4. Menangani error dengan redirect ke error.log
![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/latihan%203.1.4.png)
## Latihan 3.2
Buat pipeline yang:
   - saya menggunankan "cut -d':' -f1 /etc/passwd | sort | tee sorted-users.txt" untuk menyederhanakannya
1. Membaca /etc/passwd
2. Mengekstrak username (kolom pertama)
3. Mengurutkan alfabetis
   - menggunakan "sort" akan menyusun daftar nama dari A ke Z.
4. Menyimpan ke file sorted-users.txt
Hint: Gunakan cut, sort, dan operator redirect.
![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/latihan%203.2.1.png)
## Latihan 3.3
Tulis script monitoring yang:
1. Mencatat penggunaan CPU dan memory setiap 5 detik
2. Menyimpan log dengan timestamp
3. Berjalan selama 1 menit (12 iterasi)
4. Output ditampilkan di terminal DAN disimpan ke file
![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/latihan%203.3.1.png)
![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/latihan%203.3.2.png)
![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/latihan%203.3.3.png)
## Latihan 3.4
Latihan 3.4
Buat perintah yang:
1. Mencari semua file .conf di sistem
2. Membuang pesan "Permission denied"
3. Menghitung jumlah file yang ditemukan
4. Menyimpan daftar path lengkap ke file
![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/latihan%203.4.1.png)
## Latihan 3.5
Latihan 3.5
Implementasikan script backup yang:
1. Menggunakan tar untuk backup direktori
2. Menampilkan progress dengan tee
3. Mencatat stdout ke backup-success.log
4. Mencatat stderr ke backup-error.log
5. Menambahkan timestamp di setiap log entry
![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/latihan%203.5.1.png)
![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/latihan%203.5.2.png)
![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](img/latihan%203.5.3.png)