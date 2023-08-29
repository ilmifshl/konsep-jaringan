## Apa Itu FTP?

 FTP (File Transfer Protocol) adalah layanan Internet yang dirancang untuk membuat koneksi dengan server Internet atau komputer tertentu, sehingga pengguna dapat mengirim file ke komputer (download) atau mengirim file ke server (upload). Server FTP kini banyak digunakan untuk bertukar data karena lebih mudah dibandingkan menggunakan perangkat fisik atau kabel.

## Mengapa ada dua protokol TCP dan UDP dalam satu port FTP?

Pertanyaan yang mungkin muncul adalah mengapa bisa ada dua protokol pada port FTP yang sama yaitu TCP (Transmission Control Protocol) dan UDP (User Datagram Protocol)? Untuk menjawab pertanyaan ini, kita perlu memahami struktur kerja FTP dan penggunaan masing-masing protokol tersebut.

 FTP, atau File Transfer Protocol, adalah protokol yang digunakan untuk mentransfer file antara klien dan server melalui jaringan komputer. Dalam kebanyakan kasus, FTP menggunakan  TCP sebagai protokol transport utama. TCP adalah protokol yang andal yang memastikan pengiriman data yang benar dan teratur. Hal ini dicapai dengan memastikan bahwa data dikirimkan ke tujuan yang  benar dan dalam urutan yang benar. Namun, ada situasi khusus ketika mengimplementasikan FTP, terutama dalam mode aktif, dimana protokol UDP juga dapat digunakan bersama dengan TCP. Mode FTP aktif terdiri dari dua koneksi terpisah antara klien dan server:
kontrol koneksi  dan koneksi data. Koneksi kontrol menggunakan protokol TCP untuk memproses perintah dan respons antara klien dan server, sedangkan koneksi data digunakan untuk mentransfer file sebenarnya.

 Pada tahap ini, penggunaan protokol UDP dalam koneksi data dapat dipertimbangkan. Ini ada hubungannya dengan kinerja dan kecepatan transfer. Dalam situasi di mana kecepatan transmisi lebih diutamakan daripada fidelitas absolut, misalnya dalam streaming video atau audio, protokol UDP dapat diterapkan. UDP memiliki overhead yang lebih sedikit  dibandingkan  TCP karena tidak melibatkan mekanisme transmisi ulang untuk menjamin keakuratan data. Oleh karena itu, UDP dapat memungkinkan transmisi data lebih cepat.

 Namun, perlu ditekankan bahwa penggunaan UDP dalam mode  FTP bukanlah praktik  atau standar umum. TCP tetap menjadi pilihan utama dalam banyak kasus karena keandalan dan jaminan pengiriman yang ditawarkannya. TCP memastikan bahwa data dikirim dengan benar dan dalam urutan yang benar, namun ada penundaan tambahan karena mekanisme transmisi ulang.

 Singkatnya, memilih antara menggunakan protokol TCP atau UDP dalam mode FTP aktif harus didasarkan pada kebutuhan spesifik. Jika kecepatan transfer lebih penting daripada akurasi absolut, maka  UDP dapat dipertimbangkan, namun waspadai risiko kehilangan  atau gangguan data. Dalam kebanyakan kasus, FTP masih mengandalkan protokol TCP untuk kedua jenis koneksi tersebut karena keandalan dan akurasi data tetap menjadi prioritas utama dalam transfer file.