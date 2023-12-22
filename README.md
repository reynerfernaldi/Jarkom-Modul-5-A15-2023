# Jarkom-Modul-5-A15-2023

### Kelompok A15

| **No** | **Nama**                   | **NRP**    |
| ------ | -------------------------- | ---------- |
| 1      | Frederick Hidayat          | 5025211152 |
| 2      | Reyner Fernaldi            | 5025201094 |


# PEMBAHASAN

## Topologi
</br><img src="img/Topologi.png?raw=true" alt="Alt text" title="1a" width="700">

## VLSM
</br><img src="img/vlsm.png?raw=true" alt="Alt text" title="1a" width="700">

## VLSM Tree
</br><img src="img/tree1.png?raw=true" alt="Alt text" title="1a" width="700">
</br><img src="img/tree2.png?raw=true" alt="Alt text" title="1a" width="700">

## Pembagian subnet
</br><img src="img/subnet2.png?raw=true" alt="Alt text" title="1a" width="700">


## Konfigurasi 

-   Aura
    ```
    auto eth0
    iface eth0 inet dhcp

    #A2
    auto eth1
    iface eth1 inet static
    address 192.176.14.133
    netmask 255.255.255.252

    #A6
    auto eth2
    iface eth2 inet static
    address 192.176.14.149
    netmask 255.255.255.252


    #Heiter
    up route add -net 192.176.8.0 netmask 255.255.252.0 gw 192.176.14.134
    up route add -net 192.176.0.0 netmask 255.255.248.0 gw 192.176.14.134

    #Frieren
    up route add -net 192.176.14.136 netmask 255.255.255.252 gw 192.176.14.150
    up route add -net 192.176.14.128 netmask 255.255.255.252 gw 192.176.14.150
    up route add -net 192.176.12.0 netmask 255.255.254.0 gw 192.176.14.150
    up route add -net 192.176.14.0 netmask 255.255.255.128 gw 192.176.14.150
    up route add -net 192.176.14.140 netmask 255.255.255.252 gw 192.176.14.150
    up route add -net 192.176.14.144 netmask 255.255.255.252 gw 192.176.14.150
    ```

-   Heiter
    ```
    auto lo
    iface lo inet loopback

    #A2
    auto eth0
    iface eth0 inet static
    address 192.176.14.134
    netmask 255.255.255.252
    gateway 192.176.14.133

    #A8
    auto eth1
    iface eth1 inet static
    address 192.176.0.1
    netmask 255.255.248.0

    #A1
    auto eth2
    iface eth2 inet static
    address 192.176.8.1
    netmask 255.255.252.0

    up route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.176.14.132
    ```
-   Frieren
    ```
    auto lo
    iface lo inet loopback

    #A6
    auto eth0
    iface eth0 inet static
    address 192.176.14.150
    netmask 255.255.255.252
    gateway 192.176.14.149

    #A3
    auto eth1
    iface eth1 inet static
    address 192.176.14.137
    netmask 255.255.255.252

    #A1
    auto eth2
    iface eth2 inet static
    address 192.176.14.129
    netmask 255.255.255.252

    up route add -net 192.176.12.0 netmask 255.255.254.0 gw 192.176.14.130
    up route add -net 192.176.14.0 netmask 255.255.255.128 gw 192.176.14.130
    up route add -net 192.176.14.140 netmask 255.255.255.252 gw 192.176.14.130
    up route add -net 192.176.14.144 netmask 255.255.255.252 gw 192.176.14.130
    up route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.176.14.149
    ```
-   Himmel
    ```
    auto lo
    iface lo inet loopback

    #A1
    auto eth0
    iface eth0 inet static
    address 192.176.14.130
    netmask 255.255.255.252
    gateway 192.176.14.129

    #A7
    auto eth1
    iface eth1 inet static
    address 192.176.12.1
    netmask 255.255.254.0

    #A10
    auto eth2
    iface eth2 inet static
    address 192.176.14.1
    netmask 255.255.255.128

    up route add -net 192.176.14.140 netmask 255.255.255.252 gw 192.176.14.2
    up route add -net 192.176.14.144 netmask 255.255.255.252 gw 192.176.14.2
    up route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.176.14.129
    ```

