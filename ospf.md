Si queremos hacer un area stub simplemente añadimos el comando `area 10.10.2.0 stub`
Si queremos redistribuir rutas de un tipo usamos el comando `redistribute type_of_route`


## R1
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

router ospf
ospf router-id 10.10.2.176
passive-interface eth0.1
network 10.10.2.0/24 area 10.10.2.0



```

## R2
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


router ospf
ospf router-id 10.10.2.177
passive-interface eth0.1
network 10.10.2.0/24 area 10.10.2.0

```

## R3
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

router ospf
ospf router-id 10.10.2.178
passive-interface eth0.1
network 10.10.2.0/24 area 10.10.2.0

```

## R4
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

router ospf
ospf router-id 10.10.2.179
network 10.10.0.0/24 area 0.0.0.0
network 10.10.2.0/24 area 10.10.2.0

```
