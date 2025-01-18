# ¿Qué es el IP Spoofing?

El IP Spoofing es una técnica utilizada para enviar paquetes falsificando la dirección IP de origen, de manera que parece que los paquetes provienen de un dispositivo dentro de una red, ocultando nuestra verdadera identidad. Esto puede utilizarse para engañar al receptor, esconder el origen de los paquetes y realizar ataques.

# ¿Cómo realizar un IP spoofing?

Lo primero que vamos a hacer es falsificar nuestra dirección IP de nuestra máquina kali

`iptables -t nat -APOSTROUTING -j SNAT --to-source 192.168.1.10`

![imagen](https://github.com/user-attachments/assets/f931b3e6-2af4-4dbc-8e4f-6a160885ff15)


Este comando configura iptables para que todos los paquetes salientes tengan como dirección IP de origen `192.168.1.10` en vez de nuestra IP real.

Ahora, le enviaré un ping a mí máquina Windows la cual tiene la IP `192.168.1.17`

![imagen](https://github.com/user-attachments/assets/7d0b299b-ca0e-459d-add2-30d944ea35b7)

El tráfico lo capturaré mediante la herramienta Wireshark, la cual tengo instalada en el Windows para poder interceptar los paquetes que viajan.

![imagen](https://github.com/user-attachments/assets/fc052fc7-ebe7-4e06-bbbf-9f69098132c5)

Como vemos, al tramitar un paquete desde nuestro Kali, no viaja con la dirección IP 192.168.1.24 la cual sería la original, viaja utilizando la dirección IP que le asignamos anteriormente

Para poder restablecer nuestra dirección IP, ejecutaremos este comando el cual eliminara la configuración anteriormente aplicada

`iptables -t nat -D POSTROUTING 1`

# Alternativas

Una herramienta que podemos utilizar también para efectuar este spoofing puede ser `Hping3` la cual viene instalada en kali por defecto

`hping3 -a 192.168.200.200 -S 192.168.1.17 -p 8080`

Con este comando estamos diciéndole a la herramienta que envie paquetes a la dirección IP `192.168.1.17` por el puerto `8080` haciendo uso de la IP `192.168.200.200`

![imagen](https://github.com/user-attachments/assets/76c3e841-8e3e-4dfb-affe-d242c7921a48)

