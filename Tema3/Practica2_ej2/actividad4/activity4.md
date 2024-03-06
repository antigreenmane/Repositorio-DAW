[volver](../Ejercicio2.md)


***Ejemplo 1: Despliegue de la aplicación Guestbook***

Vamos a desplegar una aplicación web que requiere de dos servicios (servicio web y servicio de base de datos)

Para esto necesitaremos los siguientes servicios:

La aplicación guestbook es una aplicación web desarrollada en python que es servida por el puerto 5000/tcp. Utilizaremos la imagen iesgn/guestbook.
Esta aplicación guarda la información en una base de datos no relacional redis, que utiliza el puerto 6379/tcp para conectarnos. Usaremos la imagen redis.


Primeros creamos un red comun para estos

![red](1.png)

Ahora debemos ejecutar los contenedores, siendo este para Redis

![redis](2.png)

y este otro para iesgn/guestbook

![guestbook](3.png)

Finalmente comprobamos su funcionamiento

![prueba](4.png)




***Ejemplo 2: Despliegue de la aplicación Temperaturas***

Vamos a hacer otro ejemplo, la practica viene a ser la misma, solo que esta vez sera una aplicación que nos permite consultar
la temperatura mínima y máxima de todos los municipios de España. Esta aplicación está formada por dos microservicios:frontend y backend

Creamos una nueva red

![red](5.png)

Iniciamos el backend

![backend](6.png)

y ahora el frontend

![frontend](7.png)

Finalmente comprobamos

![prueba](8.png)



***Ejemplo 3: Despliegue de Wordpress + mariadb***

Para la instalación de WordPress necesitamos dos contenedores: la base de datos (imagen mariadb) y el servidor web con la aplicación (imagen wordpress). 
Los dos contenedores tienen que estar en la misma red y deben tener acceso por nombres.

Nuevamente, lo primero sera rear la red

![red](9.png)

Ejecutamos el contenedor de mariadb

![mariadb](10.png)

El contenedor de wordpress

![wordpress](11.png)

Y probamos que funciona

![prueba](12.png)




[volver](../Ejercicio2.md)
