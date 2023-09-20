### 1.Analiza los headers de las peticiones cuando inicias sesión en el Moodle y comprende
### cómo se obtiene el token. Para ello, necesitamos saber de dónde salen TODOS los
### datos sensibles que se envían.

![image](https://github.com/anMarchena/despliegue-de-aplicaciones-web/assets/107402815/3f185088-049d-436c-9abe-3b74663eadf3)

En esta imagen vemos el index en el cual introducimos las credenciales.

![image](https://github.com/anMarchena/despliegue-de-aplicaciones-web/assets/107402815/da67b95b-cff3-42a2-ba31-f185aad4cd14)

En la siguiente vemos como se recibe el usuario y contraseña y comprueba si estos existen.

![image](https://github.com/anMarchena/despliegue-de-aplicaciones-web/assets/107402815/56946295-1b0d-460b-9f3b-69b816cd99f8)

Una vez comprueba si existe el usuario este carga la pagina correspondiente del usuario.

### 2.¿A qué puerto se reciben normalmente las peticiones del protocolo HTTP? 

Por defecto se reciven al pueto 80.

### ¿A qué capa del modelo TCP/IP se encuentra el protocolo HTTP? 

El protocolo HTTP pertenece a la capa de aplicación del modelo TCP/IP.

### ¿Y los protocolos TCP, UDP, e IP?

El TCP y el UDP pertenecen a la capa de transporte.
El IP pertenece a la capa de internet.

### 3.¿Cuál es el significado de la siguiente respuesta de un servidor?
### HTTP/1.1 302 Found
### Location: http://www.example.com/test/index2.php

Esto significa que la request se ha encontrado y despues muestra la ruta de esta.

### 4.Utilizando el filtro de captura para la interfaz de red de Wireshark, analiza la petición
### al host: www.google.com. Mostrando la cabecera IP, la dirección IP de tu ordenador y
### la del servidor. Comprueba que, poniendo esa IP en el navegador, accedas a Google.

![image](https://github.com/anMarchena/despliegue-de-aplicaciones-web/assets/107402815/e6ed7bd8-acb1-48ff-9250-256e83bfc711)

Aqui podemos ver como la ip de 10.0.2.15 es la de mi ordenador, que es el que esta haciendo la request para habrir google.

![image](https://github.com/anMarchena/despliegue-de-aplicaciones-web/assets/107402815/3789631f-6063-47bf-9d4d-ca1ff3686ff0)


Tambien podemos ver como la otra es la ip de google. Si buscamos esta ip en el buscador nos hare la pagina de google directamente.