-   Fern
    ```
    auto lo
    iface lo inet loopback

    #A10
    auto eth0
    iface eth0 inet static
    address 192.176.14.2
    netmask 255.255.255.128
    gateway 192.176.14.1

    #A4
    auto eth1
    iface eth1 inet static
    address 192.176.14.141
    netmask 255.255.255.252

    #A5
    auto eth2
    iface eth2 inet static
    address 192.176.14.145
    netmask 255.255.255.252

    up route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.176.14.1
    ```

-   Revolte
    ```
    auto eth0
    iface eth0 inet static
    address 192.176.14.146
    netmask 255.255.255.252
    gateway 192.176.14.145
    ```

-   Richter
    ```
    auto eth0
    iface eth0 inet static
    address 192.176.14.142
    netmask 255.255.255.252
    gateway 192.176.14.141
    ```

-   Stark
    ```
    auto eth0
    iface eth0 inet static
    address 192.176.14.138
    netmask 255.255.255.252
    gateway 192.176.14.137
    ```

-   Sein
    ```
    auto eth0
    iface eth0 inet static
    address 192.176.8.2
    netmask 255.255.252.0
    gateway 192.176.8.1
    ```

-   Client
    ```
    auto eth0
    iface eth0 inet dhcp
    ```

## DNS Server (Richter)
```
echo 'nameserver 192.168.122.1' >/etc/resolv.conf

apt update
apt install netcat -y
apt install bind9 -y

echo '
options {
  directory "/var/cache/bind";
  forwarders {
    192.168.122.1;
  };
  allow-query {any;};
  auth-nxdomain no; # conform to RFC1035
  listen-on-v6 {any;};
}' > /etc/bind/named.conf.options 

service bind9 restart 
```

## DHCP Server (Revolte)

```
echo 'nameserver 192.168.122.1' > /etc/resolv.conf

apt update
apt install netcat -y
apt install isc-dhcp-server -y

echo 'INTERFACESv4="eth0"' > /etc/default/isc-dhcp-server

echo '
# option definitions common to all supported networks...
option domain-name "example.org";
option domain-name-servers ns1.example.org, ns2.example.org;

default-lease-time 600;
max-lease-time 7200;

# have support for DDNS.)
ddns-update-style none;

# A1
subnet 192.176.14.128 netmask 255.255.255.252 {}

# A2
subnet 192.176.14.132 netmask 255.255.255.252 {}

# A3
subnet 192.176.14.136 netmask 255.255.255.252 {}

# A4
subnet 192.176.14.140 netmask 255.255.255.252 {}

# A5
subnet 192.176.14.144 netmask 255.255.255.252 {}

# A6
subnet 192.176.14.148 netmask 255.255.255.252 {}

# A7
subnet 192.176.12.0 netmask 255.255.254.0 {
  range 192.176.12.2 192.176.13.254;
  option routers 192.176.12.1;
  option broadcast-address 192.176.13.255;
  option domain-name-servers 192.176.1.110;
  default-lease-time 720;
  max-lease-time 7200;
}

# A8
subnet 192.176.0.0 netmask 255.255.248.0 {
  range 192.176.0.2 192.176.7.254;
  option routers 192.176.0.1;
  option broadcast-address 192.176.7.255;
  option domain-name-servers 192.176.1.110;
  default-lease-time 720;
  max-lease-time 7200;
}

# A9
subnet 192.176.8.0 netmask 255.255.252.0 {
  range 192.176.8.2 192.176.11.254;
  option routers 192.176.8.1;
  option broadcast-address 192.176.11.255; 
  option domain-name-servers 192.176.1.110;
  default-lease-time 720;
  max-lease-time 7200;
}

# A10
subnet 192.176.14.0 netmask 255.255.255.128 {
  range 192.176.14.3 192.176.14.126;
  option routers 192.176.14.1;
  option broadcast-address 192.176.14.127;
  option domain-name-servers 192.176.1.110;
  default-lease-time 720;
  max-lease-time 7200;
}
' > /etc/dhcp/dhcpd.conf

service isc-dhcp-server start
```

## DHCP Relay (Hieter, Himmel)
```
echo 'nameserver 192.168.122.1' > /etc/resolv.conf

apt update
apt install netcat -y
apt install isc-dhcp-relay -y

echo '
SERVERS="192.173.1.106"
INTERFACES="eth0 eth1 eth2 eth3"
OPTIONS=""
' > /etc/default/isc-dhcp-relay

service isc-dhcp-relay restart
```

