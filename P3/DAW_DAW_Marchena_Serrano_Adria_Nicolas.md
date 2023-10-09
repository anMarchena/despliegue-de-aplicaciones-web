**parte 1**

El módulo mod_info es un módulo de Apache que proporciona información detallada sobre el servidor web y su configuración. Se utiliza principalmente con fines de diagnóstico y depuración. Al habilitar el módulo mod_info, puedes acceder a una página web especial que muestra datos importantes sobre el servidor Apache y sus módulos cargados.

Instalación del modulo:

Instalamos mod-info:

![image](https://github.com/anMarchena/despliegue-de-aplicaciones-web/assets/107402815/a0e719d7-cdf6-432b-8287-e7b1675c79f8)

Activamos module info.
una vez echo esto reiniciamos el apache y ya estaria:

![image](https://github.com/anMarchena/despliegue-de-aplicaciones-web/assets/107402815/75949c6a-4d82-46e4-9b83-cf9d1ab2eec3)

**parte 2**

Para ocultar la version del sistema y la de apache modificaremso el siguiente archivo añadiendo las dos ultimas linias como se muestra en la imagen:

![image](https://github.com/anMarchena/despliegue-de-aplicaciones-web/assets/107402815/1c093e9f-624a-44a8-be17-38cb29bbcee9)

Solo queda reiniciar el servidor y ya estaria.
Con esto ya habriamos configurado Apache para ocultar la versión del servidor y los detalles del sistema operativo en las respuestas HTTP. 
Esto nos ayuda a aumentar la seguridad del servidor al reducir la información que se expone públicamente a posibles atacantes.

**parte 3**

Para esto creamos dos directorios ,public y private en el directorio del servidor:

![image](https://github.com/anMarchena/despliegue-de-aplicaciones-web/assets/107402815/a937b0a3-91a7-462e-8f9a-23273c6b2e45)

Luego creamos un archivo .htaccess y lo modificamos de la siguiente manera:

![image](https://github.com/anMarchena/despliegue-de-aplicaciones-web/assets/107402815/6e2506d6-a193-4a70-b050-44e05f3a2c5b)

Ahora en apache2.conf cambiamos el allowoverride de none a all:

![image](https://github.com/anMarchena/despliegue-de-aplicaciones-web/assets/107402815/dfddc15a-ed41-42aa-9c0f-7f8fed4e0bd1)

Y con esto ya estaria:

![image](https://github.com/anMarchena/despliegue-de-aplicaciones-web/assets/107402815/a30211ff-818e-4116-8162-965513c6164e)

**parte 4**

Para poder acceder poniendo www debemos hacer lo siguiente:

Crearemos un archivo .htaccess en el directorio raiz del servidor y lo modificaremos de la siguiente manera:

![image](https://github.com/anMarchena/despliegue-de-aplicaciones-web/assets/107402815/61be5cf0-cc5a-4b28-9c2e-71feba06ae6d)

Con esto ya podriamos acceder poniendo www antes de la ip del servidor.

**parte 5**

Para esta parte primero descargaremos el tema:

![image](https://github.com/anMarchena/despliegue-de-aplicaciones-web/assets/107402815/eb595443-aaf1-417a-960d-cadc5172364a)

Ahora configuramos el .htaccess:

![image](https://github.com/anMarchena/despliegue-de-aplicaciones-web/assets/107402815/a2ddb427-ff2c-4c69-8a7b-9716da85e78c)

Con esto ya estaria.
