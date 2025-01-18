# ¿Qué son las direcciones IP?

Una dirección IP es un identificador único asignado a cada dispositivo que se conecta a una red que utiliza el protocolo de Internet. Esta dirección permite la comunicación entre dispositivos dentro de una red, ya sea local o global.

# ¿Qué es una IP privada?

Una dirección IP privada es una dirección que se asigna a un dispositivo dentro de una red local (LAN) gracias a un router utilizando el protocolo DHCP. Se llama "privada" porque solo es válida y accesible dentro de esa red local.

# ¿Qué es una IP publica?

Una dirección IP pública es una dirección única que identifica a un dispositivo en Internet, a diferencia de las direcciones IP privadas que se usan solo dentro de redes locales (LAN), la IP pública permite que un dispositivo sea accesible desde cualquier lugar de Internet. Estas direcciones son asignadas por los proveedores de servicios de Internet (ISP) y son únicas, lo que garantiza que no haya duplicados. El router de una red doméstica generalmente tiene una IP pública y los dispositivos dentro de esa red pueden acceder a Internet mediante un proceso llamado NAT (Network Address Translation), que permite que múltiples dispositivos usen una sola IP pública.

# ¿Qué es el proceso NAT?

NAT (Network Address Translation) es un proceso que permite a un router modificar las direcciones IP de los paquetes de datos mientras viajan entre redes. Esto permite que múltiples dispositivos dentro de una red local utilicen una sola dirección IP pública para acceder a Internet. La razón por la que esto es necesario es la escasez de direcciones IP públicas, ya que las direcciones IPv4 son limitadas y no hay suficientes para asignar una IP única a cada dispositivo conectado a Internet en todo el mundo.

Una pregunta que me surgió mientras estudiaba este concepto fue

Si todos utilizan la misma IP pública para navegar en internet, ¿Cómo sabe el router que dispositivo hizo x consulta?

El router no solamente cambia las direcciones IP, sino que también va haciendo un registro de cada conexión que se realiza, lo que permite saber qué dispositivo dentro de la red local hizo la consulta, incluso después de cambiar la dirección IP y este proceso se puede llevar a cabo gracias a una "tabla de traducción NAT"

Supongamos que nuestra dirección IP privada es "192.168.1.10" y accedemos a internet, el router va a tomar nuestra solicitud y va a cambiar la dirección IP de origen(192.168.1.10) por la IP pública del router, supongamos que la IP pública del router es la (205.0.15.21), acá viene la explicación, este proceso no solo cambia la dirección IP, sino que también asigna un número de puerto único para la conexión que se acaba de realizar, cada conexión de un dispositivo local al Internet se realiza con un número de puerto diferente.

El router lleva un registro de todos los cambios que se realizaron en las direcciones IP y en los puertos mediante la tabla NAT, esta tabla posee un mapeo de cada dirección IP privada y su puerto original correspondiente junto a la dirección IP pública y el nuevo puerto asignado


| IP privada     | Puerto privado | IP pública     | Puerto público |
|----------------|----------------|----------------|----------------|
| 192.168.1.2    | 12345          | 203.0.113.45   | 10001          |


Supongamos que esa IP privada hizo una petición web, la respuesta llega a la dirección IP pública 203.0.113.45 por el puerto 10001, el router va a consultar que IP privada posee ese puerto público, al encontrarla el router va a saber que la petición original provino de la IP 192.168.1.2 usando el puerto 12345, entonces lo que va a hacer el router es reemplazar la dirección IP pública y el puerto con la dirección IP privada del dispositivo y su puerto original, y reenvía los datos de vuelta a 192.168.1.2

https://www.cisco.com/c/en/us/support/docs/ip/network-address-translation-nat/26704-nat-faq-00.html
