**LAPORAN PRAKTIKUM KONSEP JARINGAN**
> Kelas : 2 D4 IT A
>
> Tugas Kelompok BGP
> Nama : Ahmad Shonhaji (3121600025)
> Nama : Muhammad Rizqy Ferdiansyah (3121600024)
>

# A. TOPOLOGI

[![Topologi.png](https://i.postimg.cc/W1NcPdjv/Topologi.png)](https://postimg.cc/Yhss6qhn)

Topologi di atas terdiri dari 10 Router. R1 sebagai router utama yang akan terhubung ke AS Number yang lain. Area R2 menggunakan routing protocol RIP, area R3 menggunakan OSPF, area R4 menggunakan Static Routing, sementara untuk menghubungkan area R2, R3, dan R4 menggunakan routing protocol BGP yang terhubung ke router pusat yakni R1.

| Devices |   IP Address    | CIDR |     Network     | Interface |
| :-----: | :-------------: | :--: | :-------------: | :-------: |
|   R1    |   14.14.14.1    |  24  |   14.14.14.0    |  ether2   |
|         |   13.13.13.1    |  24  |   13.13.13.0    |  ether3   |
|         |   12.12.12.1    |  24  |   12.12.12.0    |  ether4   |
|   R2    |   12.12.12.2    |  24  |   12.12.12.0    |  ether1   |
|         |   27.27.27.2    |  24  |   27.27.27.0    |  ether2   |
|         |   28.28.28.2    |  24  |   28.28.28.0    |  ether3   |
|   R3    |   13.13.13.3    |  24  |   13.13.13.0    |  ether1   |
|         |   36.36.36.3    |  24  |   36.36.36.0    |  ether2   |
|         |   35.35.35.3    |  24  |   35.35.35.0    |  ether3   |
|   R4    |   14.14.14.4    |  24  |   14.14.14.0    |  ether1   |
|         |   41.41.41.4    |  24  |   41.41.41.0    |  ether2   |
|         |   49.49.49.4    |  24  |   49.49.49.0    |  ether3   |
|   R5    |   35.35.35.5    |  24  |   35.35.35.0    |  ether1   |
|         |   50.50.50.50   |  -   |   50.50.50.50   |    lo0    |
|   R6    |   36.36.36.6    |  24  |   36.36.36.0    |  ether1   |
|         |   60.60.60.60   |  -   |   60.60.60.60   |    lo0    |
|   R7    |   27.27.27.7    |  24  |   27.27.27.0    |  ether1   |
|         |   70.70.70.70   |  -   |   70.70.70.70   |    lo0    |
|   R8    |   28.28.28.8    |  24  |   28.28.28.0    |  ether1   |
|         |   80.80.80.80   |  -   |   80.80.80.80   |    lo0    |
|   R9    |   49.49.49.9    |  24  |   49.49.49.0    |  ether1   |
|         |   90.90.90.90   |  -   |   90.90.90.90   |    lo0    |
|   R10   |   41.41.41.10   |  24  |   41.41.41.0    |  ether1   |
|         | 100.100.100.100 |  -   | 100.100.100.100 |    lo0    |

# B. Ruang Lingkup Kerja

Dalam pratikum kali ini kelompok kami terdiri dari Ahmad Shonhaji (3121600025), Muhammad Rizqy Ferdiansyah (3121600024), bertugas untuk mengatur router R10 yng menggunakan routing RIP sesuai area yang telah ditentukan. Kami melakukan konfigurasi routing tersebut dengan perintah sebagai berikut:

> tambah alamat addres untuk router 10 dan route ke r4 : 

> /interface bridge
> add name=lo0
> /ip address
> add address=41.41.41.10/24 interface=ether1 network=41.41.41.0
> add address=100.100.100.100 interface=lo0 network=100.100.100.100

>Setting RIP
>/ip route
>add distance=1 gateway=41.41.41.4

# C. Table Routing

[![7.png](https://i.postimg.cc/DyspYnXK/7.png)](https://postimg.cc/Ln9VJdDy)

Terlihat dengan perintah ip route print untuk melihat isi tabel routing, bahwa router R10 sudah terhubung dengan router R4 dan R9 yang menggunakan routing protocol RIP. Selain itu juga terhubung dengan router R2 yang menggunakan routing protocol BGP. Karena terhubung dengan R1 yang menggunakan protocol BGP pada router R2-R4, maka router R10 juga menerima table routing yang otomatis terhubung juga dengan R1.

# D. Test Koneksi

> dengan Router 1
[![2.png](https://i.postimg.cc/t4gb0stx/2.png)](https://postimg.cc/rK73xFHV)

> dengan Router 9
[![3.png](https://i.postimg.cc/s2Zty7Bv/3.png)](https://postimg.cc/XZ42kZkb)

> dengan Router 2
[![5.png](https://i.postimg.cc/W1xH9z9j/5.png)](https://postimg.cc/Sn7dRSFt)

dengan Router 3
[![6.png](https://i.postimg.cc/sX4HDc3D/6.png)](https://postimg.cc/8JsmZLFq)

Gambar-gambar di atas merupakan test koneksi dengan perintah ping ke IP Address yang telah ditentukan.

Berhasil melakukan ping ke IP Address pada router R2 (12.12.12.2), R3 (13.13.13.3), R1 (14.14.14.1), R9 (49.49.49.9) yang tentu saja berhasil karena sudah memiliki routing tabel dengan tujuan ke network berikut.

Gagal melakukan ping ke IP Address pada router R7 (27.27.27.7) dan R8 (28.28.28.8) serta R9 (49.49.49.9) karena tidak memiliki routing tabel dengan tujuan ke network di atas. Sepertinya masalah karena tidak menerima routing tabel dari R2 dan R4 secara penuh, hanya menerima routing tabel sebatas dengan router R1 saja.







