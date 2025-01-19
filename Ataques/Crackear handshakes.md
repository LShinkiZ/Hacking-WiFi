# Crackear handshakes

Una vez obtenido el Handshake de la red objetivo y lo tengamos almacenado en el archivo `.cap`, podemos intentar crackearlo haciendo uso de la herramienta `aircrack-ng`

`aircrack-ng Captura-01.cap -e Telecentro-36e7 -w /usr/share/wordlists/rockyou.txt`

![imagen](https://github.com/user-attachments/assets/b70b2274-ceb4-48c8-b3c6-450c5df5b1ba)

Primero debemos pasarle el archivo que contenga el handshake, luego con el parámetro `-e` le indicamos el nombre del punto de acceso y por último el diccionario que queremos usar para crackear el handshake

# Alternativa

Si queremos extraer el hash para crackearlo con otra herramienta, como por ejemplo hashcat, debemos hacer lo siguiente

`hcxpcapngtool -o handshake.txt Captura-01.cap &>/dev/null`
`cat handshake.txt`

![imagen](https://github.com/user-attachments/assets/5c66b80a-e3d6-48ee-bb88-601b9407c530)

Una vez tengamos el hash, procederemos a crackearlo con hashcat de la siguiente forma

`hashcat -m 22000 handshake.txt /usr/share/wordlists/rockyou.txt`

![imagen](https://github.com/user-attachments/assets/c7b7a8bb-f058-4dfa-8f0a-ead82c7430f2)
