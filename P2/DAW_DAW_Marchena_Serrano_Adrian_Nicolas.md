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

Primero creamos la key:
![image](https://github.com/anMarchena/despliegue-de-aplicaciones-web/assets/107402815/6ee31d9a-dea9-4ae0-b9cd-e88d922d37e5)

Ponemos nuestros datos:
![image](https://github.com/anMarchena/despliegue-de-aplicaciones-web/assets/107402815/90cd116c-8fd8-4f3b-b283-34624c44555c)

Ponemos esto en 000-defaul.conf:
![image](https://github.com/anMarchena/despliegue-de-aplicaciones-web/assets/107402815/57225225-4d22-468e-a91d-418c50399428)

Reiniciamos el apache.
Ahora si buscamos nuesto dominio con http nos saldra el siguiente error:
![image](https://github.com/anMarchena/despliegue-de-aplicaciones-web/assets/107402815/2d0f2e0b-2954-4b67-8603-1ae31a71fd46)

Pero si buscamos en https podremos entrar:
![image](https://github.com/anMarchena/despliegue-de-aplicaciones-web/assets/107402815/8fecf7de-de75-437b-9fe6-5d401555ec84)


**parte 5**
## Dónde se encuentran los ficheros de configuración de Apache2?
## • Ubicación principal.
Los archivos de configuración principales de Apache2 se encuentran en el directorio /etc/apache2/.

## • Explora el archivo apache2.conf. Identifica las secciones principales y describe
##su propósito.
El archivo apache2.conf es el archivo de configuración principal de Apache2 y contiene configuraciones globales para el servidor web.
<Directory>: Aquí se establecen configuraciones globales para directorios, como opciones de seguimiento y restricciones de acceso.
<Files>: Similar a <Directory>, pero se aplica a archivos específicos.
<Location>: Configura ajustes para ubicaciones URL específicas.
<VirtualHost>: Define la configuración de los host virtuales, que permite alojar múltiples sitios web en un mismo servidor.

## • sites-available y sites-enabled: Explica la diferencia entre estos dos directorios
## y cómo funcionan juntos.
sites-available: Este directorio contiene archivos de configuración para los sitios web disponibles en Apache2. Cada archivo representa la configuración de un sitio web en particular.
sites-enabled: Aquí se encuentran los enlaces simbólicos a los archivos de configuración de los sitios web que están habilitados actualmente. Los archivos en este directorio son enlaces simbólicos a los archivos en sites-available. Apache2 solo servirá los sitios web que estén habilitados en sites-enabled. Esto permite habilitar y deshabilitar sitios web de manera fácil y segura sin tener que eliminar los archivos de configuración.

## • mods-available y mods-enabled: Explica la diferencia entre estos dos
## directorios.
mods-available: Contiene archivos de configuración para los módulos de Apache2 disponibles. Cada archivo corresponde a un módulo específico.
mods-enabled: Similar a sites-enabled, este directorio contiene enlaces simbólicos a los archivos de configuración de los módulos habilitados actualmente. Los módulos habilitados son los que Apache2 cargará y utilizará en el servidor.


**parte 6**
## ¿Dónde se encuentran los ficheros de ejecución de Apache2?
## • Ubicación principal
Los archivos ejecutables principales de Apache2 se encuentran en /usr/sbin/.

## • Control del servicio: Utiliza el binario de ejecución para iniciar, detener,
## recargar y reiniciar el servidor Apache2 explicando la diferencia entre cada uno
## de los comandos utilizados.
sudo systemctl start apache2: Inicia el servidor Apache2.
sudo systemctl stop apache2: Detiene el servidor Apache2.
sudo systemctl restart apache2: Detiene y luego inicia nuevamente el servidor Apache2 para aplicar cambios de configuración.
sudo systemctl reload apache2: Vuelve a cargar la configuración de Apache2 sin detener el servidor. Esto es útil cuando realizas cambios de configuración y no deseas interrumpir el servicio.
sudo systemctl status apache2: Muestra el estado actual del servicio Apache2, incluyendo si está en ejecución o detenido y si hay algún error en el registro.

## • Comprobación de sintaxis: Usa el binario de Apache para verificar la sintaxis
## de tu configuración. Esto es útil para asegurarse de que no haya errores antes
## de reiniciar el servidor.
sudo apachectl -t: Verifica la sintaxis de la configuración de Apache2 y muestra si hay errores. Esto es útil para detectar problemas de configuración antes de reiniciar el servidor. Si no hay errores, verás un mensaje que indica que la sintaxis es válida.


**parte 7**
## ¿Dónde se encuentran los ficheros de monitorización de Apache2?
## • Ubicación principal
Los archivos de registro principales de Apache2 se encuentran en el directorio /var/log/apache2/.

## • error.log y access.log: Explica la diferencia entre estos dos archivos. Abre y
## revisa las entradas recientes en cada uno de ellos.
error.log: Contiene registros de errores y problemas en el servidor web. Se utiliza para identificar y solucionar problemas de funcionamiento del servidor.
![image](https://github.com/anMarchena/despliegue-de-aplicaciones-web/assets/107402815/72e0331a-75bb-4d37-8a85-d3ecd739a6ae)

access.log: Registra todas las solicitudes entrantes, lo que permite el seguimiento de quién accede al servidor, qué recursos se solicitan y cuándo. Es útil para el análisis de tráfico y el seguimiento de las interacciones de los clientes.
![image](https://github.com/anMarchena/despliegue-de-aplicaciones-web/assets/107402815/c67b2676-e3b4-4b0a-b910-2aafdddcd7f6)

## • Rotación de logs: Investiga cómo funciona la rotación de logs en Apache2.
## ¿Por qué es importante? ¿Cómo se configura?
La rotación de logs es importante para evitar que los archivos de registro ocupen demasiado espacio en disco y para mantener un registro de eventos pasados. En Apache2, la rotación de logs está configurada mediante el programa logrotate, que automáticamente archiva y comprime los archivos de registro. Puedes encontrar la configuración de rotación de logs de Apache2 en el archivo /etc/logrotate.d/apache2.

## • Monitorización en tiempo real: Utiliza herramientas como tail -f para monitorear
## en tiempo real los accesos a tu servidor web y posibles errores.
![image](https://github.com/anMarchena/despliegue-de-aplicaciones-web/assets/107402815/e9a9c902-a064-4ce5-abd4-14439d86d82d)

## • Análisis de logs: Instala y usa herramientas como goaccess para analizar y
## obtener estadísticas visuales a partir de tus logs de Apache2.
![image](https://github.com/anMarchena/despliegue-de-aplicaciones-web/assets/107402815/5390dfb4-dc8e-4e2e-8518-d7b19931a11f)


** parte 8**
## ¿Qué es un Firewall?
Un firewall es una medida de seguridad que actúa como una barrera entre una red o sistema y el tráfico no autorizado o potencialmente peligroso que intenta ingresar

## ¿Para qué sirve?
 Su función principal es controlar y filtrar el tráfico de red, permitiendo o bloqueando el paso de acuerdo con reglas y políticas de seguridad definidas.

## ¿Por qué es necesario?
 Los firewalls son necesarios para proteger las redes y sistemas contra amenazas en línea, como intrusiones, malware, ataques de denegación de servicio (DoS) y otros riesgos de seguridad.

## Instalacion de firewall:

Primero instalamos iptables:
![image](https://github.com/anMarchena/despliegue-de-aplicaciones-web/assets/107402815/fca95794-9b9a-4d4f-a813-21b179df1cc8)

Configuramos iptables poniendo lo siguiente:
![image](https://github.com/anMarchena/despliegue-de-aplicaciones-web/assets/107402815/ad676dcc-f41f-4c23-9f0c-6109a7963c50)

Guardamos las reglas:
![image](https://github.com/anMarchena/despliegue-de-aplicaciones-web/assets/107402815/99462162-39f2-400b-b1c6-d346f4d71d87)

Miramos si va:
![image](https://github.com/anMarchena/despliegue-de-aplicaciones-web/assets/107402815/b47e8a2f-611c-4e4a-b3e8-68f5321f3cae)


**parte 9**

Esquema (Protocolo): Es como el tipo de "idioma" que se utiliza para comunicarse con un sitio web. Puede ser "http://" para páginas web normales o "https://" para páginas web seguras.

Nombre del sitio (Dominio): Es la dirección del sitio web, como "www.ejemplo.com".

Ruta: Es como la dirección dentro del sitio web que te lleva a la página o recurso que quieres, como "/productos/pagina.html".

Consulta: A veces, se utiliza para enviar información adicional al sitio web, como una búsqueda. Empieza con "?" y podría verse así: "?q=ejemplo".

Fragmento: Es como un marcador de página dentro de una página web, apuntando a una sección específica. Comienza con "#" y se ve así: "#seccion".


**parte 10**

Primero el navegador indica la pagina que quiere que se muestre.

Luego el servidor entiende la request y obtiene la direccion.

Seguidamente, el servidor envia esta direccion al ordenador.

Por ultimo, se muesta la pagina deseada en el navegador del ordenador.


**parte 11**

Un archivo .htaccess es un archivo de configuración utilizado en servidores web Apache para realizar cambios en la configuración y comportamiento del servidor en un directorio específico o en sus subdirectorios. Puedes utilizarlo para controlar el acceso, configurar redirecciones, establecer reglas de reescritura de URL y más.

Un ejemplo de como usar uno es el siguiente:
Si se desea redirigir todas las solicitudes de una antigua pagina a una pagina nueva, see puede agregar el siguiente código al archivo .htaccess:

RewriteEngine On
RewriteRule ^antigua$ nueva [L,R=301]
