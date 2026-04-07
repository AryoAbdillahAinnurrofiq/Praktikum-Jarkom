# Laporan Jaringan Komputer WEEK 4

## DNS
Tujuan Praktikum :
1. Mahasiswa dapat menginvestigasi cara kerja DNS menggunakan Wireshark 

## NSLOOKUP
1.  Jalankan nslookup untuk mendapatkan alamat IP dari server web di Asia. Berapa alamat IP 
server tersebut? 
Jawab : IP : 2404.6800.4003.c02.5e.142.250.4.94
![gambar](../Praktikum-Jarkom/assets/image/week4(1).png)
2. Jalankan nslookup agar dapat mengetahui server DNS otoritatif untuk universitas di Eropa
Jawab : menggunakkan universitas oxford
![gambar](../Praktikum-Jarkom/assets/image/week4(2).png)
3. Jalankan nslookup untuk mencari tahu informasi mengenai server email dari Yahoo! Mail 
melalui salah satu server yang didapatkan di pertanyaan nomor 2. Apa alamat IP-nya?
Jawab : pada mta5.am0.yahoodns.net salah satu ip nya adalah : 67.195.204.79
![gambar1](../Praktikum-Jarkom/assets/image/week4(3).png)
![gambar2](../Praktikum-Jarkom/assets/image/week4(4).png)

## IPCONFIG
IPCONFIG/ALL :
![gambar](../Praktikum-Jarkom/assets/image/week4(5).png)
IPCONFIG/DISPLAYDNS
![gambar](../Praktikum-Jarkom/assets/image/week4(6).png)

