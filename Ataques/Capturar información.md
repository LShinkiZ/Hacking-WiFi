# Airodump-ng

Una vez estemos en modo monitor, podemos utilizar la herramienta airodump-ng, la cual nos servirá para poder interceptar los datos que viajen por el aire ejecutando el siguiente comando.

`airodump-ng wlan0mon`

![imagen](https://github.com/user-attachments/assets/e0caa130-6525-4140-bd6e-40297662d24d)

Si observamos, la herramienta esta "seccionada" en 2 partes, la parte superior nos muestra lo que vendrías a ser los diferentes puntos de accesos con sus respectivos datos, en la parte inferior tenemos la información de los clientes, los cuales son los dispositivos que están tramitando paquetes con su respectiva información 

## Sección 1

- BSSID: Este campo nos representa la dirección Mac de los puntos de acceso
- PWR: Este campo nos representa el nivel de señal, mientras más alto sea el número se podría decir que más cerca estamos del punto de acceso.
- Beacons: Estos son paquetes que emiten los puntos de accesos para mostrarse
- Data: El campo data nos representa la cantidad de paquetes capturados
- #/s: Números de paquetes de datos medidos durante los últimos 10 segundos
- CH: Canal donde se encuentra el punto de acceso
- MB: Este campo nos representa la velocidad máxima soportada por el AP
- ENC: Este campo nos representa el tipo de encriptado que utiliza el AP
- CIPHER: Este campo nos muestra el tipo de cifrado que usa el AP
- AUTH: Este campo nos muestra el tipo de autenticación que utiliza el AP
- ESSID: Este campo nos muestra el nombre del punto de acceso

## Sección 2

- BSSID: Este campo nos representa la dirección Mac de los puntos de acceso
- STATION: Este campo nos representa las direcciones Mac de los clientes que estén conectados ha dicho bssid, n caso de que en el apartado de BSSID ponga "(not associated)" es porque ese cliente no está conectado a ninguna red
- Probes: Este campo nos muestra a las redes que se quiso conectar un cliente

# Filtrar información

Supongamos que queremos filtrar solamente por la red que tiene de nombre "Telecentro-36e7" para esto podeos hacerlo de varias formas

`airodump-ng -c 4 --essid Telecentro-36e7 wlan0mon`

Con este comando le estamos indicando a la herramienta que filtre solamente por la red que se llama Telecentro-36e7 y su respectivo canal

También se puede filtrar con la mac de la red, es decir el bssid

`airodump-ng -c 4 --bssid 08:7B:12:9E:36:E8 wlan0mon`

# Exportar información

Una vez tengamos a nuestro objetivo filtrado, lo que debemos hacer es guardar la información, esto lo debemos hacer, ya que si capturamos el handshake de la red luego lo podemos crackear.

`airodump-ng -w Captura -c 4 --bssid 08:7B:12:9E:36:E8 wlan0mon`

Con el parámetro `-w` le indicamos que guarde la información capturada en un archivo, en este caso el archivo se llama Captura.
