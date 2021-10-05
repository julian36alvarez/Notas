
![image](https://user-images.githubusercontent.com/31891276/135485377-01fc0112-b414-42a7-ad2f-4f7407a3dd92.png)   
# Java Spring 

![image](https://user-images.githubusercontent.com/31891276/135555630-730d4bfc-67a3-44d1-ab2c-ae3d49b07925.png)

**Spring Framework:** permite la creación de aplicaciones empresariales.  
**Spring Boot:** permite la creación de aplicaciones auto contenidas y autoconfigurables.  
**Spring Data:** permite gestionar e integrar bases de datos relacionales y no relacionales con la aplicación.  
**Spring Security:** permite gestionar la seguridad de la aplicación.  


![image](https://user-images.githubusercontent.com/31891276/135555942-2df031b7-bfe8-4139-97d7-4c43dc15d286.png)

Hasta hace algún tiempo las aplicaciones web empresariales lucias como el grafico de la izquierda, teníamos un servidor de aplicaciones que contenían su configuración donde van configuración de bases de datos, servicios externos, variables, etc. allí también ibas desplegadas todas las aplicaciones que quisiéramos que interactuaran o colaborativamente entre si, ahora las tendencias han cambiado las arquitecturas modernas nos sugieren tener algo como el diagrama de la derecha donde tengamos pequeñas aplicaciones o pequeños servicios que interactúen entre si, en vez de una gran aplicación. esto nos da mucha facilidad al momento de desarrollo y al momento de mantener nuestra aplicación. Cada aplicación internamente contiene su propio servidor de aplicaciones, con una configuración totalmente independiente una de la otra. como vimos en la clase anterior sprint Boot es el proyecto de sprint para crear aplicaciones autocontenidas estos nos permite olvídanos completamente de la arquitectura y enfocarnos únicamente en desarrollo, delegadle a sprint boot labores como configuración de dependencias o desplegar nuestros servicios o aplicación a un servidores de aplicaciones y enfocarnos únicamente en crear el mejor código posible. Para eso sprint boot utiliza internamente un servidor de aplicaciones embebido o un contenedor de aplicaciones embebido, por defecto sprint boot utiliza TOMCAT pero podemos hacerlo también con JETTY o con UNDERTOW.



## Spring Initializr

https://start.spring.io/

![image](https://user-images.githubusercontent.com/31891276/135556303-49281ee5-f8aa-457a-937b-0eddbb8bc43e.png)


Project:

Los projectos Maven gestionan las dependencias con archivos XML  

Los archivos Gradle son escritos en Groovy y permite crear tareas que se pueden ejecutar al momento de hacer despliegue o integración continua

Utilizar la version estable de spring boot y llenar los metadatos  

Spring Web: permite genera APIs rest utilizando Apache Tomcat como servidor por defecto  
build.gradle: Es donde etsta escrita toda la configuración del proyecto (plugins, version de Java, dependencias, software para pruebas etc.)  
Carpeta gradle: Archivos necesarios para que gradle funcione  
@SpringBootApplication: indica la clase que gestiona la aplicación  


## Configurar Spring Boot  

![image](https://user-images.githubusercontent.com/31891276/135946165-0543a167-19b1-4052-892e-42ec27db2b4a.png)  

https://docs.spring.io/spring-boot/docs/current/reference/html/application-properties.html

## Arquitectura por capas orientada al Dominio

![image](https://user-images.githubusercontent.com/31891276/135947824-bf3fd7a2-ae4b-4099-9727-3201f0abd875.png)

# JPA

Jpa es una especificación de Java, standar, para un framework ORM. Quiere decir que son uan serie de reglas que Java define para que cualquier framework que quierea interactura con la BD de Java, tenga que seguir.  
Los frameworks mas populares de Java para este fin son:  

+ Hibernate
+ TopLink
+ EclipseLink
+ ObjectDB

## Anotaciones JPA  

JPA utiliza anotaciones para conectar clases a tablas de la BD y asi evitar hacerlo de manera nativa con SQL.

**@Entity.** Indica a una clase de java que esta representando una tabla de nuestra BD.  

**@Table.** Recibe el nombre de la tabla a la cual esta mapeando la clase.  

**@column.** Se le pone a los atributos de la clase, no es obligatoria, se indica sólo cuando el nombre de la columna es diferente al nombre del atributo de la tabla.  

**@id amd @EmbededID.** Es el atributo como clave primaria de la tabla dentro de la clase. @id se utiliza cuando es clave primaria sencilla y @EmbededID cuando es una clave primaria compuesta.  

**@GeneratedValue.** Permite generar automáticamente generar valores para las clases primarias en nuestras clases  

**@OneToMany and @MatyToOne.** Representar relaciones  

![image](https://user-images.githubusercontent.com/31891276/135948282-aee8aab0-855f-42ac-b047-99b0d240b914.png)


![image](https://user-images.githubusercontent.com/31891276/135948298-dc750587-d363-4510-ad93-94e5fe69e91e.png)


![image](https://user-images.githubusercontent.com/31891276/135948381-76fc0cd1-adb7-43a6-ba34-2e1728067906.png)


Spring Data NO es una implementacion de JPA, sino mas bien es un proyecto que usa JPA para ofrecer funcionalidaes extra en la gestion de tareas desde JAVA a las base de datos.  

Spring Data internamente tiene varios subproyectos, entre ellos: Spring Data JPA y Spring Data JDBC, para conectarnos a BD relacionales (SQL). Spring Data MongoDB y Spring Data Cassandra, son proyectos para conectarnos a BD no relacionales.  

La tarea principal de Spring Data es optimizar tareas repitivas.  

Spring data nos provee de respositorios sin codigo, nos permiten hacer todo tipo de operaciones en BD (CRUD) sin utilizar una linea de código.  

También nos provee de auditorías transparentes, por ello, posee un motor de auditorias que nos permite saber cuadno se insertó un registro, cuando se borró, cuando se actualizo en la BD, etc.  




