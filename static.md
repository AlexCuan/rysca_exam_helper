# Escenario Estatico

Ver diagrama escenario estatico. En las rutas estaticas si se usa redundacia se le pone un peso las rutas duplicadas para que no ocurran bucles.

### R1
```bash
conf t
interface eth0.1
no ip address 192.168.1.1/24
ip address 10.10.2.10/26
exit
interface eth0.3
no ip address 192.168.3.1/24
ip address 10.10.2.165/30
exit
interface eth0.2
no ip address 192.168.2.1/24
ip address 10.10.2.161/30
exit
interface eth0.4
shutdown
exit

interface wlan0
shutdown
exit

interface lo
ip address 10.10.2.176/32
exit

ip route 10.10.2.128/27 10.10.2.166
ip route 10.10.2.168/30 10.10.2.166
ip route 10.10.2.172/30 10.10.2.162
ip route 10.10.2.64/26 10.10.2.162

ip route 10.10.2.128/27 10.10.2.162 10
ip route 10.10.2.168/30 10.10.2.162 10
ip route 10.10.2.172/30 10.10.2.166 10
ip route 10.10.2.64/26 10.10.2.166 10

```

### R2

```bash
conf t
interface eth0.1
no ip address 192.168.1.1/24
ip address 10.10.2.130/27
exit
interface eth0.2
no ip address 192.168.2.1/24
ip address 10.10.2.166/30
exit
interface eth0.3
no ip address 192.168.3.1/24
ip address 10.10.2.169/30
exit

interface eth0.4
shutdown
exit
interface wlan0
shutdown
exit

interface lo
ip address 10.10.2.177/32
exit


ip route 10.10.2.0/26 10.10.2.165
ip route 10.10.2.160/30 10.10.2.165
ip route 10.10.2.64/26 10.10.2.170
ip route 10.10.2.172/30 10.10.2.170

ip route 10.10.2.0/26 10.10.2.170 10
ip route 10.10.2.160/30 10.10.2.170 10
ip route 10.10.2.64/26 10.10.2.165 10
ip route 10.10.2.172/30 10.10.2.165 10
```


### R3

```bash
conf t
interface eth0.1
no ip address 192.168.1.1/24
ip address 10.10.2.70/26
exit
interface eth0.2
no ip address 192.168.2.1/24
ip address 10.10.2.173/30
exit
interface eth0.4
no ip address 192.168.4.1/24
ip address 10.10.2.170/30
exit
interface eth0.3
no ip address 192.168.3.1/24
ip address 10.10.2.162/30
exit
interface lo
ip address 10.10.2.178/32
exit
interface wlan0
shutdown
exit

ip route 10.10.2.164/30 10.10.2.161
ip route 10.10.2.0/26 10.10.2.161
ip route 10.10.2.128/27 10.10.2.169

ip route 10.10.2.164/30 10.10.2.169 10
ip route 10.10.2.0/26 10.10.2.169 10
ip route 10.10.2.128/27 10.10.2.161 10
```

### R4

```bash
conf t
interface eth0.1
no ip address 192.168.1.1/24
ip address 10.0.0.2/24
exit
interface eth0.2
no ip address 192.168.2.1/24
ip address 10.10.2.174/30
exit
interface eth0.3
shutdown
exit
interface eth0.4
shutdown
exit
interface lo
ip address 10.10.2.179/32
exit
interface wlan0
shutdown
exit

ip route 10.10.2.64/26 10.10.2.173
ip route 10.10.2.0/26 10.10.2.173
ip route 10.10.2.128/27 10.10.2.173
ip route 10.10.2.160/30 10.10.2.173
ip route 10.10.2.168/30 10.10.2.173
ip route 10.10.2.164/30 10.10.2.173
```
