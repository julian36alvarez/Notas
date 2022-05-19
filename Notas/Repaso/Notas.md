
# ARQUITECTURA HEXAGONAL

## DOMINIO

El Dominio es el nucleo de todas las capas. Y el dominio es el que define los puertos, tambien implementa toda la logica de negocio
DaoCliente es un puerto, Repositorio Cliente es un puerto.

En las capas superiores se definen los adapatadores para desacoplar el dominio.

## INFRAESTRUCTURA. 

Esta es la capa que se encarga de realizar los adaptadores a los puertos, expone los web service y ejecuta las sentencias de manipulacion de datos.

## APLICACION.

Se encarga de enrutar los eventos, es la capa transaccional, enruta de la capa de infraestructura a la capa de dominio.

Fabricas manejadores de comandos bus etc...

## Bloque HealthCheck

Es un bloque que tiene como fin saber el estado de otros bloques o servicios agregados

## Patrón CQRS:

Patrón con el cual dividimos nuestro modelo de objetos en dos, un modelo para consulta y un modelo para comando (modificación de datos). Este patrón es recomendado cuando se va desarrollar lógica de negocio compleja porque nos ayuda a separar las responsabilidades y a mantener un modelo de negocio consistente.

# Pruebas

## Pruebas de Carga.

    Para evaludar el rendimiento de la aplicacion, y saber que tanta concurrencia soporta.

    + Number of thread (users):  

    Indica el número de usuarios concurrentes con los cuales se realizará la prueba

    + Ramp-Up (in seconds): 
    Sirve para realizar pruebas con concurrencia escalonada, es decir luego de cuántos segundos los n usuarios estarán realizando peticiones al mismo tiempo.

    + Duration (seconds): 

    Tiempo en segundos que durará la prueba

    Siendo así la prueba de carga se realizará con 5 usuarios concurrentes durante 60 segundos, los 5 usuarios realizarán peticiones concurrentes a partir del segundo 30, antes de los 30 segundos se realizarán de forma escalonada es decir primero 1 usuario, luego 2 etc.


## Patrón triple A.

Es un patrón que sugiere cómo se debería estructurar el código de una prueba unitaria, su nombre se deriva de un acrónimo para:
**preparación**, **acción** y **verificación** (Arrange, Act, Assert) por sus siglas en inglés.

## Pruebas Unitarias.

Las pruebas unitarias se encargan de validar unidades pequeñas de código(por ejemplo, un método de una clase) , el alcance es muy reducido y está perfectamente acotado. 

## Pruebas de integracion.

Las pruebas de integración son posteriores a la Pruebas Unitarias y están enfocadas en probar cómo es la interacción entre los diferentes módulos del software, como interacciones entre componentes o bases de datos.


