 # Laporan Praktikum Konsep Jaringan Praktikum 9

Muhammad Rizqy Ferdiansyah (3121600024)

2-D4 IT A

## Topologi

Berikut topologi yang di gunakan:

![Topologi.png](https://i.postimg.cc/Y2566gQZ/Topologi.png)

Dari topologi diatas kita dapat membuat tabel konfigurasi seperti berikut:

| No  | Device name | Interface name | IP Address/subnet mask | Additional Information     |
| --- | ----------- | -------------- | ---------------------- | -------------------------- |
| 1   | Router 0    | fa0/0          | 192.168.2.2/24         | dest network : 192.168.2.0 |
|     |             | fa0/1          | 192.168.1.2/24         | dest network : 192.168.1.0 |
| 2   | Router 1    | fa0/0          | 192.168.1.1/24         | dest network : 192.168.1.0 |
|     |             | fa0/1          | 192.168.3.2/24         | dest network : 192.168.3.0 |
|     |             | fa0/2          | 192.168.5.1/24         | dest network : 192.168.5.0 |
| 3   | PC1         | fa0            | 192.168.5.2/24         | default gw : 192.168.5.1   |
| 4   | Router 2    | fa0/0          | 192.168.2.1/24         | dest network : 192.168.2.0 |
|     |             | fa0/1          | 192.168.3.1/24         | dest network : 192.168.3.0 |
|     |             | fa0/2          | 192.168.4.1/24         | dest network : 192.168.4.0 |
| 5   | PC0         | fa0            | 192.168.4.2/24         | default gw : 192.168.4.1   |

Untuk memberikan destination network untuk routing dinamis dapat menggunakan perintah berikut :

    RIPv1
    router rip
    network "ip destination"
    network "ip destination"

    RIPv2
    router rip
    version 2
    network "ip destination"
    network "ip destination"

Kita dapat melakukan trace packet dari jaringan 4.0 menuju 5.0 dengan memberikan perintah :

    tracert 192.168.5.2

- Pada cmd PC0

Hasil dari trace packet seperti berikut:



## Time Convergency

Konvergensi adalah suatu bahasan dalam dynamic routing yang mempunyai keadaan dimana ketika semua router telah mempunyai routing tabel mereka sendiri sacara tetap dan konsisten. Jaringan yang Convergence ketika semua router telah mendapatkan hasil lengkap dan akurat mengenai informasi jaringan. Waktu convergence adalah waktu saat semua router berbagi informasi, menghitung jalur terbaik, memperbaharui Routing tabel mereka. Jaringan tidak akan berhenti beroperasi sampai semua network mendapatkan status convergence, kebanyakan jaringan mempunyai waktu yang singkat untuk mengubah statusnya menjadi konvergensi. (Graziani & Johnson, 2008).
