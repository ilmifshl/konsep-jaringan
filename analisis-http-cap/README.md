## Analisis Flow Graph

<img src='../assets/flowgraph-http-1.png'>

**Detik 0 - 1: Permulaan Permintaan HTTP**

1. **Detik 0**: User memasukkan URL situs web di Client dan menekan "Enter".
2. **Detik 1**: Client User menginisiasi koneksi dengan server tujuan menggunakan protokol TCP/IP. Proses ini melibatkan tiga langkah, yaitu perancangan koneksi, sinkronisasi urutan nomor urut, dan pertukaran informasi tentang ukuran jendela.

**Detik 2 - 3: Permintaan HTTP**

3. **Detik 2**: Setelah koneksi terbentuk, Client mengirimkan pesan SYN (synchronize) ke alamat IP server yang sesuai dan port 80 (port default untuk HTTP). Ini merupakan langkah pertama dalam proses TCP handshake.

4. **Detik 3**: User Client menerima pesan SYN-ACK dari server dan mengirimkan pesan ACK (acknowledge) sebagai tanggapan. Tahap ini menyelesaikan proses TCP handshake dan membuka koneksi TCP yang stabil antara peramban Anda dan server di port 80.

**Detik 4 - 8: Proses Server**

5. **Detik 4**: Setelah koneksi terbuka, User Client mengirimkan permintaan HTTP GET ke server untuk alamat URL yang diminta. Permintaan ini mencakup informasi seperti alamat URL lengkap dan header permintaan HTTP.

6. **Detik 5**: Jika sumber daya adalah halaman statis, server akan mengambil berkas tersebut dari sistem file atau memori cache, dan kemudian mempersiapkannya untuk pengiriman.

7. **Detik 6-7**: Jika sumber daya adalah halaman dinamis (misalnya, halaman web yang dihasilkan secara dinamis dari database), server akan menjalankan skrip atau program yang diperlukan untuk menghasilkan konten yang sesuai.

8. **Detik 8**: Server memasukkan konten yang dihasilkan ke dalam pesan respons HTTP, termasuk status kode (misalnya, 200 OK jika berhasil) dan header respons (seperti jenis konten dan panjang konten).

<img src='../assets/flowgraph-http-2.png'>
**Detik 9 - 12: Pengiriman Respons HTTP**

9. **Detik 9**: Respons HTTP, yang berisi konten yang diminta, dikirimkan kembali ke Client User melalui koneksi TCP yang sama.

10. **Detik 10**: Client User menerima respons HTTP dan memulai penguraian respons.

11. **Detik 11**: Jika respons berisi halaman HTML, Client User mulai memproses kode HTML, menampilkan teks, gambar, dan elemen lainnya secara bertahap.

12. **Detik 12**: Selama proses penguraian, Client User juga akan mengambil sumber daya tambahan yang diperlukan, seperti gambar, CSS, atau JavaScript yang disebutkan dalam kode HTML. Ini mungkin melibatkan permintaan tambahan ke server untuk mengunduh sumber daya ini.

**Detik 17 - 30: Menampilkan Halaman Web**

13. **Detik 17-30**: Selama Tahap ini, peramban Anda terus memuat dan menampilkan konten halaman web yang dihasilkan oleh server. Ini mencakup tindakan seperti memuat gambar, CSS, JavaScript, dan sumber daya lain yang diperlukan untuk menampilkan halaman dengan benar. Jika ada permintaan tambahan, mereka akan terjadi melalui koneksi TCP yang sama pada port 80.

## Analisis Packet Counter

<img src='../assets/packet-counter-http.png'>
Packet Counter adalah alat untuk memahami apa yang  terjadi di Internet dengan menghitung dan menampilkan paket atau bingkai selama pengambilan sesi atau  pemantauan jaringan.
Informasi penting mengenai lalu lintas jaringan disediakan yaitu jumlah total  paket, kecepatan paket masuk, pengiriman paket, kecepatan ledakan, durasi ledakan awal.

 Dari penangkapan penghitung paket di atas, dapat disimpulkan bahwa  4 paket HTTP telah dicatat, semuanya terkait dengan lalu lintas HTTP. Dari 4 paket ini, 2 merupakan permintaan  HTTP  menggunakan metode GET. Selebihnya merupakan respon dari web server, dengan seluruh respon mempunyai kode status HTTP  kategori 2xx (berhasil) yaitu “200 OK”. Tingkat ledakan untuk  permintaan dan tanggapan GET  adalah 0,0100 paket per detik, dengan tingkat ledakan pertama  dimulai pada waktu yang berbeda (0,911 detik untuk permintaan GET dan 3,956 detik untuk tanggapan). Rata-rata throughput masuk  adalah 0,0005 paket per milidetik. Jadi, tangkapan ini menunjukkan bahwa ada pertukaran data HTTP yang sebagian besar terdiri dari permintaan GET dan respons 200 OK yang berhasil. 

 ## Analisis Throughput

 <img src='../assets/throughput-http.png'>
 TCP Throughput adalah ukuran seberapa efektif data dapat ditransmisikan melalui koneksi TCP dalam suatu periode waktu tertentu. Ini mencerminkan jumlah data yang berhasil dikirim atau diterima melalui koneksi TCP dalam satuan data per waktu, seperti byte per detik atau bit per detik.

Dari gambar diatas, kita dapat melihat grafik throughput yang menggambarkan bagaimana throughput berubah selama sesi koneksi. Grafik throughput ini memungkinkan kita untuk memantau perubahan dalam kecepatan transmisi data selama waktu tertentu. Ini sangat berguna untuk mengidentifikasi puncak throughput, penurunan kinerja, atau tren dalam koneksi jaringan.

- Puncak pada grafik mengindikasikan titik-titik di mana throughput mencapai nilai tertinggi.
- Penurunan tajam atau fluktuasi throughput dapat mengindikasikan masalah dalam koneksi jaringan, seperti packet loss atau konflik.

Melalui grafik throughput ini, kita dapat dengan cepat mengidentifikasi tren dan perubahan dalam kinerja koneksi TCP. Ini bisa membantu kita dalam mengatasi masalah jaringan, memantau kinerja aplikasi, atau melakukan analisis lebih lanjut terhadap sesi koneksi yang spesifik.