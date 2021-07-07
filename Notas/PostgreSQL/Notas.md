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

## 12. Creación de Tablas.

![image](https://user-images.githubusercontent.com/31891276/124518643-92af2f80-ddac-11eb-856b-aed9142265a6.png)

## 13. Particion de Tablas.

![image](https://user-images.githubusercontent.com/31891276/124519462-05b9a580-ddaf-11eb-9f0f-04f562574822.png)

![image](https://user-images.githubusercontent.com/31891276/124521269-88912f00-ddb4-11eb-8e3e-cd18dd72c3f6.png)

    
    CREATE TABLE public.bitacora_viaje
    (
        id integer NOT NULL DEFAULT nextval('bitacora_viaje_id_seq'::regclass),
        id_viaje integer,
        fecha date
    ) PARTITION BY RANGE (fecha);

    ALTER TABLE public.bitacora_viaje
        OWNER to postgres;

    -- Partitions SQL

    CREATE TABLE public.bitacora_viaje20102021 PARTITION OF public.bitacora_viaje
        FOR VALUES FROM ('2010-01-01') TO ('2021-12-31');

    ALTER TABLE public.bitacora_viaje20102021
        OWNER to postgres;

no es posible crear llaves primarias en particiones.

## 14. Creacion de Roles.

![image](https://user-images.githubusercontent.com/31891276/124521798-79ab7c00-ddb6-11eb-9b3f-060d77f58171.png)


![image](https://user-images.githubusercontent.com/31891276/124523145-6ea71a80-ddbb-11eb-9495-00c365c25766.png)

## 15. Llaves foráneas

![image](https://user-images.githubusercontent.com/31891276/124523590-4e785b00-ddbd-11eb-8977-d9132ad8cda2.png)

Opciones de las foreing Keys son: 
Deferreable (Aplazar validación)
Deferred (Apenas se crea se válida)
Match Type (SIMPLE=VALOR A VALOR OR FULL=COMPLEJA)
Validated (Iniciamos las tablas con la validación)
Auto FK Index (No es un indice de la tabla)

En la pestania Action le tenemos que decir que hacer a la base de datos entre la tabla origen y la tabla destino cuando ocurra un cambio:

NO ACTION: No hacer nada.

RESTRICT: Decirle a Postgres que no podemos permitir que la tabla cambie algo.

CASCADE: Si cambio la tabla de origen, la tabla destino tambien cambia.

SET NULL quiere decir que nuestra columna en esa fila va a dejar de tener por ejemplo el ID que tenia asociado un 77 y va a convertirse en NULL. Esto por que la tabla destino recibe un cambio y le decimos aPostgres que lo ponga en nulo.

SET DEFAULT: Si hay un cambio en la tabla origen nuestra tabla destino ponga un valor predeterminado. En un ejemplo un id podra quedar NULL.

## 16. Inserción y consulta de datos.
    INSERT INTO public.trayecto(
        id_tren,id_estacion)
        VALUES ( 1 ,1);
## 17. Inserción masiva de datos.

Insertar Datos de manera masiva.

    https://mockaroo.com/
    
## 18. Cruzar tablas: SQL JOIN

![image](https://user-images.githubusercontent.com/31891276/124615230-aef9ad80-de3a-11eb-86ae-83aabc508bd1.png)

![image](https://user-images.githubusercontent.com/31891276/124615318-c20c7d80-de3a-11eb-81bb-ea1b07deb62d.png)

## 19. Funciones Especiales Principales.

![image](https://user-images.githubusercontent.com/31891276/124615858-3cd59880-de3b-11eb-9c2c-7bab8e39e75d.png)

**ON CONFLICT DO**

Esta instruccion nos permite especificar que debemos hacer en caso de un conflicto.
Ejemplo: Imaginamos que realizamos una consulta donde el id ya ha sido utilizado. Podemos especificar que en ese caso, actualize los datos.

    INSERT INTO pasajero (id, nombre, direccion_residencia, fecha_nacimiento)
        values (1, '', '','2010-01-01')
        ON CONFLICT (id) DO 
        UPDATE SET 
        nombre = '', direccion_residencia='', fecha_nacimiento='2010-01-01';

**RETURNING**

Returning nos devuelve una consulta select de los campos sobre los que ha tenido efecto la instruccion.
Ejemplo: Queremos saber cual es el id que le fue asignado a un dato insertado.

    INSERT INTO tren (modelo, capacidad)
         VALUES('modelo x', 100)
         RETURNING id;
    /*
    Opcionalmente tambien puedes solicitar todos los campos o alguno de ellos
    */

    INSERT INTO tren (modelo, capacidad)
         VALUES('modelo x', 100)
         RETURNING id;

    INSERT INTO tren (modelo, capacidad)
         VALUES('modelo x', 100)
         RETURNING id, capacidad;

**Like / Ilike**

Las funciones like y ilike sirven para crear consultas a base de expresiones regulares.
Like considera mayusculas y minusculas, mientras que ilike solo considera las letras.
Ejemplo: Busquemos a los pasajeros con nombre que terminen con la letra o


    -- Usando LIKE
    SELECT * FROM PASAJERO
    WHERE pasajero.nombre LIKE '%O'
    -- No devulve nada, porque ningun nombre terminara con una letra mayuscula


    -- Usando ILIKE
    SELECT * FROM PASAJERO
    WHERE pasajero.nombre LIKE '%O'
    -- Devolvera los nombres que terminen con o, independiente si es mayuscula o minuscula.
    
**IS / IS NOT**

Permite hacer comprobacion de valores especiales como null
Ejemplo: Consultemos a todos los usuarios que tengan como direccion_residencia NULL

    -- IS
    SELECT * FROM PASAJERO
    WHERE pasajero.nombre IS null;

    -- IS NOT
    SELECT * FROM PASAJERO
    WHERE pasajero.nombre IS NOT null;


## 20. Funciones Especiales Avanzadas

![image](https://user-images.githubusercontent.com/31891276/124619795-92f80b00-de3e-11eb-8f39-8112eff9fcf3.png)

**COALESCE**
Permite comparar dos valores y retornar cual no es null.

    SELECT coalesce(nombre,'No aplica') FROM PASAJERO where id=1

**NULLIF**
Nos permite comparar dos valores y retorna null si son Iguales.

    SELECT coalesce(nombre,'No aplica') FROM PASAJERO where id=1

**GREATEST**

Permite comparar un arreglo de valores y definir el mayor o el menor.

    select greatest(1,2,3,5,4,5,4,5,8,4,4,7)

**LEAST**

Permite ingresar condicionales dentro de una consulta de base de datos.

    select least(1,2,3,5,4,5,4,5,8,4,4,7)
    
**Bloques Anónimos**

    select id , nombre, fecha_naciemiento,
    case
    when fecha_naciemiento > '1999-01-01' then 'Es JOVEN' 
    ELSE 'ES UN CUCHO' END
    from pasajero
    
## 21 VISTAS

![image](https://user-images.githubusercontent.com/31891276/124627097-e2413a00-de44-11eb-8d26-1b85796fab65.png)

Tipos de vistas:
- Vista Volátil: Consulta con data actualizada
- Vista Materializada: Consulta con data persistente

## 22 PL/SQL

PL o procedimientos almacenados, tambien hacen parte de motor de postgresSQL
su estructura es sencilla y tiene una declaracion uso de varibles y un fin

![image](https://user-images.githubusercontent.com/31891276/124631014-91cbdb80-de48-11eb-9670-5892c6f3f295.png)

![image](https://user-images.githubusercontent.com/31891276/124631042-9bedda00-de48-11eb-9cdc-59904f96e029.png)

un bloque de codigo se ejecuta con la funcion do.

DO $$ para abrir
begin
$$ -- para cerrar

![image](https://user-images.githubusercontent.com/31891276/124631401-f9822680-de48-11eb-913b-c20e1a7b4664.png)

    do $$
    begin
        raise notice 'Algo esta pasando';
    end
    $$
    
    do $$
    declare
    rec record;
    contador integer :=0;
    begin
        FOR rec in select * from pasajero LOOP
            raise notice 'Un pasajero se llama %', rec.nombre;
            contador := contador +1;
        END LOOP;
    raise notice 'El Conteo es %', contador;	
    end
    $$
    
 **Función**
 
    create OR REPLACE function importantePL() 
        Returns integer
    as $$
    declare
    rec record;
    contador integer :=0;
    begin
        FOR rec in select * from pasajero LOOP
            raise notice 'Un pasajero se llama %', rec.nombre;
            contador := contador +1;
        END LOOP;
    raise notice 'El Conteo es %', contador;
    return contador;
    end
    $$
    language PLPGSQL;

    SELECT importantePL() 
    
 ## Triggers
 
 ![image](https://user-images.githubusercontent.com/31891276/124636330-0b19fd00-de4e-11eb-8073-88dc4e123d6d.png)


    CREATE OR REPLACE FUNCTION public.trigger_func()
    RETURNS trigger
    LANGUAGE 'plpgsql'
    VOLATILE
    COST 100
    AS $BODY$
    declare
    rec record;
    contador integer :=0;
    begin
            FOR rec in select * from pasajero LOOP
                raise notice 'Un pasajero se llama %', rec.nombre;
                contador := contador +1;
            END LOOP;
    --raise notice 'El Conteo es %', contador;
        insert into conteo_pasajeros(total, time)
        values (contador, now());
        return new
    END
    $BODY$;

Se crea el lanzador del trigger.

    CREATE TRIGGER mitrigger
    AFTER INSERT on pasajero for each row
    execute procedure trigger_func();


## 24. Simulando una conexión a Bases de Datos remotas

Hacemos Conexion a una base de datos remoto y la cruzamos con nuestra informacion.

    create extension dblink;

    select * from pasajero as pj
    join 
    (select * from dblink('dbname=remota 
           port=5432 
           host=127.0.0.1 
           user=usuario_consulta 
           password=1q2w3e4r5T', 'select * from vip') 
     as datos_remotos (id integer, fecha date, id_usuario integer)) as dt
    on  pj.id= dt.id_usuario
  
## 25. Transacciones.

![image](https://user-images.githubusercontent.com/31891276/124666936-56470680-de74-11eb-93af-6543e32e1620.png)

Lo desactivamos primero

![image](https://user-images.githubusercontent.com/31891276/124667092-8e4e4980-de74-11eb-9555-be07da851b94.png)

## 26. Otras Extensiones para Postgres.

https://www.postgresql.org/docs/11/contrib.html

## 27. Backups y Restauración.

![image](https://user-images.githubusercontent.com/31891276/124670606-d4f27280-de79-11eb-8e7f-bdeb56560d4d.png)

## 28. 

Vacuum: La más importante, con tres opciones, Vacuum, Freeze y Analyze.
Full: la tabla quedará limpia en su totalidad
Freeze: durante el proceso la tabla se congela y no permite modificaciones hasta que no termina la limpieza
Analyze: solo revisa la tabla 


Analyze: No hace cambios en la tabla. Solo hace una revisión y la muestra.


Reindex: Aplica para tablas con numerosos registros con indices, como por ejemplo las llaves primarias.


Cluster: Especificamos al motor de base de datos que reorganice la información en el disco.


![image](https://user-images.githubusercontent.com/31891276/124672365-85617600-de7c-11eb-889e-3a3fd408aa4e.png)


Se recomienda hacerlo por tabla, o que el sistema lo haga solo.

se debe hacer cuando existen problemas de indexacion.

## 29. Introducción a Réplicas.


Pensar siempre en modo replica, limites de fisica y de electronica, 

Una maestra y otra master o compia en caliente.

IO PS

Son mecánismos que permiten evitar problemas de entrada y salida en los SO.
“Existen 2 tipos de personas, los que ya usan réplicas y los que las van a usar…” - Piensa siempre en modo réplica.
A medida que la DB crece encontraremos limitaciones físicas y de electrónica, si la DB aumenta tanto su tamaño, las limitaciones serán de procesamiento, RAM, almacenamiento.
Hemos visto que las consultas en local son muy rápidas, sin embargo, cuando la aplicación ha sido desplegada pueden ocurrir multiples peticiones de lectura y escritura. Todos los motores de DB pueden hacer una ejecución a la vez, por lo que recibir tantas peticiones de consulta al mismo tiempo puede hacer que regresar una consulta se demore demasiado y eso puede ser catastrófico, pero las réplicas son la solución a este tipo de problemas.
¿Cuál es la estrategia? Tener una base de datos principal donde se realizan todas las modificaciones, y una base de datos secundaria dónde se realiza las lecturas. Separar las tareas es altamente beneficioso en cuanto al rendimiento de la aplicación, así, cuando se modifica una DB automáticamente se lleva el cambio a la DB de lectura. Todo lo que hay que hacer es configurar 2 servidores de postgres, uno como maestro y otro como esclavo. Se debe modificar la aplicación para que todas las modificaciones se hagan sobre el maestro y la lectura sobre la replica, o la DB en caliente. Es imposible realizar cambios en la DB de réplica.

## 30. Implementación de Réplicas en Postgres

https://jelastic.com/

https://platzi.com/tutoriales/1480-postgresql/6559-implementacion-de-replicas-en-postgres-con-docker-2/
