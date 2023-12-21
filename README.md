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
</br><img src="img/subnet.png?raw=true" alt="Alt text" title="1a" width="700">

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
  option broadcast-address 192.176.13.255;
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

# Jangan lupa uncomment 
# nano /etc/sysctl.conf
# net.ipv4.ip_forward=1

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