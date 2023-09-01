## Mengakses Packet Gambar pada HTTP

**1. Buka file sample http_with_jpegs.cap menggunakan Wireshark dan filter HTTP** 
<img src='../assets/httpjpegs_filter_http.png'>

**2. Cari packet yang memiliki info "200 OK (JPEG JFIF image)"**
<img src='../assets/packet-info.png'>

**3. Pilih paket tersebut dan klik kanan pada  "JPEG file interchange format" yang terletak pada window di bagian kiri bawah, lalu pilih "Show Packet Bytes..."**
<img src='../assets/jpeg-file-interchange.png'>
<img src='../assets/show-packet-bytes.png'>

**4. Wireshark akan menampilkan gambar yang terdapat pada packet tersebut**
<img src='../assets/packet-61.png'>

---

Terdapat lima packet yang memuat data gambar pada sampel file tersebut. Berikut adalah gambar-gambar yang dimuat pada lima packet tersebut.

<p align="center">
<img src="../assets/packet-72.png" alt="72">
<br>
<i>Packet No. 72</i>
</p>

<br>

<p align="center">
<img src="../assets/packet-259.png" alt="259">
<br>
<i>Packet No. 259</i>
</p>

<br>

<p align="center">
<img src="../assets/packet-269.png" alt="269">
<br>
<i>Packet No. 269</i>
</p>

<br>

<p align="center">
<img src="../assets/packet-479.png" alt="479">
<br>
<i>Packet No. 479</i>
</p>

