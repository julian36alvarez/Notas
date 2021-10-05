
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

