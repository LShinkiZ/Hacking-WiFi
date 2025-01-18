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
