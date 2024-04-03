# Laporan Resmi Praktikum Komunikasi Data dan Jaringan Komputer  
## Modul 1 Kelompok IT-32

**Anggota Kelompok IT-32:**

| Nama                      | NRP        |
|---------------------------|------------|
|Atha Rahma Arianti         | 5027221030 |
|Nur Azka Rahadiansyah      | 5027221064 |



## **FUZZ:**

![fuzz](fuzz.jpg)

Di soal fuzz ini, menggunakan filter `http`. Dari situ dapat dicari info dari POST, maka akan didapatkan IP address 

![fuzz1](fuzz1.png)

Kemudian menggunakan filter `tcp`, dari situ terlihat jika port yang digunakan adalah port 80

![fuzz2](fuzz2.png)

Kembali ke filter `http`, scroll dan klik paling bawah yang ada tulisan `302 found`, kemudian FOLLOW. Dari situ maka akan didapat endpoint `/` 

![fuzz3](fuzz3.png)


Terlihat juga toolname yang digunakan adalah `Fuzz Faster U Fool v2.0.0-dev`, yang kemudian disingkat menjadi `ffuf-v2.0.0-dev` pada jawaban 

![fuzz4](fuzz4.png)


Masukkan `302 found` pada kolom pencarian di bawah 

![fuzz5](fuzz5.png)

![fuzz6](fuzz6.png)

Didapatkan user & password, sayangnya baru dapet pas waktunya dah abis :((((

![fuzzlast](fuzzlast.png)



## **EVIDENCE:** 

![evidence](evidence.jpg)

Di soal evidence ini, menggunakan filter `http`, cari saja random yang memiliki info POST didalamnya kemudian klik follow

![EVIDENCE1](EVIDENCE1.png)

Didapatkan host `nanomate-solutions.com` 

![EVIDENCE2](EVIDENCE2.png)

Didapatkan server `Apache/2.4.56` 

![EVIDENCE3](EVIDENCE3.png)

Didapatkan endpoint `/app/includes/process_login.php` 

![EVIDENCE4](EVIDENCE4.png)

Kemudian menggunakan filter `tcp.stream eq 1248` (asalnya cari dari `frame.len == 714` dan beberapa packet length lainnya yang memiliki percobaan login, sudah dibuka satu persatu tetapi invalid semua kecuali yg eq 1248 ini) 

![EVIDENCE5](EVIDENCE5.png)

![EVIDENCE6](EVIDENCE6.png)

Klik follow, didapatkan email `tareq@gmail.com` dan password `tareq@nanomate` 

![EVIDENCE8](EVIDENCE8.png)




## **ATM ATP OR FTP**

![atm atp ftp](atmatpftp.jpg)

Pada soal ATM ATP or FTP ini digunakan filter `ftp`. Dari situ cukup cari yang memiliki keterangan `login successfull` atau memiliki kode 230


![atm atp ftp](atmatpftp0.png)

Klik follow

![atm atp ftp](atmatpftp1.png)

Didapatkan password 



## **HOW MANY PACKAGES**
![how many packages](howmanypackages.jpg)

Untuk pengerjaan soal How Many Packages ini, klik `statistic` di bagian atas kiri, lalu klik `packet length`, gunakan filter `frame.len == 94` (soalnya percobaan login yg gagal ada di length 94)

Didapatkan angka 934 

![how many packages](HOWMANYPACKAGES.png)





## **TRACE HIM**
![trace him](tracehim.jpg)

Di soal Trace Him ini menggunakan filter `ftp`. Dari situ dicari yang memiliki info `request`, tinggal dilihat saja IP sourcenya lalu didapatkan lah IP nya 10.30.3.4


![trace him](tracehim1.png)




## **creds**
(File Name : evidence)
![creds](creds.jpg)

filter `FTP` 
pada bagian info terdapat user dan password yang dikirim oleh 10.30.3.1
atau juga bisa menggunakan `Analyze` -> `follow` -> `tcp stream`




## **malwleowleo**
(File Name : evidence)
![malwleowleo](malwleowleo.jpg)




filter `FTP`

menggunakan `Analyze` --> `follow` --> `tcp stream`

atau juga bisa mencari lewat filter `tcp.stream eq 14` lalu menggunakan langkah yang sama dengan langkah 2



### **Sekian Laporan Resmi Praktikum Komunikasi Data dan Jaringan Komputer Modul 1 dari Kelompok IT-32**
## MATUR TENGKYU <3
