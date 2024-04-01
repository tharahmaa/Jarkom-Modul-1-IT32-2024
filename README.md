# Laporan Resmi Praktikum Komunikasi Data dan Jaringan Komputer 

## Modul 1 Kelompok IT-32


**Anggota:**

Atha Rahma Arianti - 5027221030

Nur Azka Rahadiansyah - 5027221064



# **FUZZ:**

![fuzz](fuzz.jpg)

filter http, cari info POST

dapet info dapet info IP address 

![fuzz1](fuzz1.png)

filter tcp
dapet info port 80 

![fuzz2](fuzz2.png)

balik ke filter http, klik paling bawah yg 302 found, FOLLOW 


dapet info endpoint / 

![fuzz3](fuzz3.png)


dapet info toolname Fuzz Faster U Fool v2.0.0-dev, disingkat 

![fuzz4](fuzz4.png)


cari 302 found di bawah 

![fuzz5](fuzz5.png)

![fuzz6](fuzz6.png)

dapet user & password, sayangnya baru dapet pas waktunya dah abis :((((

![fuzzlast](fuzzlast.png)



# **EVIDENCE:** 

![evidence](evidence.jpg)

filter http

cari info POST

follow 

![EVIDENCE1](EVIDENCE1.png)

dapet info host nanomate-solutions.com 

![EVIDENCE2](EVIDENCE2.png)

dapet info server Apache/2.4.56 

![EVIDENCE3](EVIDENCE3.png)

dapet info endpoint /app/includes/process_login.php 

![EVIDENCE4](EVIDENCE4.png)

filter tcp.stream eq 1248 (asalnya cari dari frame.len == 714 soalnya percobaan login ada di situ semua, dah dibuka 1” invalid semua kecuali yg eq 1248 ini) 

![EVIDENCE5](EVIDENCE5.png)

![EVIDENCE6](EVIDENCE6.png)

follow, dapet info email tareq@gmail.com dan password tareq@nanomate 

![EVIDENCE8](EVIDENCE8.png)




# **ATM ATP OR FTP**

![atm atp ftp](atmatpftp.jpg)

filter “ftp”

cari login successfull (code=230) 

![atm atp ftp](atmatpftp0.png)

follow

![atm atp ftp](atmatpftp1.png)

dapet password 



# **HOW MANY PACKAGES**
![how many packages](howmanypackages.jpg)

di bagian statistic, packet length, filter frame.len == 94 (soalnya percobaan login yg gagal ada di length 94)

dapet angka 934 

![how many packages](HOWMANYPACKAGES.png)





# **TRACE HIM**
![trace him](tracehim.jpg)

filter ftp

cari yg infonya request, berarti asalnya dari situ, IP nya 10.30.3.4 
![trace him](tracehim1.png)




# **creds**
(File Name : evidence)
![creds](creds.jpg)

filter “FTP” 
pada bagian info terdapat user dan password yang dikirim oleh 10.30.3.1
atau juga bisa menggunakan Analyze -> follow -> tcp stream




# **malwleowleo**
(File Name : evidence)
![malwleowleo](malwleowleo.jpg)




filter “FTP” 

menggunakan Analyze -> follow -> tcp stream

atau juga bisa mencari lewat filter tcp.stream eq 14 lalu menggunakan langkah yang sama dengan langkah 2



# **Sekian Laporan Resmi Praktikum Komunikasi Data dan Jaringan Komputer dari Kelompok IT-32**
## MATUR TENGKYU <3
