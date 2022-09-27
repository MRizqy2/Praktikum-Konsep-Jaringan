# Laporan Praktikum Konsep Jaringan Minggu ke 5

Muhammad Rizqy Ferdiansyah (3121600024)

2-D4 IT A

# VLAN

## A. Pengertian VLAN

VLAN adalah virtual local area network atau suatu model jaringan yang tidak terbatas pada lokasi fisik seperti LAN, hal ini mengakibatkan suatu network dapat dikonfigurasi secara virtual tanpa harus menuruti lokasi fisik peralatan. Penggunaan VLAN akan membuat pengaturan jaringan menjadi sangat fleksibel karena dapat dibuat segmen yang bergantung pada organisasi, tanpa bergantung lokasi workstations, eperti kita ketahui bahwa switch tidak bisa membaca Layer 3 sehingga tidak bisa membaca Network sehingga hanya bisa dihubungkan hanya satu network saja.

## Kegunaan VLAN

- Menimalisir kemungkinan terjadinya konflik IP yang terlalu banyak.
- Mencegah terjadinya collision domain (tabrakan domain).
- Mengurangi tingkat vulnerabilities.

## Percobaan Topologi

![Topologi.png](https://i.postimg.cc/m29X7GjF/Topologi.png)

- Topologi di atas terdiri dari 1 router, 1 switch, dan 3 pc-client dengan 2 VLAN (172.17.10.11 - 10 [VLAN10] & 172.17.30.11 - 30 [VLAN30]) dan 1 Non-VLAN (172.17.1.1).

Konfigurasi IP yang akan digunakan sebagai berikut :

| Device  | Interface | IP Address      | Gateway      |
| ------- | --------- | --------------- | ------------ |
| Router0 | vlan10    | 172.17.10.1/24  |              |
|         | vlan30    | 172.17.30.1/24  |              |
| pc0     | fa0/1     | 172.17.10.21/24 | 172.17.10.24 |
| pc1     | fa0/3     | 172.17.30.23/24 | 172.17.30.24 |

- Vlan 10 akan melalui port gi0/0 pada router dan port fa0/3 pada switch, sedangkan vlan 30 akan melalui port gi0/1 pada router dan port fa0/4 pada switch

![gi0-0.png](https://i.postimg.cc/T2smfLrr/gi0-0.png)

![gi0-1.png](https://i.postimg.cc/ZRcG6zLS/gi0-1.png)

- Konfigurasi pada switch supaya dapat terhubung dengan jaringan dari router ke pc tujuan. PC0 terhubung dengan switch pada port fa0/1 yang memiliki akses vlan 10 dan PC1 terhubung dengan switch pada port fa0/3 yang memiliki akses vlan 30

![vlan-config.png](https://i.postimg.cc/hGPDws3c/vlan-config.png)

![fe0-1.png](https://i.postimg.cc/5t0HvfJB/fe0-1.png)

![fe0-2.png](https://i.postimg.cc/8znp2M8v/fe0-2.png)

![fe0-3.png](https://i.postimg.cc/1Rc99Lhs/fe0-3.png)

![fe0-4.png](https://i.postimg.cc/445gCVV3/fe0-4.png)

- Testing ping PC0 ke PC1

![ping-1.png](https://i.postimg.cc/Hk3zdW3X/ping-1.png)
