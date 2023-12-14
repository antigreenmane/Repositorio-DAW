<span style="font-size:larger;">**1) Instalación del servidor web apache. Usaremos dos dominios mediante el archivo hosts: centro.intranet y departamentos.centro.intranet. El primero servirá el contenido mediante wordpress y el segundo una aplicación en python</font>**</span>


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

Activar los módulos necesarios para ejecutar php y acceder a mysql

