# Laporan Praktikum Konsep Jaringan Minggu ke 4

Muhammad Rizqy Ferdiansyah (3121600024)

2-D4 IT A

# Static Routing

## A. Percobaan Static Routing

Berikut merupakan topologi dari static routing yang membutuhkan 2 pc dan 2 router dengan subneting.

![Topologi.png](https://i.postimg.cc/ZnJ0kxVh/Topologi.png)

Konfigurasi IP yang akan digunakan sebagai berikut :

| Perangkat | Interface | IP Address     | Gateway     |
| --------- | --------- | -------------- | ----------- |
| PC0       | fa0       | 192.168.1.2/24 | 192.168.1.1 |
| PC1       | fa0       | 192.168.3.3/24 | 192.168.3.2 |
| Router0   | Gig0/1    | 192.168.1.1/24 |             |
|           | Gig0/0    | 192.168.2.1/24 |             |
| Router1   | Gig0/0    | 192.168.2.2/24 |             |
|           | Gig0/1    | 192.168.3.2/24 |             |

Kita juga membutuhkan konfigurasi router staticnya. berikut konfigurasi routing staticnya :

Router0

- ip route 192.168.3.0 - 255.255.255.0 - 192.168.2.2

Router1

- ip route 192.168.1.0 - 255.255.255.0 - 192.168.2.1

Konfigurasi router diperlukan untuk menentukan rute yang dapat dilalui oleh paket saat mencari tujuan menggunakan jaringan yang sudah ada.

Percobaan ping dari PC-0 ke PC-1

![Ping1.png](https://i.postimg.cc/fLbZNqYZ/Ping1.png)

Pada Percobaan diatas terjadi RTO 2 kali pada ping pertama dan ping kedua disebabkan terjadinya arp pada saat broadcast domain antara PC-0 dengan router0 dan terjadi brodcast lagi pada saat ping kedua antara router0 an router1. Pada ping ketiga baru terhubung langsung sebab proses arp sudah selesai.

## B. Percobaan 1 router 2 Jaringan

Berikut merupakan topologi dari 2 jaringan yang terhubung ke sebuah router yang sama.

![Topologi2.png](https://i.postimg.cc/XJgx0391/Topologi2.png)

Konfigurasi IP yang akan digunakan sebagai berikut :

| Perangkat | Interface | IP Address     | Gateway     |
| --------- | --------- | -------------- | ----------- |
| PC0       | fa0       | 192.168.1.2/24 | 192.168.1.1 |
| PC1       | fa0       | 192.168.1.3/24 | 192.168.1.1 |
| PC2       | fa0       | 192.168.2.2/24 | 192.168.2.1 |
| PC3       | fa0       | 192.168.2.3/24 | 192.168.2.1 |
| Router0   | Gig0/1    | 192.168.1.1/24 |             |
|           | Gig0/0    | 192.168.2.1/24 |             |

Percobaan ping dari PC-0 ke PC-2 yang memiliki jaringan berbeda.

![Ping2.png](https://i.postimg.cc/qvZLkjh0/Ping2.png)

Pada Percobaan diatas PC-0 dan PC-2 otomasi akan terhubung sebelum menambahkan routing manual sebab routing pada jaringan akan terjadi secara otomatis saat kita menambahkan ip ke router yang dinamakan directly connected.
