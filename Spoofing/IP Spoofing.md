# ¿Qué es el IP Spoofing?

El IP Spoofing es una técnica utilizada para enviar paquetes falsificando la dirección IP de origen, de manera que parece que los paquetes provienen de un dispositivo dentro de una red, ocultando nuestra verdadera identidad. Esto puede utilizarse para engañar al receptor, esconder el origen de los paquetes y realizar ataques.

# ¿Cómo realizar un IP spoofing?

Lo primero que vamos a hacer es falsificar nuestra dirección IP de nuestra máquina kali

`iptables -t nat -APOSTROUTING -j SNAT --to-source 192.168.1.10`

Este comando configura iptables para que todos los paquetes salientes tengan como dirección IP de origen 192.168.1.10 en vez de nuestra IP real.
