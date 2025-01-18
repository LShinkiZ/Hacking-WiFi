# ¿Qué es el MAC Spoofing?

El MAC spoofing (suplantación de dirección MAC) es el proceso de cambiar la dirección MAC (Media Access Control) de una interfaz de red para que parezca que proviene de otro dispositivo o adaptador.

# ¿Para qué nos sirve el MAC Spoofing?

El uso del MAC spoofing nos puede servir para la evasión del rastreo, ya que hay algunos dispositivos o redes que mediante nuestra dirección MAC, pueden hacernos un seguimiento. Por lo tanto, modificarla puede ser una solución para esto. Otro uso que le podemos dar es para la evasión del filtrado de MAC. Hay redes que pueden estar configuradas para que ciertas direcciones MAC tengan o no acceso a la red. Si sabemos la dirección MAC de un dispositivo cuya dirección MAC esté aceptada, podemos sustituirla por la misma. Y muchos más usos.

# ¿Cómo cambio mi dirección MAC?

Para poder llevar a cabo la técnica de MAC Spoofing podemos utilizar varias herramientas, una de ellas es `macchanger`, para poder cambiar la dirección MAC de nuestra tarjeta de red usando esta herramienta primero tendremos que desactivar su interfaz de red temporalmente.

![imagen](https://github.com/user-attachments/assets/492e88ad-0227-4803-850b-72be6e81d0da)

Con el parámetro `-r` le indicamos que le asigne una dirección MAC aleatoria, en caso de que queramos asignarle una dirección MAC en específico que nosotros queramos, podemos usar el parámetro `-m` o `--mac`

![imagen](https://github.com/user-attachments/assets/ebd13786-04ca-47f5-b9b9-37536a849b59)
