# Laporan Praktikum Konsep Jaringan Minggu ke 6

Muhammad Rizqy Ferdiansyah (3121600024)

2-D4 IT A

# VLAN Trunk

## Topologi

![topologi](assets/topologi.png)

Konfigurasi IP yang digunakan :

| Device   | Interface    | IP Address      | Gateway      |
| -------- | ------------ | --------------- | ------------ |
| Router0  | gig0/0       | 192.17.1.1/24   |              |
| pc0      | vlan10       | 192.168.10.2/24 | 192.168.10.1 |
| pc1      | vlan20       | 192.168.20.3/24 | 192.168.20.1 |
| pc2      | vlan30       | 192.168.30.4/24 | 192.168.30.1 |
| pc3      | vlan10       | 192.168.10.2/24 | 192.168.10.1 |
| pc4      | vlan20       | 192.168.20.3/24 | 192.168.20.1 |
| pc5      | vlan30       | 192.168.30.4/24 | 192.168.30.1 |
| pc6      | vlan10       | 192.168.10.2/24 | 192.168.10.1 |
| pc7      | vlan20       | 192.168.20.3/24 | 192.168.20.1 |
| pc8      | vlan30       | 192.168.30.4/24 | 192.168.30.1 |

| Device   | Interface    | IP Address      | Gateway      |
| -------- | ------------ | --------------- | ------------ |
| Switch 0 | fa0/1 vlan10 |                 |              |
|          | fa0/2 vlan20 |                 |              |
|          | fa0/3 vlan30 |                 |              |
|          | fa0/10 trunk |                 |              |
| Switch 1 | fa0/1 vlan10 |                 |              |
|          | fa0/2 vlan20 |                 |              |
|          | fa0/3 vlan30 |                 |              |
|          | fa0/10 trunk |                 |              |
|          | fa0/11 trunk |                 |              |
|          | fa0/12 trunk |                 |              |
| Switch 2 | fa0/1 vlan10 |                 |              |
|          | fa0/2 vlan20 |                 |              |
|          | fa0/3 vlan30 |                 |              |
|          | fa0/10 trunk |                 |              |

Konfigurasi pada switch 1 supaya dapat terhubung dengan switch 0 dan switch 2 yang terhbung juga deng router.

| Nama Divisi | Segmen IP    |
|-------------|--------------|
| Admin       |192.168.1.0/24|
| Developer   |192.168.2.0/24|
| Management  |192.168.3.0/24|

![switch vlan config](assets/vlan%20config.png)

konfigurasi switch 0

![config switch0 fa0/10](assets/sw0%20fa10.png)

konfigurasi switch 1

![config switch1 fa0/10](assets/sw1%20fa10.png)

![config switch1 fa0/11](assets/sw1%20fa11.png)

![config switch1 fa0/12](assets/sw1%20fa12.png)

konfigurasi switch 2

![config switch2 fa0/10](assets/sw2%20fa10.png)

konfigurasi pada router

![config router gig0/0](assets/gig%200.png)

Testing ping PC-10.4 ke PC-10.2 dan PC-10.4 ke PC30.3

![ping](assets/test%20ping.png)

Pada testing ping diatas saat PC-10.4 ke PC-10.2 sukses dilakukan karena PC-10.4 memiliki vlan yang sama dengan PC-10.2 yaitu vlan 10, sedangkan saat melakukan ping dari PC-10.4 ke PC30.3 tidak sukses karena vlan yang digunakan berbeda PC-10.4 menggunakan vlan 10 dan PC30.3 menggunakan vlan 30 sehingga ping yang dikirim tidak akan perna sampai.
