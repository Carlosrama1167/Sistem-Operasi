# Sistem Operasi

<h4>Nama : Carlos Fadellilah Rama<h4>
<h4>NIM : 254107020064<h4>
<h4>Kelas : TI-1H<h4>

## Tugas Pendahuluan

### 1. Apa yang dimaksud perintah-perintah direktory : pwd, cd, mkdir, rmkdir.
- pwd (Print Working Directory): Menampilkan jalur (path) direktori tempat Anda berada saat ini.
- cd (Change Directory): Berpindah dari satu direktori ke direktori lain.
- mkdir (Make Directory): Membuat direktori baru.
- rmdir (Remove Directory): Menghapus direktori yang kosong.

### 2. Apa yang dimaksud perintah-perintah manipulasi file :	cp, mv dan rm (sertakan format yang digunakan)
- cp [asal] [tujuan]: Menyalin file atau direktori.
- mv [asal] [tujuan]: Memindahkan atau mengubah nama (rename) file/direktori.
- rm [file]: Menghapus file. Gunakan -r untuk menghapus direktori beserta isinya.
### 3. Jelaskan perbedaan Symbolic link menggunakan hard link (direct) dan soft link (indirect).
- Hard Link: Menciptakan nama file baru yang menunjuk ke INODE yang sama. Jika file asli dihapus, data tetap ada selama masih ada hard link lain. Terbatas pada partisi yang sama.
- Soft Link (Symbolic): Seperti shortcut di Windows. Ia menunjuk ke nama file asli. Jika file asli dihapus, link akan rusak (broken). Bisa lintas partisi.
### 4. Tuliskan maksud perintah-perintah : file, find, which, locate dan grep.
- file: Menentukan tipe/format file.
- find: Mencari file di dalam hirarki direktori secara mendalam.
- which: Menunjukkan lokasi file executable dari suatu perintah sistem.
- locate: Mencari file dengan cepat menggunakan database sistem.
- grep: Mencari string atau teks tertentu di dalam isi file.

## Percobaan 1: Membuat Direktori
### Langkah-Langkah
1. Melihat direktori HOME
    - pwd
    - echo $HOME
    ![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](IMG/percobaan%201.1.png)
2. Melihat Direktori induk dan aktual
    - pwd
    - cd .
    - pwd
    - cd ..
    - pwd
    - cd
  ![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](IMG/percobaan%201.2.png)
3. Membuat satu direktori, lebih dari satu direktori atau sub direktori
    - pwd
    - mkdir A B C A/D A/E B/F A/D/A
    - ls -l
    - ls -l A
    - ls -l A/D
  ![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](IMG/percobaan%201.3.png)
4. Menghapus satu atau lebih direktori hanya dapat dilakukan pada direktori kosong dan hanya dapat dihapus oleh pemiliknya kecuali bila diberikan ijin aksesnya
    - rmdir B
    - ls -l B
    - rmdir B/F B
    - ls -l B
    ![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](IMG/percobaan%201.4.png) 
    - terjadi error saat rmdir B karena direktori B tidak kosong sehingga tidak bisa dihapus
    - terjadi error saat ls -l B karena direktori B sudah dihapus sehingga tidak bisa di-list
5. Navigasi direktori dengan instruksi cd untuk berpindah dari satu direktori ke direktori lain
    - pwd
    - ls -l
    - cd A
    - pwd
    - cd ..
    - pwd
    - cd /home/laut/C
    - pwd
    - cd /laut/C
    - pwd
    ![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](IMG/percobaan%201.5.png) 
    - Terjadi error karena alamat yang ditulis tidak lengkap, jika ingin menulis alamat tanpa harus menulis /home/username/ maka kita bisa menggunakan ~ sebagai pengganti dan bukannya langsung menulis /username/
## Percobaan 2: Manipulasi File
### Langkah-Langkah
1. Perintah cp untuk mengkopi file atau seluruh direktori
    - cat > contoh
    - Membuat sebuah file
    [Cntrl-d]
    - ls -l
    - cp contoh A
    - ls -l A
    - cp contoh contoh1 A/D
    - ls -l A/D
    ![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](IMG/percobaan%202.1.png)
2. Perintah mv untuk memindah file
    - mv contoh contoh2
    - ls -l
    - mv contoh1 contoh2 A/D
    - ls -l A/D
    - mv contoh contoh1 C
    - ls -l C
      ![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](IMG/percobaan%202.2.png)
3. Perintah rm untuk menghapus file
    - rm contoh2
    - ls -l
    - rm -i contoh
    - rm -rf A C
    - ls -l
      ![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](IMG/percobaan%202.3.png)
## Percobaan 3: Tautan Simbolis
### Langkah-Langkah
1. 
    - echo "Hello apa khabar" > halo.txt
    - ls -l
    - ln halo.txt z
    - ls -l
    - cat z
    - mkdir mydir
    - ln z mydir/halo.juga
    - cat mydir/halo.juga
    - ln -s z bye.txt
    - ls -l bye.txt
    - cat bye.txt
      ![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](IMG/percobaan%203.1.png)
