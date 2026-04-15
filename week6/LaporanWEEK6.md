# LAPORAN PRAKTIKUM JARINGAN KOMPUTER WEEK 6
Tujuan :
1. Mahasiswa dapat menginvestigasi cara kerja protokol TCP menggunakan Wireshark

# Menangkap Tansfer TCP dalam Jumlah Besar dari Komputer Pribadi ke Remote Server
Soal :
1. Berapa alamat IP dan nomor port TCP yang digunakan oleh komputer klien (sumber) untuk 
mentransfer file ke gaia.cs.umass.edu? Cara paling mudah menjawab pertanyaan ini adalah 
dengan memilih sebuah pesan HTTP dan meneliti detail paket TCP yang digunakan untuk 
membawa pesan HTTP tersebut. 
Jawab : Berdasarkan analisis paket HTTP pada Wireshark, alamat IP komputer klien adalah 192.168.1.102 dengan nomor port TCP 1161. Informasi ini diperoleh dari field Source pada bagian Internet Protocol dan Transmission Control Protocol.
![gambar](../assets/image/week6(1).png)
2. Apa alamat IP dari gaia.cs.umass.edu? Pada nomor port berapa ia mengirim dan menerima 
segmen TCP untuk koneksi ini? 
Jawab : Berdasarkan analisis paket TCP pada Wireshark, alamat IP dari gaia.cs.umass.edu adalah 128.119.245.12. Server menggunakan port 80 (HTTP) untuk mengirim dan menerima segmen TCP dalam koneksi tersebut.
![gambar](../assets/image/week6(1).png)
3. Berapa alamat IP dan nomor port TCP yang digunakan oleh komputer klien Anda (sumber) 
untuk mentransfer  ke gaia.cs.umass.edu? 
Jawab : Berdasarkan analisis paket TCP pada Wireshark, alamat IP komputer klien adalah 192.168.1.102 dengan nomor port TCP 1161. Informasi ini diperoleh dari field Source pada protokol IP dan TCP.
![gambar](../assets/image/week6(1).png)

# Dasar TCP
Soal : 
1. Berapa nomor urut segmen TCP SYN yang digunakan untuk memulai sambungan TCP antara 
komputer klien dan gaia.cs.umass.edu? Apa yang dimiliki segmen tersebut sehingga 
teridentifikasi sebagai segmen SYN? 
Jawab : Nomor urut segmen SYN adalah 0. Segmen ini teridentifikasi sebagai SYN karena memiliki flag SYN.
![gambar](../assets/image/week6(2).png)
2. Berapa nomor urut segmen SYNACK yang dikirim oleh gaia.cs.umass.edu ke komputer klien 
sebagai balasan dari SYN? Berapa nilai dari field Acknowledgement pada segmen SYNACK? 
Bagaimana gaia.cs.umass.edu menentukan nilai tersebut? Apa yang dimiliki oleh segmen  
sehingga teridentifikasi sebagai segmen SYNACK? 
Jawab : Nomor urut SYN-ACK adalah 0 dan nilai acknowledgement adalah 1. Nilai ini diperoleh dari sequence number SYN sebelumnya ditambah 1. Segmen ini teridentifikasi karena memiliki flag SYN dan ACK.
![gambar](../assets/image/week6(3).png)
3. Berapa nomor urut segmen TCP yang berisi perintah HTTP POST? Perhatikan bahwa untuk 
menemukan perintah POST, Anda harus menelusuri content field milik paket di bagian 
bawah jendela Wireshark, kemudian cari segmen yang berisi "POST" di bagian field DATA
nya. 
Jawab : Nomor urut segmen TCP yang berisi HTTP POST adalah 164041
![gambar](../assets/image/week6(4).png)
4. Anggap segmen TCP yang berisi HTTP POST sebagai segmen pertama dalam koneksi TCP. Berapa nomor urut dari enam segmen pertama dalam TCP (termasuk segmen yang berisi HTTP POST)? Pada jam berapa setiap segmen dikirim? Kapan ACK untuk setiap segmen diterima? Dengan adanya perbedaan antara kapan setiap segmen TCP dikirim dan kapan acknowledgement-nya diterima, berapakah nilai RTT untuk keenam segmen tersebut? Berapa nilai EstimatedRTT setelah penerimaan setiap ACK? (Catatan: Wireshark memiliki fitur yang memungkinkan Anda untuk memplot RTT untuk setiap segmen TCP yang dikirim. Pilih segmen TCP yang dikirim dari klien ke server gaia.cs.umass.edu pada jendela "daftar  paket yang ditangkap". Kemudian pilih: Statistics->TCP Stream Graph- >Round Trip Time Graph). 
Jawab : 




































































