**Instalación, configuración y puesta en marcha de un servidor que ofrezca servicio de alojamiento web configurable**

***1)Instalacion de servicios***

Instalamos vsftpd y ssh.
Otras como Apache, php y phpmyadmin. Ya deberian estar instaladas de ejercicios anteriores.

![install](1.png)
![install](2.png)

***2)Configuracion de los servicios***

Creamos un directorio para el sitio web, le damos permisos al directorio y creamos el archivo de configuracion del virtual host.

![config](3.png)

Dentro del archivo de configuracion agregamos estas lineas.

![config](4.png)

Lo activamos creando el enlace simbolico y reinicamos el servidor.

![activar](5.png)

Ajustamos la configuracion host

![host](6.png)
![host](7.png)

Y comprobamos que todo funciona.

![prueba](8.png)

Genial, ahora configuramos el vsftpd para el acceso FTP seguro (TLS).

![FTP](9.png)
![FTP](10.png)

Y lo reiniciamos

![FTP](11.png)

***3)Automatizacion mediante Scripts***

Los siguientes procesos los podemos actualizar.

Empecemos por la creacion de los usuarios, por lo creamos el archivo con nano y lo editamos.

![Auto](12.png)

Una vez tengamos nuestro Script, debemos darle permiso y posteriormente, podemos ejecutarlo

![Auto](13.png)

Ahora crearemos el sistema para acceso a ftp, ssh, smtp. Por lo que nuevamente creamos el archivo

![Auto](14.png)

Le damos permisos y ejecutamos

![Auto](15.png)

Aqui podemos ver que la contraseña que use, era debil o mas bien no cumplia con los requisitos. Por lo que cambiamosla a una mas segura

![Auto](16.png)

La Ejecutamos y veremos que nos dice que el usuario ya existe, ya que lo ejecutamos antes, pero ya no da problemas con la contraseña.

![Auto](17.png)

Para el siguiente Script, antes necesitamos tener instalado bind, en caso negativo, lo instalamos igual que hicimos con otros servicios.

![Bind](18.png)

Una vez instalado podemos automatizar los servidores DNS con otro Script.

![Auto](19.png)

Nuevamente, le damos permisos y lo ejecutamos.

![Auto](20.png)

Para asegurarnos de que se han creado correctamente podemos usar CAT.

![Cat](21.png)

LLegados hasta aqui, ahora debemos crear el Script para la creacion de la base de datos con todos los permisos.
Como otras veces, creamos el archivo.

![Auto](22.png)

Nuevamente, le damos permisos y ejecutamos.

![Auto](23.png)

Por ultimo, debemos automatizar la habilitacion de Python. Creamos un ultimo archivo.

![Auto](24.png)

Y para finalizar, permisos y ejecutamos.

![Auto](25.png)
