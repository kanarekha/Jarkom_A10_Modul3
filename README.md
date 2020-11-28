# Jarkom_A10_LapresModul3

Anggota :

Kana Rekha 05111840000001

Abdul Rozak Baharudin 05111840000148	

- [Lapres_modul3_A10](#lapres_modul3_A10)
	- [Soal 1](#soal-2)
	- [Soal 2](#soal-2)
	- [Soal 3](#soal-3)
	- [Soal 4](#soal-4)
	- [Soal 5](#soal-5)
	- [Soal 6](#soal-6)
	- [Soal 7](#soal-7)
	- [Soal 8](#soal-8)
	- [Soal 9](#soal-9)
	- [Soal 10](#soal-10)
 	- [Soal 11](#soal-11)
	- [Soal 12](#soal-12)
	- [Soal 13](#soal-13)
	
## Soal 1
* Setting ```nano topologi.sh``` seperti pada gambar
![1-1](https://github.com/kanarekha/Jarkom_A10_Modul3/blob/main/img/1-1.jpg)
* jangan lupa untuk menambahkan halt untuk uml yang ada pada topologi.sh

## Soal 2
* pada UML TUBAN setting ```nano /etc/default/isc-dhcp-server``` dengan menambahkan ```INTERFACESv4="eth0"```

## Soal 3
* pada UML TUBAN ```nano /etc/dhcp/dhcpd.conf``` lalu tambahkan untuk subnet 1 seperti pada gambar
![3-1](https://github.com/kanarekha/Jarkom_A10_Modul3/blob/main/img/3-1.jpg)
* ```range 192.168.0.10 192.168.0.100; range 192.168.0.110 192.168.0.200;```

## Soal 4
* pada ```nano /etc/dhcp/dhcpd.conf``` ditambahkan untuk subnet 3 seperti pada gambar
![4-1](https://github.com/kanarekha/Jarkom_A10_Modul3/blob/main/img/4-1.jpg)
* ```range 192.168.1.50 192.168.0.70;```

## Soal 5
* pada UML client di file ```nano /etc/resolv.conf``` ditambahkan ```nameserver "IP_MALANG"``` dan ```nameserver 202.46.129.2```

## Soal 6
* pada UML TUBAN ```nano /etc/dhcp/dhcpd.conf``` dan tambahkan ```default-lease-time 300;```
 dan ```max-lease-time 300;``` pada subnet 192.168.0.0 atau subnet 1
![6-1](https://github.com/kanarekha/Jarkom_A10_Modul3/blob/main/img/6-1.jpg)
## Soal 7
* pada UML TUBAN ```nano /etc/dhcp/dhcpd.conf``` dan tambahkan ```default-lease-time 600;```
 dan ```max-lease-time 600;``` pada subnet 192.168.1.0 atau subnet 3
![7-1](https://github.com/kanarekha/Jarkom_A10_Modul3/blob/main/img/7-1.jpg)

## Soal 8
* Install squid3 pada UML MOJOKERTO ```apt-get install squid3```
* Install apache2-utils pada UML MOJOKERTO ```apt-get install apache2-utils```
* Backup terlebih dahulu file konfigurasi default yang disediakan squid ```mv /etc/squid3/squid.conf /etc/squid3/squid.conf.bak```
* Membuat user dan password baru. Lakukan setting pada ```htpasswd -c /etc/squid/passwd userta_a10``` dengan password: inipassw0rdta_a10
* Edit konfigurasi squid menjadi , Tambahkan konfigurasi seperti di bawah ini :

```
http_port 8080
visible_hostname mojokerto

auth_param basic program /usr/lib/squid3/ncsa_auth /etc/squid3/passwd
auth_param basic children 5
auth_param basic realm Proxy
auth_param basic credentialsttl 2 hours
auth_param basic casesensitive on
acl USERS proxy_auth REQUIRED
http_access allow USERS
```
* Restart squid dengan cara mengetikkan perintah ```service squid3 restart```
## Soal 9
* Buka ```nano /etc/squid3/squid.conf```pada UML MOJOKERTO lalu tambahkan konfigurasi ```acl AVAILABLE time TW 13:00-18:00```
* Restart squid dengan cara mengetikkan perintah ```service squid3 restart```

## Soal 10
* Buka ```nano /etc/squid3/squid.conf``` pada UML MOJOKERTO lalu tambahkan konfigurasi berikut :
```
acl AVAILABLE_1 time TWH 21:00-23:59
acl AVAILABLE_2 time WHF 00:00-09:00
```
* Restart squid dengan cara mengetikkan perintah ```service squid3 restart```

## Soal 11
* Buka ```nano /etc/squid3/squid.conf``` pada UML MOJOKERTO lalu tambahkan konfigurasi berikut :
```
acl roket dstdomain .google.com
deny_info http://monta.if.its.ac.id roket
http_reply_access deby roket
```
* Restart squid dengan cara mengetikkan perintah ```service squid3 restart```

<img width="361" alt="squid" src="https://user-images.githubusercontent.com/57948206/100496896-6f733080-318a-11eb-9b62-b58247be71f5.PNG">

## Soal 12
* buka UML MOJOKERTO dan pindah ke directory ```cd /usr/share/squid3/errors/English``` dan wget ```wget 10.151.36.202/ERR_ACCESS_DENIED``` lalu coba buka pada browser
![12-1](https://github.com/kanarekha/Jarkom_A10_Modul3/blob/main/img/12-1.jpg)

## Soal 13
* Install aplikasi bind9 pada UML MALANG dengan perintah ```apt-get install bind9 -y```
* Buka ```nano /etc/bind/named.conf.local``` . Edit konfigurasi sebagai berikut :

<img width="363" alt="conf" src="https://user-images.githubusercontent.com/57948206/100496892-6d10d680-318a-11eb-98e0-af766be93bfc.PNG">

* Buat folder jarkom di dalam /etc/bind dengan perintah ```mkdir /etc/bind/jarkom```
* Copykan file db.local ke dalam folder janganlupa-ta.a10.pw dengan perintah ```cp /etc/bind/db.local /etc/bind/jarkom/janganlupa-ta.a10.pw```
* Buka file ```nano /etc/bind/jarkom/janganlupa-ta.a10.pw``` dan edit konfigurasi sebagai berikut :

<img width="364" alt="jarkom jangan" src="https://user-images.githubusercontent.com/57948206/100496894-6e420380-318a-11eb-9138-1891fda1ee64.PNG">
 
 * Restart bind9 dengan perintah ```service bind9 restart```
 * Atur proxy di firefox seperti gambar berikut :
 
 <img width="577" alt="proxy" src="https://user-images.githubusercontent.com/57948206/100496895-6eda9a00-318a-11eb-82ab-c13008cab951.PNG">
 
 
 
 
 
 
 
