# Modul Jarkom Kelompok A06

## Anggota Kelompok

1. Hans Sean Nathanael - 5025201019
2. Mohammad Fany Faizul Akbar - 5025201225
3. Fadel Pramaputra Maulana - 5025201260

## Nomor 1

### Soal

Sebutkan web server yang digunakan pada "monta.if.its.ac.id"!

### Cara Pengerjaan

1. Menghubungkan wireshark dengan http://monta.if.its.ac.id/

![dokumentasi 1-1](image/Nomor%201/jawaban%201-1.png)

2. Melakukan filter display "http"

![dokumentasi 1-2](image/Nomor%201/jawaban%201-2.png)

3. Memilih paket yang terdapat "(text/html)" dan melihat info drop down Hypertext Transfer Protocol terlihat server yang digunakan adalah nginx/1.10.3

![dokumentasi 1-3](image/Nomor%201/jawaban%201-3.png)

## Nomor 2

### Soal

Ishaq sedang bingung mencari topik ta untuk semester ini , lalu ia datang ke website
monta dan menemukan detail topik pada website “monta.if.its.ac.id” , judul TA apa
yang dibuka oleh ishaq ?

### Cara Pengerjaan

1. Export semua object HTTP (File -> Export Objects -> HTTP...) kemudian disimpan dan dibuka semua file export tipe html.
2. Pada file “194” terdapat penjelasan satu judul topik TA.
3. Topik TA yang dibuka oleh Ishaq adalah “Evaluasi unjuk kerja User Space Filesystem (FUSE)”
4. Dengan memasukkan filter `http.request.uri contains "detail"` juga menampilkan bahwa link topik TA tersebut yang dibuka oleh Ishaq.

![dokumentasi 2-1](image/Nomor%202/jawaban%202-2.png)
![dokumentasi 2-2](image/Nomor%202/jawaban%202-3.png)
![dokumentasi 2-3](image/Nomor%202/jawaban%202-1.png)

## Nomor 4

### Soal

Filter sehingga wireshark hanya mengambil paket yang berasal dari port 21!

### Cara Pengerjaan

1. Melakukan filter "tcp.srcport == 21 || udp.srcport == 21"

![dokumentasi 1-1](image/Nomor%204/jawaban%204-1.png)

## Nomor 6

### Soal

Filter sehingga wireshark hanya menampilkan paket yang menuju ke lipi.go.id!

### Cara Pengerjaan

1. Melakukan ping ke lipi.go.id dan didapatkan ip address dari lipi.go.id yaitu "203.160.128.158"

![dokumentasi 1-1](image/Nomor%206/jawaban%206-1.png)

2. Lakukan display filter menggunakan "ip.dst == 203.160.128.158"

![dokumentasi 1-2](image/Nomor%206/jawaban%206-2.png)

## Nomor 7

### Soal

Filter sehingga wireshark hanya mengambil paket yang berasal dari ip kalian!

### Cara Pengerjaan

1. Menjalankan command “ipconfig” pada command prompt untuk mendapatkan IP sendiri.
2. Memasukkan capture filter “src host 192.168.100.6” (192.168.100.6 adalah IP lokal yang didapat dari ipconfig praktikan).
3. Melakukan ping pada suatu situs internet (yang digunakan adalah www.speedtest.net).

![dokumentasi 7-1](image/Nomor%207/jawaban%20nomor%207-1.png)
![dokumentasi 7-2](image/Nomor%207/jawaban%20nomor%207-2.png)
![dokumentasi 7-3](image/Nomor%207/jawaban%20nomor%207-3.png)
![dokumentasi 7-4](image/Nomor%207/jawaban%20nomor%207-4.png)
