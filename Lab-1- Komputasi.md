Nama		: Zinedine Maylano

NIM 		: 09021182025011

Mata kuliah	: Komputasi Ubiquitos dan Perpasiv

Kelas		: Teknik Informatika

Semester	: 6 (Enam)

Fakultas Ilmu Komputer, Universitas Sriwijaya. 

**Lab-1:** Implementasi dan pemanfaatan infrastruktur perangkat keras menggunakan ownCloud pada Sistem operasi linux Ubuntu 18.04 server

**Tujuan :**

- Mahasiswa bisa mengimplementasikan sistem operasi berbasis web interface, pemanfaatan storage berbasis cloud.

**Perkenalan.**

Owncloud adalah sebuah platform file sharing yang bersifat *open-source* dan berbagai gabungan atau kolaborasi yang dapat menyimpan, memanage *personal content* kita, seperti dokumen dan gambar pada lokasi yang terpusat. Implementasi dari ownCloud merupakan hal yang serupa pada aplikasi dropbox, dengan fitur online storage yang dapat kita *create* sesuai dengan resource pada server atau komputer kita. 

**Langkah 1 - Installasi Ubuntu Server.**

Pertama kali, kita harus mendownload file .iso linux ubuntu server pada link berikut <https://ubuntu.com/download/server>



Lakukan instalasi di komputer yang tersedia, ataupun jalankan menggunakan software virtualisasi seperti virtualbox (https://www.virtualbox.org/wiki/Downloads) ataupun opsitional menggunakan VM-ware player (https://www.vmware.com/go/downloadworkstationplayer). Untuk tutorial tata cara proses instalasi ubuntu server pada aplikasi virtualisasi akan dilewatkan.

\*Catatan: pastikan alamat IP pada virtualbox terpasang dan dalam network yang sama.

**Langkah 2 - Installasi ownCloud**

Paket ownCloud server pada dasarnya tidak tersedia pada repositori dari sistem linux ubuntu tersebut, maka perlu kita unduh release key menggunakan curl command dan import menggunakan apt-key add, seperti pada command di bawah:

$ curl https://download.owncloud.org/download/repositories/10.0/Ubuntu\_18.04/Release.key | sudo apt-key add -

File ‘Release.key’ berisikan sebuah PGP (Pretty Good Privacy publik key seperti apt, yang akan digunakan untuk men-verifikasi ownCloud package sebagai aplikasi authentic.

Untuk tambahan silahkan tambahkan owncloud.list pada source.list.d pada direktori apt.

$ echo 'deb http://download.owncloud.org/download/repositories/10.0/Ubuntu\_18.04/ /' | sudo tee /etc/apt/sources.list.d/owncloud.list

Kemudian lakukan update, instalasi beberapa paket - paket pendukung seperti php

$ sudo apt update

$ sudo apt install php-bz2 php-curl php-gd php-imagick php-intl php-mbstring php-xml php-zip owncloud-files


**Langkah 3 - konfigurasi MySQL database**

Login ke database sql server menggunakan command line sebagai berikut:

$ sudo mysql

Lakukan konfigurasi untuk password MySQL pada akun root:

$ mysql -u root -p

Kemudian, buatlah database untuk ownCloud:

$ mysql> CREATE DATABASE owncloud;

$ mysql> GRANT ALL ON owncloud.\* to 'owncloud'@'localhost' IDENTIFIED BY 'owncloud\_database\_password';

\*Catatan: ganti owncloud\_database\_password dengan password database.

$ mysql> FLUSH PRIVILEGES;

$ mysql> exit

**Langkah 4 - konfigurasi ownCloud**

Untuk melakukan akses pada ownCloud web interface, bukalah browser anda, dan akses <http://alamat_ip_server>

Kita akan melihat konfigurasi ownCloud pada browser, buatlah akun anda, dan password:


Selanjutnya lewati, konfigurasi **Data folder** kemudian lanjutkan ke konfigurasi database.

Kemudian klik **Finish** untuk menyelesaikan tahapan konfigurasi ownCloud. Lakukan login menggunakan akses akun dan password yang kita buat sebelumnya.

Setelah itu kita akan ditampilkan, tampilan dari ownCloud tersebut.

**Note:** ulangi langkah - langkah di atas, kemudian jelaskan fitur - fitur yang ada owncloud tersebut, beserta pemanfaatannya.