## Web Server (Sein dan Stark)
```
echo 'nameserver 192.168.122.1' > /etc/resolv.conf

apt update
apt install netcat -y
apt install apache2 -y
service apache2 start

echo '# If you just change the port or add more ports here, you will likely also
# have to change the VirtualHost statement in
# /etc/apache2/sites-enabled/000-default.conf

Listen 80
Listen 443

<IfModule ssl_module>
        Listen 443
</IfModule>

<IfModule mod_gnutls.c>
        Listen 443
</IfModule>

# vim: syntax=apache ts=4 sw=4 sts=4 sr noet' > /etc/apache2/ports.conf
```
### 1. Agar topologi yang kalian buat dapat mengakses keluar, kalian diminta untuk mengkonfigurasi Aura menggunakan iptables, tetapi tidak ingin menggunakan MASQUERADE.
```
IPETH0="$(ip -br a | grep eth0 | awk '{print $NF}' | cut -d'/' -f1)"
iptables -t nat -A POSTROUTING -o eth0 -j SNAT --to-source "$IPETH0" -s 192.176.0.0/20
```

### 2. Kalian diminta untuk melakukan drop semua TCP dan UDP kecuali port 8080 pada TCP.
- Konfigurasi pada Revolter (DHCP Server)
  ```
  iptables -A INPUT -p tcp --dport 8080 -j ACCEPT
  iptables -A INPUT -p tcp -j DROP
  iptables -A INPUT -p udp -j DROP
  ```

- Result
  </br><img src="img/sblmblock.png?raw=true" alt="Alt text" title="1a" width="700">
  </br><img src="img/blocked_tcp.png?raw=true" alt="Alt text" title="1a" width="700">


### 3. Kepala Suku North Area meminta kalian untuk membatasi DHCP dan DNS Server hanya dapat dilakukan ping oleh maksimal 3 device secara bersamaan, selebihnya akan di drop.
- Kofigurasi Revolte
  ```
  iptables -I INPUT -p icmp -m connlimit --connlimit-above 3 --connlimit-mask 0 -j DROP
  iptables -I INPUT -m state --state ESTABLISHED,RELATED -j ACCEPT
  ```
- Result
  </br><img src="img/3.png?raw=true" alt="Alt text" title="1a" width="700">

### 4. Lakukan pembatasan sehingga koneksi SSH pada Web Server hanya dapat dilakukan oleh masyarakat yang berada pada GrobeForest.
- Konfigurasi
  ```
  iptables -A INPUT -p tcp --dport 22 -s 192.176.x.x -j ACCEPT
  iptables -A INPUT -p tcp --dport 22 -j DROP
  ```
  note: x.x adalah ip GorbeForest
- Result
  </br><img src="img/4_ip.png?raw=true" alt="Alt text" title="1a" width="500">
  </br><img src="img/4_grobeforest_in.png?raw=true" alt="Alt text" title="1a" width="700">
  </br><img src="img/4_gagal.png?raw=true" alt="Alt text" title="1a" width="700">

### 5. Selain itu, akses menuju WebServer hanya diperbolehkan saat jam kerja yaitu Senin-Jumat pada pukul 08.00-16.00.
- Konfigurasi
  ```
  iptables -A INPUT -m time --timestart 08:00 --timestop 16:00 --weekdays Mon,Tue,Wed,Thu,Fri -j ACCEPT
  iptables -A INPUT -j REJECT
  ```
- Ubah date server sesuai ketentuan
  ```
  date --set="2023-12-22 11:00:00"
  ```
- Result
  </br><img src="img/5a.png?raw=true" alt="Alt text" title="5a" width="700">
  </br><img src="img/5b.png?raw=true" alt="Alt text" title="5b" width="700">

### 6. Lalu, karena ternyata terdapat beberapa waktu di mana network administrator dari WebServer tidak bisa stand by, sehingga perlu ditambahkan rule bahwa akses pada hari Senin - Kamis pada jam 12.00 - 13.00 dilarang (istirahat maksi cuy) dan akses di hari Jumat pada jam 11.00 - 13.00 juga dilarang (maklum, Jumatan rek).

- Konfigurasi
  ```
  iptables -I INPUT 3 -m time --timestart 12:00 --timestop 13:00 --weekdays Mon,Tue,Wed,Thu -j REJECT
  iptables -I INPUT 4 -m time --timestart 11:00 --timestop 13:00 --weekdays Fri -j REJECT
  ```
