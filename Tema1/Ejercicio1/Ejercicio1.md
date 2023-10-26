Paso 1: Instalar Apache

Primero hago un update de apt

![update](update.png)

Y ahora procedo a instalar Apache con el administrador de paquetes de Ubuntu, apt

![Instalar](install.png)

Si la he realizado correctamente, ahora al dirigirme a Localhost deberia aparecer la pagina principal de apache

![Prueba](comprobacion.png)

Paso 2: Instalar MySQL.

Ahora procedo a realizar la misma instalacion con SQL.

![SQLins](sqlinstall.png)

Cuando la instalación se complete, es recomendable ejecutar una secuencia de comandos de seguridad que viene preinstalada en MySQL.
Saldran una serie de pregunta e ire eligiendo que quiero activar y que no.

![SQLsec](securesql.png)

Ahora puedo comprobar si esta instalado correctamente.

![PruebaSQL](comprobacionsql.png)

Paso 3: Instalar PHP

Vuelvo a repetir los procesos anteriores pero ahora con PHP.

![PHPins](phpinstall.png)

Y si lo he hecho bien deberia reconocermelo la terminal.

![PruebaPHP](comprobacionphp.png)

Paso 4: Crear un host virtual para su sitio web

Para crearlo primero necesito crear un entorno donde guardar el dominio.

![hos1](hostvirtual1.png)

A continuación, asigno la propiedad del directorio con la variable de entorno $USER

![hos2](hostvirtual2.png)

Lo siguiente es configurarlo y accedemos a dicha configuracion con el siguiente codigo.

![hos3](hostvirtual3.png)

Agregamos las siguientes lineas en la lista de la configuracion.

![hos4](hostvirtual4.png)

Y a continuacion activo nuestro host virtural

![hos5](hostvirtual5.png)

Para evitar que se abra el host de Apache en lugar del nuestro procedo a desactivarlo

![hos6](hostvirtual6.png)

Continuo ahora haciendo una comprobacion para que el codigo no tenga errores de sintaxis.

![hos7](hostvirtual7.png)

Y finalmente vuelvo a cargar Apache para que los cambios surtan efecto.

![hos8](hostvirtual8.png)

Bien, el sitio web esta activo, pero el dominio esta vacio, ahora procedo a crear un index.html

![hos9](hostvirtual9.png)

Le añado un poco de contenido a dicho index.

![hos10](hostvirtual10.png)

Y finalmente volvemos a probar nuestro localhost

![hos11](hostvirtual11.png)
