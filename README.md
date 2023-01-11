# debfoster
Limpieza paqutes del sistema. Para mantener solo los paquetes esenciales y eliminar los que ya no se necesitan.
Debfoster utilizará esta lista para detectar que los paquetes se han instalado solo porque otros paquetes dependían de ellos.


La lista de paquetes instalados y se guardará en un archivo denominado keepers en el directorio
/var/lib/debfoster/




#INSTALAR DEBFOSTER 

comando: sudo aptinstall debfoster

#USAR DEBFOSTER

Crea la lista de paquetes instalados.
Una vez instalado, debemos crear la lista de paquetes instalados.
Comando: sudo debfoster -q

#ELIMINAR PAQUTES QUE NO FIGUREN EN NUESTRA LISTA
Podemos forzar a la utilidad a eliminar lso paquetes que no figuran en el archivo keepers

Comando debfoster -f

Debfoster eliminará todos los paquetes que no estén disponibles en el archivo keepers, junto con sus dependecias.

Despues de esto, podemos ejecutar el siguiente comando de vez en cuando o después de agregar/eliminar paquetes

Comando: sudo debfoster

Si has instalado / eliminado algún paquete Debfoster te preguntará qué quieres hacer. Si no está seguro de qué hacer,
escribe H para ver las opciones disponibles.


#Visualización de paquetes en la lista Keepers

Para ver la lista de paquetes en la base de datos.

Comando: debfoster -a


#Usar una base de datos diferente
Por defecto, se mantendrán los paquetes instalados en el archivo /var/lib/debfoster/keepers

Si queremos especificar una base de datos diferente ( un archivo keeper, por su puesto ) utilizaremos la opción-k 

Comando: debfoster -k /ruta/hacia-el/nuevo/archivo/keepers

#Ver paquetes huérfanos
No siempre es necesiario ejecutar el comando <<sudo debfoster>> para verificar los paquetes huérfanos. Esta función la podremos realizar añadiendo la opción -s:

Comando: debfoster -s

En el caso de tener algún paquete huérfano, pero lo consideramos necesario y no queremos que Debfoster lo elimine, simplemente lo agregamos al archivo keeprs.
Para hacerlo. editamos el archivo:
    /var/lib/debfoster/keepers y agregamos el nombre de este programa

#Agregar/eliminar paquetes

Como esta utilidad es un contenedor para los administradores de paquetes apt-get y dpkg, también podremos usarlo para agregar o eliminar paaquetes

Comando: sudo debfoster screen

Ahora Debfster ejecutará apt-get e instalará el paquete especificado.

Para eliminar un paquete, simplemente colocaremos un signo menos ( - ) directamnete después del nombr del paquete

sudo debfoster screen-

#ENCONTRAR DEPENDENCIAS

Para enumerar los paquetes de los que depende un paquete:

Comando: opción -d

Comando debfoster -d screen

Para enumerar todos los paquetes en la base de de datos de la utilidad que dependen del paquete dado, utilizaremos la opción-e

Comando: debfoster -e nombre-del-paquete

#Comando ayuda

Comando: man debfoster


