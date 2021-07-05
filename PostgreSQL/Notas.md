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
