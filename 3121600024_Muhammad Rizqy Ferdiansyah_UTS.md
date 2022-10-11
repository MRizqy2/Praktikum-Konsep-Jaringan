# Laporan Praktikum Konsep Jaringan (UTS)

Muhammad Rizqy Ferdiansyah (3121600024)

2-D4 IT A

Diketahui desain sebuah jaringan 2 lantai digambarkan dalam Gambar 1.  Sedangkan konfigurasi detil terdapat pada Tabel 1. Tugas anda adalah mengkonfigurasi seluruh perangkat sehingga seluruh PC yang ada dapat saling terhubung. Buatlah simualsinya dengan menggunakan packet tracer.

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

Setelah anda berhasil mengkonfigurasi seluruh perangkat dan terhubung satu sama lain, maka salin konfigurasi yang ada dan beri penjelasan singkat dari konfigurasi yang telah anda lakukan !

- Konfigurasi Router0
- Konfigurasi Switch0
- Konfigurasi Switch1
- 
