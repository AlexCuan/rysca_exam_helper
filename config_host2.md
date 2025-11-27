sudo ip link set eth1 up
# No usar las lineas comentadas a menos que sea necesario hacer un hot fix
<!-- sudo ip addr add 192.168.0.2/24 dev eth1 -->
# CONFIGURA LOS ROUTERS
<!-- sudo ip addr del 192.168.0.2/24 dev eth1 -->
sudo ip addr add 10.10.2.135/27 dev eth1
sudo ip route add 10.0.0.0/8 via 10.10.2.130
