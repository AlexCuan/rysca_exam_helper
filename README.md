# Informacion general

Para levantar la interfaz del dongle se usa `sudo ip link set dev eth1 up`

Para establecer una ip se usa `sudo ip addr add $IP/$SUBNET dev $INTERFACE`

Importante añadir las rutas. Si añadimos una ruta es `sudo ip route add $NETWORK/$SUBNET dev $INTERFACE`, 
o si añadimos una ruta por defecto (por ejemplo, si solamente tenemos una conexion) seria `sudo ip route add default via $GATEAWAY dev $INTERFACE`

Para ver las rutas solamente de un protocolo especifico hacemos `show ip route protocol`

Para ver las rutas hacia una subred especifica usamos `show ip route red`

Para configurar los routers la topologia esta hecha para que solo quede sin desactivar la interfaz eth0.0, que es la que vamos a usar para configurar cada router. Nos ponemos la una ip del rango `192.168.0.0/24` que nos sirve para configurar todos los routers por la misma interfaz sin tener que estar cambiando. Simplemente conectamos y desconectamos siempre en el eth0.0.


El tiempo de convergencia de RIP es de 180 a 210 segundos. 180 en el mejor de los casos, que se caiga el enlace acabada de mandar la actualizacion, 210 en el peor de los casos, antes de mandar la actualizacion.

Como medir tiempo cuando se cae una conexion? Podemos hacer un ping y dejarlo correr hasta que se reestablezca, y el numero de secuencia nos dira cuanto tiempo ha pasado. Los pings se mandan cada 1 segundo, asi que cada numero de secuencia sera 1 segundo.


