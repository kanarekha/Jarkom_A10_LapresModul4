# Jarkom_A10_LapresModul4

Anggota :

Kana Rekha 05111840000001

Abdul Rozak Baharudin 05111840000148	

# VLSM
* Membuat topologi di Cisco Packet Tracer sesuai soal.

* Menambahkan port NM-2FE2W pada semua router .Khusus untuk router SURABAYA tambahkan port NM-4E.

* Sambungkan kabel antara sesama router atau dengan switch.

* Mengelompokkan router dan switch yang ada. Namun untuk sesama router tidak diperbolehkan untuk berada pada satu kelompok. Pengelompokkan subnet seperti pada gambar berikut ini:

![SUBNET](https://user-images.githubusercontent.com/57948206/101988975-cb33d280-3ccf-11eb-8608-fb0dde967e38.jpg)

* Setelah menghitung jumlah subnet, dapat menghitung jumlah ip yang akan dipakai dan labelling netmask seperti gambar berikut :

<img width="236" alt="jml ip" src="https://user-images.githubusercontent.com/57948206/101989280-ddaf0b80-3cd1-11eb-80b6-28fabf8a8f69.PNG">

* Selanjutnya menghitung pembagian IP berdasarkan NID dan netmask tersebut menggunakan diagram pohon seperti gambar di bawah.

![pohon vlsm (1)](https://user-images.githubusercontent.com/57948206/101988972-c96a0f00-3ccf-11eb-8d12-823bcdc0229a.jpg)

* Untuk server memakai 2 ip yang diperoleh dari ip DMZ tiap kelompok dan Cloud memakai ip tuntap tiap kelompok .

* Atur IP untuk masing-masing interface yang ada di setiap device sesuai dengan pembagian subnet pada VLSM. Interface dapat diatur pada menu Config -> Interface > “nama interface” (contoh: FastEthernet0/0). Kemudian, isi alamat IP dan subnet mask dari subnet interface tersebut. Berikut contoh untuk mengatur IP pada subnet A1.
Atur IP pada interface BLITAR yang mengarah ke client TULUNGAGUNG .

<img width="560" alt="router" src="https://user-images.githubusercontent.com/57948206/101989666-9aa26780-3cd4-11eb-8ed5-a459bff3897a.PNG">

* Kemudian atur IP pada salah satu client, yaitu TULUNGAGUNG yang mengarah ke BLITAR.

<img width="557" alt="pc" src="https://user-images.githubusercontent.com/57948206/101989664-9a09d100-3cd4-11eb-85eb-a9c03c5f938b.PNG">

* Ulangi langkah di atas untuk setiap router, dan juga client lain yang ada.

* Melakukan routing di setiap router yang ada. Routing dapat dilakukan pada menu Config > Routing > Static pada device Router. Lalu, isilah static routes seperti gambar dibawah pada SURABAYA dan tekan tombol 'Add':

<img width="555" alt="static" src="https://user-images.githubusercontent.com/57948206/101989667-9aa26780-3cd4-11eb-973a-2546264112c6.PNG">

* Pada static routing juga dibutuhkan default routing agar router dapat mengirimkan paket sesuai dengan tujuan. Default routing dibutuhkan untuk router yang berada di bawah router utama. contoh : BLITAR

<img width="558" alt="default" src="https://user-images.githubusercontent.com/57948206/101989662-98d8a400-3cd4-11eb-88e9-cba3ca622f53.PNG">

* Agar semua subnet dapat saling terhubung, tambahkan static routing berikut:

SURABAYA
```
192.168.0.16/28 via 192.168.0.6
192.168.2.0/23 via 192.168.0.6
192.168.8.0/22 via 192.168.0.6
192.168.0.0/30 via 192.168.0.6
192.168.1.0/24 via 192.168.0.6
192.168.4.0/22 via 192.168.0.6
192.168.12.0/22 via 192.168.0.10
192.168.0.12/30 via 192.168.0.10
192.168.0.128/25 via 192.168.0.10
192.168.24.0/21 via 192.168.0.10
10.151.73.92/30 via 192.168.0.6
```

PASURUAN
```
192.168.0.128/25 via 192.168.0.14
192.168.16.0/21 via 192.168.0.14
0.0.0.0/0 via 192.168.0.9
```

PROBOLINGGO
```
0.0.0.0/0 via 192.168.0.13
```

BATU 
```
192.168.0.16/28 via 192.168.2.3
192.168.4.0/22 via 192.168.0.2
192.168.1.0/24 via 192.168.0.2
10.151.73.92/30 via 192.168.0.2
0.0.0.0/0 via 192.168.0.5
```

MADIUN
```
0.0.0.0/0 via 192.168.2.1
```

KEDIRI
```
192.168.4.0/22 via 192.168.1.3
0.0.0.0/0 via 192.168.0.1
```

BLITAR
```
0.0.0.0/0 via 192.168.1.1
```
* Melakukan ping test dengan cara klik logo surat di bagian menu. Apabila berhasil mengasilkan output success dan failed apabila gagal. Contoh : ping SURABAYA KE SAMPANG

<img width="286" alt="yey" src="https://user-images.githubusercontent.com/57948206/101990371-42ba2f80-3cd9-11eb-99e3-e05b81530202.PNG">

# CIDR
* Membuat perhitungan untuk pada topologi menggunakan metode CIDR
* Melakukan pengelompokan dengan yang bersebelahan
![a](https://github.com/kanarekha/Jarkom_A10_LapresModul4/blob/main/img/a.png)
* Lalu mengelompokkan ke tahap selanjutnya dengan menggabungkan yang paling ujung
![a-b](https://github.com/kanarekha/Jarkom_A10_Modul3/blob/main/img/a-b.png)
* Lanjutkan pengelompokan sampai semua masuk kedalam pengelompokkan kecuali MOJOKERTO dan MALANG, karena IP yang akan digunakan oleh keduanya didapat dari NID DMZ
![c](https://github.com/kanarekha/Jarkom_A10_Modul3/blob/main/img/c.png)
![d](https://github.com/kanarekha/Jarkom_A10_Modul3/blob/main/img/d.png)
![e](https://github.com/kanarekha/Jarkom_A10_Modul3/blob/main/img/e.png)
![e-f](https://github.com/kanarekha/Jarkom_A10_Modul3/blob/main/img/e-f.png)
![g](https://github.com/kanarekha/Jarkom_A10_Modul3/blob/main/img/g.png)
* Setelah melakukan pengelompokan, selanjutnya dilakukan perhitungan untuk pembagian address pada setiap UML dan setiap pengelompokan
![cidr](https://github.com/kanarekha/Jarkom_A10_Modul3/blob/main/img/cidr.png)
* Selanjutnya adalah setting interface pada setiap UML, berikut adalah setting interface pada UML SURABAYA
```
#cloud
auto eth0
iface eth0 inet static
address 10.151.72.46
netmask 255.255.255.252
gateway 10.151.72.45

#sampang
auto eth1
iface eth1 inet static
address 192.168.4.1
netmask 255.255.252.0

#pasuruan
auto eth2
iface eth2 inet static
address 192.168.1.1
netmask 255.255.255.252

#batu
auto eth3
iface eth3 inet static
address 192.168.50.1
netmask 255.255.255.252

#mojokerto
auto eth4
iface eth4 inet static
address 10.151.73.89
netmask 255.255.255.252
```
* Untuk setting interface pada UML lainnya akan ada pada file di repository ini
* Selanjutnyan adalah melakukan routing, yang pertama akan di routing adalah SURABAYA ke PASURUAN, BATU dan MALANG(karena MALANG berada di luar subnet G1)
```
#pasuruan D2/18
route add -net 192.168.128.0 netmask 255.255.192.0 gw 192.168.192.2
#batu D1/19
route add -net 192.168.0.0 netmask 255.255.224.0 gw 192.168.32.2
#malang
route add -net 10.151.73.92 netmask 255.255.255.252 gw 192.168.32.2
```
* Karena PASURUAN belum kenal dengan BONDOWOSO, JEMBER dan BANYUWANGI, maka PASURUAN melakukan routing kepada router PROBOLINGGO yang mengenal BONDOWOSO, JEMBER dan BANYUWANGI setelah pengelompokan B2/20
```
#probilinggo B2/20
route add -net 192.168.128.0 netmask 255.255.240.0 gw 192.168.144.2

```
* Karena BATU belum kenal semua yang berada di bagian kiri dan di bagian bawah, maka dilakukan routing pada router MADIUN dan KEDIRI. BATU juga routing pada MALANG agar bisa terhubung kepada SURABAYA
```
#kediri B1/21
route add -net 192.168.0.0 netmask 255.255.248.0 gw 192.168.8.2
#madiun A5/28
route add -net 192.168.16.0 netmask 255.255.252.0 gw 192.168.18.3
#malang pada kediri
route add -net 10.151.73.92 netmask 255.255.255.252 gw 192.168.8.2
```
* Karena KEDIRI masih belum mengenal TULUNGAGUNG, maka dilakukan route pada KEDIRI kepada router BLITAR pada pengelompokan A1/22
```
#blitar
route add -net 192.168.0.0 netmask 255.255.248.0 gw 192.168.4.3
```
