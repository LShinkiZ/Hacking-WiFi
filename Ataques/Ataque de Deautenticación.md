# Ataque de Deautenticación

Este ataque consta en hacerle creer al router que un cliente que estaba conectado se ha desconectado, haciendo que el cliente pierda la conexión con la red, esto nos sirve porque el cliente reintentara conectarse a la red, emitiendo el handshake de la red y así nosotros podemos capturarlo para luego crackearlo

# Ataque de Deautenticación dirigido

El Ataque de Deautenticación dirigido se basa en expulsar a un solo cliente del punto de acceso seleccionado, esto lo podemos hacer utilizando la herramienta `aireplay-ng`

`aireplay-ng --deauth 10 -e Telecentro-36e7 -c 2E:9E:D3:7B:4A:00 wlan0mon`

- --deauth: Indicamos que queremos hacer un ataque de Deautenticación
- 10: Son la cantidad de paquetes de Deautenticación que queremos emitir, si no ponemos nada el ataque será infinito hasta que lo pausemos nosotros
- -e: Indicamos el nombre del punto de acceso
- -c: Con este parámetro indicamos el cliente que queremos expulsar, debemos poner la mac del cliente
- wlan0mon: Nuestra tarjeta de red

# Ataque de Deautenticación global

También lo que podemos hacer es hacer un ataque de Deautenticación de manera global, es decir, expulsar a todos los que estén conectados a la red

Para esto tenemos que hacer uso de la Broadcast MAC Address

`aireplay-ng --deauth 10 -e Telecentro-36e7 -c FF:FF:FF:FF:FF:FF wlan0mon`
