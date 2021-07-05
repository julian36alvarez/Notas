# Curso de PostgreSQL

![image](https://user-images.githubusercontent.com/31891276/124500606-b01cd300-dd85-11eb-91b5-cb8f0ca03619.png)

## ¿Qué es Postgresql?.

![image](https://user-images.githubusercontent.com/31891276/124499732-1f91c300-dd84-11eb-94cf-845a99ffcc56.png)

PostgreSQL es un Motor de bases de datos
1. Lenguaje.
2. Motor.
3. Servidor.

PostgreSQL es Open source, usa objeto-relacional, usa sql.
PostGis es un servicio de geolocalizacion que se puede implenatar en postgres.

cumple el standar.

![image](https://user-images.githubusercontent.com/31891276/124499969-857e4a80-dd84-11eb-8100-f5d5e85e279a.png)

• A: Atomicity – Atomicidad -> Separar las funciones desarrolladas en la BD como pequeñas tareas y ejecutarlas como un todo. Si alguna tarea falla se hace un rollback(Se deshacen los cambios)
• C: Consistency – Consistencia -> Todo lo que se desarrolló en base al objeto relacional. Los datos tienen congruencia
• I: Isolation – Aislamiento -> Varias tareas ejecutándose al mismo tiempo dentro de la BD
• D: Durability – Durabilidad -> Puedes tener seguridad que la información no se perderá por un fallo catastrófico. PostgreSQL guarda la información en una Bitácora.

## 3. Instalación y configuración de la Base de Datos.

![image](https://user-images.githubusercontent.com/31891276/124500255-0d645480-dd85-11eb-8b27-a5d231628cb5.png)


Para saltar a la base de datos recién creada ejecutamos el comando “\c transporte_publico”, el cursor mostrará lo siguiente:

![image](https://user-images.githubusercontent.com/31891276/124502956-1b68a400-dd8a-11eb-9d36-5a9ab7a75d00.png)


Aca vemos nustra base de datos en PGAdmin

![image](https://user-images.githubusercontent.com/31891276/124503183-9e89fa00-dd8a-11eb-9015-ef05054b9a8a.png)

## 4. Interacción con Postgres desde la Consola.

**ENTRAR A LA CONSOLA DE POSTGRES**

    psql -U postgres -W
        
**VER LOS COMANDOS \ DE POSTGRES**

    \?
    
**LISTAR TODAS LAS BASES DE DATOS**

    \l
    
**VER LAS TABLAS DE UNA BASE DE DATOS**

    \dt
    
**CAMBIAR A OTRA BD**

    \c nombre_BD
    
**DESCRIBIR UNA TABLA**

    \d nombre_tabla
    
**VER TODOS LOS COMANDOS SQL**

    \h
    
**VER COMO SE EJECTUA UN COMANDO SQL**

    \h nombre_de_la_funcion
  
**CANCELAR TODO LO QUE HAY EN PANTALLA**

    Ctrl + C
  
**VER LA VERSION DE POSTGRES INSTALADA, IMPORTANTE PONER EL ';'**

    SELECT version();
  
**VOLVER A EJECUTAR LA FUNCION REALIADA ANTERIORMENTE**

    \g
  
**INICIALIZAR EL CONTADOR DE TIEMPO PARA QUE LA CONSOLA TE DIGA EN CADA EJECUCION ¿CUANTO DEMORO EN EJECUTAR ESA FUNCION?**

    \timing 
  
**LIMPIAR PANTALLA DE LA CONSOLA PSQL**

    Ctrl + L

## 5 PgAdmin: Interacción con Postgres desde la Interfaz Gráfica

![image](https://user-images.githubusercontent.com/31891276/124504182-8f0bb080-dd8c-11eb-801d-b1ab93756401.png)

![image](https://user-images.githubusercontent.com/31891276/124505671-a0a28780-dd8f-11eb-96be-5033ab1a85d6.png)

## 6. Archivos de Configuración.

![image](https://user-images.githubusercontent.com/31891276/124505710-b7e17500-dd8f-11eb-8705-efd4139a6633.png)

![image](https://user-images.githubusercontent.com/31891276/124505724-c039b000-dd8f-11eb-8ea8-6b03469924ee.png)

Resumen de archivos de configuración.

A través de la sentencia SHOW CONFIG se nos muestra donde están los archivos de configuración. En mi caso la ruta es:

"C:/Program Files/PostgreSQL/12/data/postgresql.conf"

Postgresql.conf: Configuración general de postgres, múltiples opciones referentes a direcciones de conexión de entrada, memoria, cantidad de hilos de pocesamiento, replica, etc.

pg_hba.conf: Muestra los roles así como los tipos de acceso a la base de datos.

pg_ident.conf: Permite realizar el mapeo de usuarios. Permite definir roles a usuarios del sistema operativo donde se ejecuta postgres

## 7. Comandos más utilizados en PostgreSQL

La consola en PostgreSQL es una herramienta muy potente para crear, administrar y depurar nuestra base de datos. podemos acceder a ella después de instalar PostgreSQL y haber seleccionado la opción de instalar la consola junto a la base de datos.

PostgreSQL está más estrechamente acoplado al entorno UNIX que algunos otros sistemas de bases de datos, utiliza las cuentas de usuario nativas para determinar quién se conecta a ella (de forma predeterminada). El programa que se ejecuta en la consola y que permite ejecutar consultas y comandos se llama psql, psql es la terminal interactiva para trabajar con PostgreSQL, es la interfaz de línea de comando o consola principal, así como PgAdmin es la interfaz gráfica de usuario principal de PostgreSQL.

Después de emitir un comando PostgreSQL, recibirás comentarios del servidor indicándote el resultado de un comando o mostrándote los resultados de una solicitud de información. Por ejemplo, si deseas saber qué versión de PostgreSQL estás usando actualmente, puedes hacer lo siguiente:

En consola los dos principales comandos con los que podemos revisar el todos los comandos y consultas son:

\? Con el cual podemos ver la lista de todos los comandos disponibles en consola, comandos que empiezan con backslash ()

\h Con este comando veremos la información de todas las consultas SQL disponibles en consola. Sirve también para buscar ayuda sobre una consulta específica, para buscar información sobre una consulta específica basta con escribir \h seguido del inicio de la consulta de la que se requiera ayuda, así: \h ALTER

Comandos de navegación y consulta de información

\c Saltar entre bases de datos.

\l Listar base de datos disponibles.

\dt Listar las tablas de la base de datos.

\d <nombre_tabla> Describir una tabla.

\dn Listar los esquemas de la base de datos actual.

\df Listar las funciones disponibles de la base de datos actual.

\dv Listar las vistas de la base de datos actual.

\du Listar los usuarios y sus roles de la base de datos actual.

## 8. Presentación del Proyecto.

![image](https://user-images.githubusercontent.com/31891276/124518053-1bc56700-ddab-11eb-96dd-132cf6ee704a.png)

## 9. Tipos de datos.

![image](https://user-images.githubusercontent.com/31891276/124518101-3d265300-ddab-11eb-9fa2-1a83402187e2.png)

![image](https://user-images.githubusercontent.com/31891276/124518111-41527080-ddab-11eb-9931-f70a88575c3e.png)

https://www.postgresql.org/docs/11/datatype.html

## 10. Diseñando nuestra base de datos: estructura de las tablas.
    
   1. Objetos Tangibles.
   2. Relaciones

![image](https://user-images.githubusercontent.com/31891276/124518350-c76eb700-ddab-11eb-87fc-024c3328a0c7.png)

## 11. Jerarquía de Bases de Datos.

1. Toda jerarquía de base de datos se basa en los siguientes elementos:
2. Servidor de base de datos: Computador que tiene un motor de base de datos instalado y en ejecución.
3. Motor de base de datos: Software que provee un conjunto de servicios encargados de administrar una base de datos.
4. Base de datos: Grupo de datos que pertenecen a un mismo contexto.
5. Esquemas de base de datos en PostgreSQL: Grupo de objetos de base de datos que guarda relación entre sí (tablas, funciones, relaciones, secuencias).
6. Tablas de base de datos: Estructura que organiza los datos en filas y columnas formando una matriz.

PostgreSQL es un motor de base de datos.

La estructura de la base de datos diseñada para el reto corresponde a los siguientes
elementos:

![image](https://user-images.githubusercontent.com/31891276/124518489-20d6e600-ddac-11eb-9572-98d118b62077.png)


![image](https://user-images.githubusercontent.com/31891276/124518516-35b37980-ddac-11eb-881e-8f3efd5cb403.png)

## 12. 


