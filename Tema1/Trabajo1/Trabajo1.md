**1) Instalación del servidor web apache. Usaremos dos dominios mediante el archivo hosts: centro.intranet y departamentos.centro.intranet. El primero servirá el contenido mediante wordpress y el segundo una aplicación en python</font>**



Primero hago un update de apt

![update](1.png)


Luego procedo a instalar Apache

![installapache](2.png)

A continuacion tenemos que configurar los hosts, usando nano, accedemos al archivo y agregamos las dos siguientes lineas

![hosts](3.png)
![hosts2](4.png)

Y reiniciamos apache

![reset](5.png)

Ahora debemos crear y configurar los archivos de VirtualHost

![config](6.png)

Dentro de cada respectivo archivo de configuracion debemos colocar las siguientes lineas

![configCodigo1](7.png)
![configCodigo2](9.png)

A continuacion creamos los directorios correspondiente y le damos los permisos pertinentes

![mkdir](10.png)

Habilitamos ambos sitios y reiniciamos apache nuevamente

![permisos](11.png)



**Activar los módulos necesarios para ejecutar php y acceder a mysql**



Procedemos a activar php (En mi caso ya tenia instalado php, de no ser el caso, primero se haria un sudo apt-get install php)

![moduloPHP](12.png)

Activamos el modulo de apache para el manejo de URLs en WordPress y reiniciamos apache

![moduloApache](13.png)

Ahora procedemos a instalar MySql, mas un reset de apache

![installSQL](14.png)



**Instala y configura wordpress**



Debemos crear una base de datos y para ello vamos a utilizar nuestro recien instalado MySQL
Primero iniciamos sesion en MySQL

![sesion](15.png)

Una vez dentro, debemos crear una base de datos, introduciendo estos datos (donde pone "sergio" es el nombre del usuario, se le puede dar el que prefiera y el numero "171990" es la contraseña, nuevamente, se pone la que se prefiera)

![tablas](16.png)

Ahora vamos a proceder a descargar e instalar WordPress

nos movemos al directorio /tmp y descargamos el .tar de wordpress

![tar](17.png)

Ejecutamos el tar que se encargara de descargar los componentes necesarios para instalar wordpress

![tar2](18.png)

Movemos los archivos al directorio raiz y les concedemos permisos

![mover](19.png)

A continuacion nos movemos nosotros al directorio de wordpress, creamos una copia de la plantilla de configuracion y accedemos a ella

![copia](20.png)

Aqui debemos definir la conexion a la base de datos, usando el nombre y constreseña que pusimos

![conexion](21.png)

Debemos tambien agregar el .htaccess, por lo que usando nano, accedemos y agregamos el siguiente codigo

![htaccess](22.png)

Seguidamente le damos permisos

![permisos](23.png)

Ahora podemos ir al localhost/worlpress y si lo hemos hecho bien debia salir el asistente de instalacion

![asistente](24.png)

Seguimos los pasos de instalacion y todo transcurre correctamente, podremos acceder a nuestro recien instalado WordPress

![instalado](25.png)



**Activar el módulo “wsgi” para permitir la ejecución de aplicaciones Python**



Como con otras aplicaciones, instalamos wsgi, la habilitamos y reiniciamos apache

![installwsgi](26.png)



**Crea y despliega una pequeña aplicación python para comprobar que funciona correctamente.**



Creamos nuestra aplicacion, yo he optado por un simple Hola mundo

![app](27.png)

Debemos configurar apache para que maneje la aplicacion, accedemos como otras veces y agregamos el siguiente codigo. Teniendo encuenta las rutas de nuestra app

![manejo](28.png)

Si todo est bien, accediendo a localhost/phyton-app, podremos ver nuestra app

![hola](29.png)



**Adicionalmente protegeremos el acceso a la aplicación python mediante autenticación**



Primero debemos crear un archivo para nuestra contraseña, ojo, te pedira que introduzcas una contraseña, no la olvides

![pass](30.png)

En el, debemos introducir el siguiente codigo, guardamos y reiniciamos apache, con esto ya estaria protegido

![codigo](31.png)



**Instala y configura awstat.**



Como otros veces, instalamos la aplicacion con el siguiente codigo

![installawstats](32.png)

Ahora debemos configurarlo, por lo que accedemos a este

![confaws](33.png)

E introducimos el siguiente codigo

![code](34.png)

Ahora debemos crear el archivo de configuracion del sitio

![configsite](35.png)

Seguidamente tenemos que crear un enlace simbolico, su directorio y darles los permisos necesarios

![enlace](36.png)

Tambien necesitaremos configurar AQStats para generar los informes, siempre y cueando no se encuentre la siguiente linea, deberemos introducirla nosotros

![linea](37.png)

Lo siguiente es configurar el acceso a las estadisticas

![acceso](38.png)

Finalmente habilitamos y reiniciamos apache

![habilitar](39.png)



**Instala un segundo servidor de tu elección (nginx, lighttpd) bajo el dominio “servidor2.centro.intranet”. Debes configurarlo para que sirva en el puerto 8080 y haz los cambios necesarios para ejecutar php. Instala phpmyadmin.**



Instalamos Nginx como otros aplicaciones

![installNginx](40.png)

Creamos su respectivo archivo de configuracion con el siguiente codigo

![confNginx](41.png)

Ahora instalamos phpMyAdmin (durante la instalacion seleccionamos Nginx)

![installmyadmin](42.png)

Debemos de agregar al archivo de nginx del site para permitir el acceso a phpMyAdmin el siguiente codigo

![accsmyadmin](43.png)

Y con eso ya tendriamos todo completado.
