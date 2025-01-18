Las direcciones MAC en las redes de computadoras es un identificador de 48 bits (6 bytes) que corresponde de forma única a una tarjeta o dispositivo de red, se le conoce tambien como dirección física y esta es única para cada dispositivo

#### Estructuras de las direcciones mac

Supongamos que tenemos la siguiente dirección mac `00:0c:29:a5:61:5e` 

Las direcciones mac se dividen en 2 pares, `00:0c:29` es el OUI (**Identificador Único Organizacional**) y el otro par `a5:61:5e` es el NIC (**Controlador de interfaz de red**)  

Es decir, los primeros **3 bytes** (**24 bits**) representan el fabricante de la tarjeta, y los últimos **3 bytes** (**24 bits**) identifican la tarjeta particular de ese fabricante. Cada grupo de **3 bytes** se puede representar con **6 dígitos hexadecimales**, formando un número hexadecimal de **12 dígitos** que representa la MAC completa

#### ¿Realmente es única?

Si y no, normalmente si son únicas, pero hay herramientas que nos permiten modificar nuestra dirección, un ejemplo puede ser la famosa herramienta [macchanger](https://www.reydes.com/d/?q=macchanger) 
 