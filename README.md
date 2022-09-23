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

### Jawaban
Evaluasi unjuk kerja User Space Filesystem (FUSE)

### Cara Pengerjaan
1. Export semua object HTTP (File -> Export Objects -> HTTP...) kemudian disimpan dan dibuka semua file export tipe html.
2. Pada file “194” terdapat penjelasan satu judul topik TA.
3. Topik TA yang dibuka oleh Ishaq adalah “Evaluasi unjuk kerja User Space Filesystem (FUSE)”
4. Dengan memasukkan filter ```http.request.uri contains "detail"``` juga menampilkan bahwa link topik TA tersebut yang dibuka oleh Ishaq.

![dokumentasi 2-1](image/Nomor%202/jawaban%202-2.png)
![dokumentasi 2-2](image/Nomor%202/jawaban%202-3.png)
![dokumentasi 2-3](image/Nomor%202/jawaban%202-1.png)

## Nomor 3
### Soal
Filter sehingga wireshark hanya menampilkan paket yang menuju port 80! 

### Cara Pengerjaan
1. Menjalankan command `tcp.dstport == 80` pada display filter.

![dokumentasi 3](image/Nomor%203/1.png)

## Nomor 4

### Soal

Filter sehingga wireshark hanya mengambil paket yang berasal dari port 21!

### Cara Pengerjaan

1. Melakukan filter "tcp.srcport == 21 || udp.srcport == 21"

![dokumentasi 1-1](image/Nomor%204/jawaban%204-1.png)

## Nomor 5
### Soal
Filter sehingga wireshark hanya mengambil paket yang berasal dari port 443!

### Cara Pengerjaan
1. Menjalankan command `tcp.srcport == 443` pada display filter.

![dokumentasi 5](image/Nomor%205/1.png)

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

## Nomor 8
### Soal
Telusuri aliran paket dalam file .pcap yang diberikan, cari informasi berguna berupa percakapan antara dua mahasiswa terkait tindakan kecurangan pada kegiatan praktikum. Percakapan tersebut dilaporkan menggunakan protokol jaringan dengan tingkat keandalan yang tinggi dalam pertukaran datanya sehingga kalian perlu menerapkan filter dengan protokol yang tersebut.

### Pemecahan Masalah
TCP adalah protokol jaringan dengan tingkat keandalan yang tinggi dalam pertukaran data. Untuk mempermudah menemukan data, maka diperlukan beberapa kata kunci yang berkaitan dengan kecurangan, salah satunya jawaban.
### Cara Pengerjaan
1. Menjalankan command `tcp contains "jawaban"` pada display filter.
2. `follow TCP Stream` satu per satu sampai menemukan informasi berguna.

![dokumentasi 8-1](image/Nomor%208/1.png)
![dokumentasi 8-2](image/Nomor%208/2.png)
![dokumentasi 8-3](image/Nomor%208/3.png)

## Nomor 9
### Soal
Terdapat laporan adanya pertukaran file yang dilakukan oleh kedua mahasiswa dalam percakapan yang diperoleh, carilah file yang dimaksud! Untuk memudahkan laporan kepada atasan, beri nama file yang ditemukan dengan format [nama_kelompok].des3 dan simpan output file dengan nama “flag.txt”.

### Pemecahan Masalah
Dari informasi yang didapat dari Nomor 8, didapatkan bahwa filenya :
- file salt
- perlu didecrypt memnggunakan openssl menggunakan metode des3
- file decrypt memiliki password yang berhubungan dengan "nama karakter anime yang kembar lima"
- ditransfer dari port 9002

### Cara Pengerjaan
1. Menjalankan command `tcp.srcport == 9002"` pada display filter.
2. `follow TCP Stream` satu per satu sampai menemukan file saltnya.
3. Tampilkan file salt tersebut sebagai `Raw` lalu simpan file dengan format `A06.des3`.
4. Setelah itu, decrypt file tersebut dengan command `openssl des3 -d -salt -in A06.des3 -out flag.txt` menggunakan wsl.
5. Kemudian, akan ada perintah untuk memasukkan kode password, masukkan `nakano`

![dokumentasi 9-1](image/Nomor%209/1.png)
![dokumentasi 9-2](image/Nomor%209/2.png)
![dokumentasi 9-3](image/Nomor%209/3.png)

## Nomor 10
### Soal
Temukan password rahasia (flag) dari organisasi bawah tanah yang disebutkan di atas!

### Jawaban
Dari soal no.9, didapatkan flag.txt dengan isi `jawaban`.
![dokumentasi 10](image/Nomor%2010/1.png)