## Tracing DNS dengan Wireshark
Filter tracing DNS sesuai dengan IPaddress :
![gambar](../Praktikum-Jarkom/assets/image/weel4(7).png)
Filter DNS :
![gambar1](../assets/image/week4(9).png)
![gambar2](../assets/image/week4(8).png)
Soal :
1. Cari pesan permintaan DNS dan balasannya. Apakah pesan tersebut dikirimkan melalui UDP 
atau TCP? 
Jawab : Pesan DNS dikirim menggunakan UDP (User Datagram Protocol), bukan TCP.
![GAMBAR1](../assets/image/week4(11).png)
![GAMBAR2](../assets/image/week4(12).png)
2. Apa port tujuan pada pesan permintaan DNS? Apa port sumber pada pesan balasannya?
Jawab : Port tujuan pada pesan permintaan DNS adalah 53, sedangkan port sumber pada pesan balasan juga 53.
![GAMBAR1](../assets/image/week4(11).png)
![GAMBAR2](../assets/image/week4(12).png)
3. Pada pesan permintaan DNS, apa alamat IP tujuannya? Apa alamat IP server DNS lokal anda 
(gunakan ipconfig untuk mencari tahu)? Apakah kedua alamat IP tersebut sama? 
Jawab : Ya, sama 182.8.64.11
![GAMBAR1](../assets/image/week4(13).png)
![GAMBAR2](../assets/image/week4(14).png)
4.Periksa pesan permintaan DNS. Apa “jenis” atau ”type” dari pesan tersebut? Apakah pesan 
permintaan tersebut mengandung ”jawaban” atau ”answers”? 
Jawab : Jenis (type) dari pesan DNS adalah A (Address Record), yang digunakan untuk meminta alamat IP dari suatu domain.
Pesan permintaan DNS tidak mengandung jawaban (answers), karena hanya berisi permintaan ke server DNS.
![GAMBAR1](../assets/image/week4(15).png)
5. Periksa pesan balasan DNS. Berapa banyak ”jawaban” atau ”answers” yang terdapat di 
dalamnya? Apa saja isi yang terkandung dalam setiap jawaban tersebut?
Jawab : Ada 7 jawaban (answers)
![GAMBAR1](../assets/image/week4(16).png)
6. Perhatikan paket TCP SYN yang selanjutnya dikirimkan oleh host Anda. Apakah alamat IP 
pada paket tersebut sesuai dengan alamat IP yang tertera pada pesan balasan DNS? 
Jawab : Alamat IP pada paket TCP SYN adalah 2606:4700::6810... (IPv6), sedangkan alamat IP pada hasil DNS sebelumnya adalah IPv4 (misalnya 74.xxx.xxx.xxx). Oleh karena itu, kedua alamat IP tersebut tidak sama, karena sistem dapat menggunakan IPv6 atau IPv4 tergantung konfigurasi jaringan.
![GAMBAR1](../assets/image/week4(17).png)
7. Halaman web yang sebelumnya anda akses (http://www.ietf.org) memuat beberapa 
gambar. Apakah host Anda perlu mengirimkan pesan permintaan DNS baru setiap kali ingin 
mengakses suatu gambar? 
Jawab : Tidak, host tidak perlu mengirimkan permintaan DNS baru setiap kali mengakses suatu gambar. Hal ini karena alamat IP dari domain tersebut sudah disimpan dalam DNS cache, sehingga dapat langsung digunakan tanpa perlu melakukan query DNS kembali.

## Pengambilan paket NSLOOOKUP pada www.mit.edu
![GAMBAR1](../assets/image/week4(18).png)
![GAMBAR2](../assets/image/week4(19).png)
Soal :
1. Apa port tujuan pada pesan permintaan DNS? Apa port sumber pada pesan balasan DNS?
Jawab : Port tujuan pada permintaan DNS adalah 53, dan port sumber pada balasan DNS juga 53.
![GAMBAR1](../assets/image/week4(20).png)
![GAMBAR2](../assets/image/week4(21).png)
2. Ke alamat IP manakah pesan permintaan DNS dikirimkan? Apakah alamat IP tersebut 
merupakan default alamat IP server DNS lokal Anda?
Jawab : Ya, sama Pesan permintaan DNS dikirim ke alamat IP 182.8.64.11.
Berdasarkan hasil ipconfig, alamat IP tersebut merupakan DNS server lokal yang digunakan.
Oleh karena itu, kedua alamat IP tersebut sama.
![GAMBAR1](../assets/image/week4(22).png)
![GAMBAR2](../assets/image/week4(23).png)
3. Periksa pesan permintaan DNS. Apa ”jenis” atau ”type” dari pesan tersebut? Apakah pesan 
tersebut mengandung ”jawaban” atau ”answers”? 
Jawab : Jenis pesan DNS adalah A (Address Record).
Pesan permintaan tidak mengandung jawaban (answers), karena hanya berisi permintaan alamat IP.
![GAMBAR1](../assets/image/week4(24).png)
4. Periksa pesan balasan DNS. Berapa banyak ”jawaban” atau “answers” yang terdapat di 
dalamnya. Apa saja isi yang terkandung dalam setiap jawaban tersebut?
Jawab : Jumlah jawaban pada balasan DNS adalah 3.Isi jawaban berupa alamat IP (A record) dan/atau alias domain (CNAME).
![GAMBAR1](../assets/image/week4(25).png)

## NSLOOKUP -type=NS mit.edu 8.8.8.8
![GAMBAR1](../assets/image/week4(26).png)
Soal :
1. Ke alamat IP manakah pesan permintaan DNS dikirimkan? Apakah alamat IP tersebut 
merupakan default alamat IP server DNS lokal Anda? 
Jawab : Pesan permintaan DNS dikirim ke alamat IP 8.8.8.8.
Alamat IP tersebut bukan merupakan DNS server lokal, karena DNS lokal yang digunakan adalah 182.8.64.11.
Hal ini terjadi karena perintah nslookup secara eksplisit menggunakan DNS server Google (8.8.8.8). Perbedaan ini disebabkan karena penggunaan parameter tambahan pada perintah nslookup yang mengarahkan query ke DNS server tertentu (8.8.8.8), bukan ke DNS lokal secara default.
![GAMBAR1](../assets/image/week4(27).png)
![GAMBAR2](../assets/image/week4(28).png)
2. Periksa pesan permintaan DNS. Apa ”jenis” atau ”type” dari pesan tersebut? Apakah pesan 
tersebut mengandung ”jawaban” atau ”answers”? 
Jawab : Jenis pesan DNS adalah NS (Name Server).
Pesan permintaan tidak mengandung jawaban (answers), karena hanya berupa permintaan ke server DNS.
![GAMBAR](../assets/image/week4(29).png)
3. Periksa pesan balasan DNS. Apa nama server MIT yang diberikan oleh pesan balasan? 
Apakah pesan balasan ini juga memberikan alamat IP untuk server MIT tersebut? 
Jawab : Pesan balasan DNS memberikan beberapa nama server milik MIT, seperti use2.akam.net dan asia2.akam.net.
Pesan balasan ini tidak selalu memberikan alamat IP secara langsung, melainkan hanya nama server DNS.
![GAMBAR](../assets/image/week4(30).png)

## NSLOOKUP www.aiit.or.kr bitsy.mit.edu 
![GAMBAR](../assets/image/week4(31).png)
Soal : 
1.  Ke alamat IP manakah pesan permintaan DNS dikirimkan? Apakah alamat IP tersebut 
merupakan default alamat IP server DNS lokal Anda? 
Jawab : Pesan permintaan DNS dikirim ke alamat IP 53.
Alamat tersebut bukan merupakan DNS server lokal, karena DNS lokal yang digunakan adalah 182.8.64.11.
Hal ini terjadi karena query diarahkan ke server DNS tertentu (bitsy.mit.edu).
![GAMBAR](../assets/image/week4(32).png)
2. Periksa pesan permintaan DNS. Apa ”jenis” atau ”type” dari pesan tersebut? Apakah pesan 
tersebut mengandung ”jawaban” atau ”answers”? 
Jawab : Jenis pesan DNS adalah A (bitsy.mit.edu).
Pesan permintaan tidak mengandung jawaban (answers), karena hanya berisi permintaan alamat IP.
![GAMBAR](../assets/image/week4(33).png)
3. Periksa pesan balasan DNS. Berapa banyak ”jawaban” atau “answers” yang terdapat di 
dalamnya. Apa saja isi yang terkandung dalam setiap jawaban tersebut? 
Jawab : Jumlah jawaban pada pesan balasan DNS adalah 1.
Setiap jawaban berisi alamat IP dari domain www.aiit.or.kr
![GAMBAR](../assets/image/week4(34).png)





