- Ubah date
  ```
  date --set="2023-12-21 12:30:00"
  ```
- Result
  </br><img src="img/6a.png?raw=true" alt="Alt text" title="5b" width="700">
  </br><img src="img/6b.png?raw=true" alt="Alt text" title="5b" width="700">

### 7. Karena terdapat 2 WebServer, kalian diminta agar setiap client yang mengakses Sein dengan Port 80 akan didistribusikan secara bergantian pada Sein dan Stark secara berurutan dan request dari client yang mengakses Stark dengan port 443 akan didistribusikan secara bergantian pada Sein dan Stark secara berurutan.

- Konfigurasi
  ```
  iptables -A PREROUTING -t nat -p tcp --dport 80 -d 192.176.8.2 -m statistic --mode nth --every 2 --packet 0 -j DNAT --to-destination 192.176.8.2:80
  iptables -A PREROUTING -t nat -p tcp --dport 80 -d 192.176.8.2 -j DNAT --to-destination 192.176.14.138:80
  iptables -A PREROUTING -t nat -p tcp --dport 443 -d 192.176.14.138 -m statistic --mode nth --every 2 --packet 0 -j DNAT --to-destination 192.176.14.138:443
  iptables -A PREROUTING -t nat -p tcp --dport 443 -d 192.176.14.138 -j DNAT --to-destination 192.176.8.2:443
  ```
- Testing
  ```
  curl 192.176.8.2:80
  curl 192.176.14.138:443
  ```
- Result
  </br><img src="img/7.png?raw=true" alt="Alt text" title="5b" width="500">



### 8. Karena berbeda koalisi politik, maka subnet dengan masyarakat yang berada pada Revolte dilarang keras mengakses WebServer hingga masa pencoblosan pemilu kepala suku 2024 berakhir. Masa pemilu (hingga pemungutan dan penghitungan suara selesai) kepala suku bersamaan dengan masa pemilu Presiden dan Wakil Presiden Indonesia 2024.
- Konfigurasi
  ```
  iptables -A INPUT -p tcp --dport 80 -s 192.176.14.144/30 -m time --datestart 2023-12-22 --datestop 2024-02-15 -j DROP
  ```
- Result
  Waktu pemilu
  </br><img src="img/8a.png?raw=true" alt="Alt text" title="5b" width="500">
  </br>Bukan Waktu Pemilu
  </br><img src="img/8b.png?raw=true" alt="Alt text" title="5b" width="500">
  </br>Client lain
  </br><img src="img/8c.png?raw=true" alt="Alt text" title="5b" width="500">



### 9. Sadar akan adanya potensial saling serang antar kubu politik, maka WebServer harus dapat secara otomatis memblokir  alamat IP yang melakukan scanning port dalam jumlah banyak (maksimal 20 scan port) di dalam selang waktu 10 menit. 
(clue: test dengan nmap)
- Konfigurasi
  ```
  iptables -N portscan

  iptables -A INPUT -m recent --name portscan --update --seconds 600 --hitcount 20 -j DROP
  iptables -A FORWARD -m recent --name portscan --update --seconds 600 --hitcount 20 -j DROP

  iptables -A INPUT -m recent --name portscan --set -j ACCEPT
  iptables -A FORWARD -m recent --name portscan --set -j ACCEPT
  ```

- Result
![image](https://github.com/reynerfernaldi/Jarkom-Modul-5-A15-2023/assets/90272678/ce73f4a9-5a4a-4b9d-b2db-506030f5be64)


### 10. Karena kepala suku ingin tau paket apa saja yang di-drop, maka di setiap node server dan router ditambahkan logging paket yang di-drop dengan standard syslog level. 

    ```
        iptables -N LOGGING
        iptables -A INPUT -j LOGGING
        iptables -A OUTPUT -j LOGGING
        iptables -A LOGGING -m limit --limit 2/min -j LOG --log-prefix "IPTables-Dropped: " --log-level 4
        iptables -A INPUT -j LOG --log-prefix "Dropped packet: " --log-level 4
  ```

Dari _running_ perintah di atas akhirnya bisa dilihat syslog sebagai berikut
![image](https://github.com/reynerfernaldi/Jarkom-Modul-5-A15-2023/assets/90272678/bc8ed482-c95b-49d0-925b-ad0fd3ea1024)

