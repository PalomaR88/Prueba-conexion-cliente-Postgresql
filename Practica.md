# Prueba de conexión remota desde un cliente para PostgreSQL
En este punto se van a establecer los pasos a seguir para realizar una conexión de un cliente de Postgres de forma remota. Este ejercicio se va a realizar sobre un sistema operativo Debian 10.

### Instalación del cliente de Postgres
El paquete que se necesita es el siguiente:
~~~
$ sudo apt install postgresql-client
~~~

### Conexión entre cliente y servidor
Desde la terminal, se utiliza el comando psql con las siguientes opciones:
- **-h**: para indicar la IP del servidor de Postgres.
- **-U**: para indicar el usuario desde el que se va  a acceder a la base de datos.
- **-d**: para indicar el nombre de la base de datos a la que se va a acceder.

~~~
root@cliente: /home/cliente# psql -h 172.22.9.121 -U guarderia -d guarderia_db
Contraseña para usuario guarderia:
psql (9.4.24, servidor 11.5 (Debian 11.5-1+deb10u1))
ADVERTENCIA: psql versión mayor 9.4, servidor versión mayor 11.
        Algunas características de psql podrían no funcionar.
Conexión SSL (protocolo: TLSv1.2, cifrado: ECDHE-RSA-AES256-GCM-SHA384, bits: 256, compresión: desactivado)
Digite «help» para obtener ayuda.

guarderia_db=> \d
        Listado de relaciones
 Esquema |  Nombre  | Tipo  |   Dueño
---------+----------+-------+-----------
 public  | mascotas | tabla | guarderia
 public  | pagos    | tabla | guarderia
 public  | personas | tabla | guarderia
(3 filas)

guarderia_db=>
~~~