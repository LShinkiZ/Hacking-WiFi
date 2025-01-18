# ¿Qué es el modo monitor?

Cuando ponemos nuestra tarjeta de red en modo monitor, lo que logramos es poder capturar todos los paquetes que se transmiten en el aire, independientemente de si están destinados a la red a la que estamos conectados o no. Esto incluye no solo los paquetes de los puntos de acceso, sino también las direcciones MAC de los puntos de acceso, las direcciones MAC de los clientes conectados a cada punto de acceso y otros datos, como información sobre la calidad de la señal, configuraciones de la red, y más.

# ¿Como poner la tarjeta en modo monitor?

Una vez conectemos nuestra antena a nuestra máquina, podremos listar la interfaz de la misma utilizando el comando **ifconfig**

![imagen](https://github.com/user-attachments/assets/fee6e9c8-fe97-43e6-a6f2-3d60369f013e)

En este caso, la interfaz de red de mi antena se llama **wlan0**. No todas tienen el mismo nombre. Ahora vamos a usar la herramienta **airmon-ng** para configurarla en modo monitor.

![imagen](https://github.com/user-attachments/assets/8f92cba1-e50f-4a10-b758-082dfeb71a18)

Al activar la tarjeta de red en modo monitor, normalmente se desactiva temporalmente de forma automática. Esto sucede porque estamos cambiando el comportamiento de la misma para que intercepte todos los paquetes que circulen por el aire. Por lo tanto, si hacemos un **ifconfig**, veremos que la interfaz desapareció. Para verificar que está dada de baja, podemos usar el comando **iwconfig**

![imagen](https://github.com/user-attachments/assets/7d3550b8-2811-422f-8279-200a2708357e)

A la interfaz de red de nuestra tarjeta se le agregó la palabra `mon`, con eso podemos verificar que se ha puesto en modo monitor. Si no, también lo podemos ver en el campo `Mode`, el cual tiene el valor `Monitor`. Para poder activar esta interfaz, volveremos a usar el comando **ifconfig**.

![imagen](https://github.com/user-attachments/assets/d7f9ad82-1311-4c0e-adb1-7cb3fb477f52)
