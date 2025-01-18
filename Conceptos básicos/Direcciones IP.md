Las direcciones IP son unas "etiquetas" numéricas que nos sirven para identificar de manera lógica y jerárquica a una interfaz en la red de un dispositivo que utilice el protocolo de internet. 

Nuestra dirección IP en Linux podemos mostrarla mediante el comando `ifconfig` o `hostname -I` 

Las direcciones IP no son mas que bytes (es decir 0 o 1) en el caso de las IPv4 son 4 octeto, se le llaman octeto porque hay 4 pares de 8 bits(1 byte equivale a 8 bits).

Supongamos que nuestra dirección IP es `192.168.1.24`, esta la podemos representar en bits de la siguiente forma.

```sh
echo "$(echo "obase=2; 192" | bc).$(echo "obase=2; 168" | bc).$(echo "obase=2; 1" | bc).$(echo "obase=2; 24" | bc)"
```

La versión **IPv4** utiliza un formato de dirección de **32 bits** y se utiliza actualmente en la mayoría de las redes. La versión **IPv6** utiliza un formato de dirección de **128 bits** y se está implementando gradualmente en todo el mundo para hacer frente a la escasez de direcciones IPv4.

Las direcciones IPv4 se representan como cuatro números separados por puntos, como **192.168.1.24**, mientras que las direcciones IPv6 se representan en notación hexadecimal y se separan por dos puntos, como **2001:0db8:85a3:0000:0000:8a2e:0370:7334**.