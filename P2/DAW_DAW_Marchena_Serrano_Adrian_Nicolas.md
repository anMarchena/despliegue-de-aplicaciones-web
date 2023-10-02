**Administracion servidor**

**ejercicio 2**
GET (Obtener): Pide información del servidor. Es como mirar una página web sin cambiar nada en ella. Los datos van en la dirección web.

POST (Enviar): Envía información al servidor para guardarla o procesarla. Puede cambiar cosas en el servidor. Los datos van ocultos en la solicitud.

PUT (Actualizar): Actualiza información en el servidor o creas algo nuevo si no existe. Puede hacerlo varias veces sin cambios extras. Los datos van ocultos en la solicitud.

DELETE (Borrar): Elimina información en el servidor. Puedes hacerlo varias veces sin efectos extra. No envías datos, solo dices qué eliminar.

**parte 3**
Entramos a ports.conf y cambiamos la parte que pone listen que estara en el 80 a 4444:

![image](https://github.com/anMarchena/despliegue-de-aplicaciones-web/assets/107402815/777f3607-d647-4a61-a73d-4041e424b65d)

Luego entramos aqui "sites-available/000-default.conf" y cambiamos la parte de virtualhost de 80 a 4444:

![image](https://github.com/anMarchena/despliegue-de-aplicaciones-web/assets/107402815/90fcb1b3-fd36-4a4d-a1c3-e218a03e47f0)

Y ya va:

![image](https://github.com/anMarchena/despliegue-de-aplicaciones-web/assets/107402815/b24ca41c-23cd-43e8-a8a8-35a622df8523)

**parte 4**