## Percobaan 4: Melihat Isi File
### Langkah-Langkah
1. 
    - ls -l
    - file halo.txt
    - file bye.txt
    ![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](IMG/percobaan%204.1.png)
## Percobaan 5: Mencari File
### Langkah-Langkah
1. Perintah find
    - find /home -name "*.txt" -print > myerror.txt
    - cat myerror.txt
    - find . -name "*.txt" -exec wc -l '{}' ';'
      ![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](IMG/percobaan%205.1.png)
2. Perintah which
    - which ls
      ![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](IMG/percobaan%205.2.png)
3. Perintah locate
    - locate "*.txt"
  ![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](IMG/percobaan%205.3.png)
## Percobaan 6: Mencari Teks Pada File 
### Langkah-Langkah
    - grep Hallo *.txt
    ![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](IMG/percobaan%206.1.png)

## Latihan
1. Cobalah urutan perintah berikut:
    - cd
    - pwd
    - ls -al
    - cd .
    - pwd
    - cd ..
    - pwd
    - ls -al
    - cd ..
    - pwd
    - ls -al
    - cd /etc
    - ls -al | more
    - cat passwd
    - cd -
    - pwd
 ![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](IMG/latihan%201.1.png)
![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](IMG/latihan%201.2.png)
![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](IMG/latihan%201.3.png)
![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](IMG/latihan%201.4.png)
![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](IMG/latihan%201.5.png)
2. Lanjutkan penelusuran pohon pada sistem file menggunakan cd, ls, owd, dan cat. Telusuri direktori /bin, /usr/bin, /sbin, /tmp, dan /boot
    - /bin
    ![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](IMG/latihan%202.1.png)
    - /usr/bin
    ![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](IMG/latihan%202.1.png)
    - /sbin
    ![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](IMG/latihan%202.2.png)
    - /tmp
    ![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](IMG/latihan%202.3.png)
    - /boot
    ![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](IMG/latihan%202.4.png)
3. Telusuri direkoty /dev. identifikasi perangkat yang tersedia. identifikasitty (terminal) Anda (ketik siapa saya); siapa pemilik tty Anda (gunakan ls -l)
![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](IMG/latihan%203.1.png)
![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](IMG/latihan%203.2.png)

4. Direktori Telusuri /proc. Tampilkan isi file interupsi, perangkat, cpuinfo, meminfo dan uptime menggunakan perintah cat. Dapatkah Anda melihat mengapa direktori /proc disebut pseudo-filesystem yang memungkinkan akses ke struktur data kernel?
- interupsi
![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](IMG/latihan%204.1.png)
- perangkat
![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](IMG/latihan%204.2.png)
- info cpu
![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](IMG/latihan%204.3.png)
- info memori
![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](IMG/latihan%204.4.png)
- waktu aktif
![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](IMG/latihan%204.5.png)
- Mengapa /proc disebut sebagai pseudo-filesystem, hal ini dikarenakan direktori /proc tidak memiliki file nyata, melainkan /proc memiliki file yang memuat informasi mengenai segala sesuatu yang sedang berjalan di mesin saat ini. Hal ini relevan dengan penjelasan mengenai pseudo-filesystem yang memiliki arti sebaga filesystem yang memuat informasi mengenai sistem yang berjalan saat ini
5. Ubahlah direktori home ke user lain secara langsung menggunakan cd ~username
![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](IMG/latihan%205.1.png)
6. Ubah kembali ke direktori home anda
![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](IMG/latihan%206.1.png)
7. Buat subdirektori work dan play
![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](IMG/latihan%207.1.png)
8. Hapus direktori kerja
![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](IMG/latihan%208.1.png)
9. salin file /etc/passwd ke direktori home Anda
![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](IMG/latihan%209.1.png)
10. pindahkan ke subdirektori play
![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](IMG/latihan%2010.1.png)
11. Ubahlah ke direktori play dan buat symbolic link dengan nama terminal yang menunjuk ke perangkat tty. Apa yang terjadi jika melakukan hard link ke perangkat tty?
![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](IMG/latihan%2011.1.png)
12. Buatlah file bernama hello.txt yang berisi kata "hello world". Bisakah Anda menggunakan "cp" menggunakan "terminal" sebagai file asal untuk menghasilkan efek yang sama
![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](IMG/latihan%2012.1.png)
13. Salin hello.txt dan terminal. Apa yang terjadi?
![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](IMG/latihan%2012.1.png)
14. Masih direktori home, copy keseluruhan direktori ke direktori bernama menggunakan symbolic link.
![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](IMG/latihan%2014.1.png)
15. Hapus direktori kerja dan isinya dengan satu perintah
![Ubuntu Server 24.04.3 LTS installation ISO file displayed with a disc icon on dark background](IMG/latihan%2015.1.png)