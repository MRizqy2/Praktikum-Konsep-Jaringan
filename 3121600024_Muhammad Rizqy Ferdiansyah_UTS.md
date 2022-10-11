# Laporan Praktikum Konsep Jaringan (UTS)

Muhammad Rizqy Ferdiansyah (3121600024)

2-D4 IT A

# 

## Topologi

![Topologi.png](https://i.postimg.cc/NMBwqCxy/Topologi.png)

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

![vlanconf.png](https://i.postimg.cc/wB3LDBn7/vlanconf.png)

- Konfigurasi switch 0

![switch0-fa10.png](https://i.postimg.cc/25XdtWnQ/switch0-fa10.png)

- Konfigurasi switch 1

![switch1-fa10.png](https://i.postimg.cc/jSDSXJd0/switch1-fa10.png)

![switch1-fa11.png](https://i.postimg.cc/Tw62f7jf/switch1-fa11.png)

![switch1-fa12.png](https://i.postimg.cc/RFSrgjQ6/switch1-fa12.png)

- Konfigurasi switch 2

![switch2-fa10.png](https://i.postimg.cc/pdkcLyzr/switch2-fa10.png)

- Konfigurasi pada router

![gig0.png](https://i.postimg.cc/wM1XHjcC/gig0.png)

- Testing ping PC-10.4 ke PC-10.2

![test-ping.png](https://i.postimg.cc/05LvsH93/test-ping.png)

Pada testing diatas PC-10.4 ke PC-10.2 sukses dilakukan karena PC-10.4 memiliki vlan yang sama dengan PC-10.2 yaitu vlan 10.
