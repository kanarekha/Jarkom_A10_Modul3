# Jarkom_A10_Modul3

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

## Soal 10
* Buka ```nano /etc/squid3/squid.conf``` pada UML MOJOKERTO lalu tambahkan konfigurasi berikut :
```
acl roket dstdomain .google.com
deny_info http://monta.if.its.ac.id roket
http_reply_access deby roket
```
* Restart squid dengan cara mengetikkan perintah ```service squid3 restart```

<img width="361" alt="squid" src="https://user-images.githubusercontent.com/57948206/100496896-6f733080-318a-11eb-9b62-b58247be71f5.PNG">

## Soal 12
* Install aplikasi bind9 pada UML MALANG dengan perintah ```apt-get install bind9 -y```
* Buka ```nano /etc/bind/named.conf.local``` . Edit konfigurasi sebagai berikut :

<img width="363" alt="conf" src="https://user-images.githubusercontent.com/57948206/100496892-6d10d680-318a-11eb-98e0-af766be93bfc.PNG">

* Buat folder jarkom di dalam /etc/bind mkdir /etc/bind/jarkom
* Copykan file db.local ke dalam folder janganlupa-ta.a10.pw dengan perintah ```cp /etc/bind/db.local /etc/bind/jarkom/janganlupa-ta.a10.pw```
* Buka file ```nano /etc/bind/jarkom/janganlupa-ta.e09.pw``` dan edit konfigurasi sebagai berikut :

<img width="364" alt="jarkom jangan" src="https://user-images.githubusercontent.com/57948206/100496894-6e420380-318a-11eb-9138-1891fda1ee64.PNG">
 
 * Restart bind9 dengan perintah ```service bind9 restart```
 * Atur proxy di firefox seperti gambar berikut :
 
 <img width="577" alt="proxy" src="https://user-images.githubusercontent.com/57948206/100496895-6eda9a00-318a-11eb-82ab-c13008cab951.PNG">
 
 
 
 
 
 
 
