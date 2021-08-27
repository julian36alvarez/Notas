# Spring Boot

![image](https://user-images.githubusercontent.com/31891276/128927067-344f7e5c-bc3c-4fb5-bcf5-d28930afeac0.png)  

- Proyecto basado en Spring. No es lo mismo que Spring. Es un proyecto que forma parte del core de Spring, al igual que Spring Cloud, etc.  
- El objetivo principal es que sólo te centres en correr la aplicación, sin preocuparte por temas de configuración, etc.  
- Tiene la gran ventaja poder integrar librerías de terceros de manera muy sencilla.  
- No tendremos que preocuparnos por configuraciones a nivel de XML, sólo configuraciones mínimas a nivel de properties (ponerle el puerto, etc).  
- No tendremos que preocuparnos de desplegar nuestra aplicación en un servidor web local cuando queramos hacer pruebas, Spring Boot también contempla esto y lleva incorporado un servidor web dónde se desplegará nuestra aplicación automáticamente.  


## 2. Características principales de Spring Boot

**Independiente:** no tenemos que preocuparnos de las dependencias del core de Spring ni de la compilación de estas.  
**Incrustado Tomcat, Jetty o Undertow:** Spring Boot trae consigo un servidor web como los tres mencionados donde podemos correr nuestra aplicación sin preocuparnos de generar un artefacto WAR o JAR y desplegarlo nosotros mismos.  
**Proporción de dependencias:** no debemos preocuparnos por las configuraciones de dependencias de terceros o del core de Spring, Spring Boot se encargará de inyectar todo lo necesario.  
**Sin generación de XML:** No debemos preocuparnos de configuración XML para que nuestra aplicación funcione.
Métricas de salud del aplicativo: podemos validar el estado de un servicio desplegado, sus dependencias, estado de memoria, magnitud de configuración, etc.  

## Que es una dependencia

Pequeña característica de un objeto especifico, que puede impactar de manera particular en el funcionamiento de una unidad.
Por ejemplo, las dependencias de un Smartphone serian:

- Cámara  
- Micrófono  
- Pantalla  
- Batería  

**Alta cohesión:** Involucra que la entidad ejecute sus acciones sin involucrar otra clase o entidad.

**Bajo acoplamiento** Hablamos de acoplamiento bajo cuando existe una independencia entre los componentes entre si, por el contrario un alto acoplamiento es cuando tenemos varias dependencias relacionadas a un solo componente.  

Entonces podemos afirmar que en la definición de un buen diseño de software se debe tener una ALTA COHESIÓN y un BAJO ACOPLAMIENTO.  

## Inversion de Control

![image](https://user-images.githubusercontent.com/31891276/128946951-f018b343-97b8-440c-b98f-58a03225df79.png)

![image](https://user-images.githubusercontent.com/31891276/128946968-2f694fc5-6e4e-430f-9b5c-8c101cd460e5.png)

![image](https://user-images.githubusercontent.com/31891276/128947015-8e8541a4-0696-4bc1-9876-e76234537fd2.png)

### ¿Qué es inyección de dependencias?  

Patrón que utiliza inversión de control para utilizar las dependencias inicializadas con el contenedor Spring.

**Qué es un bean?** Un bean básicamente son módulos desarrollados en Spring estos se encargan de brindarnos toda la lógica que necesitamos para nuestra aplicación. Ejemplo: Si necesitamos referenciar que nuestra clase es un modelo hacemos uso de el bean @entity .   
Esto nos permite usar propiedades creadas para este tipo de modulo que nos agilizan nuestro desarrollo. Al hacer inversión de control nosotros al llamar esos beans lo que hacemos es referenciar módulos funcionales creados por spring. Spring boot nos facilita el fácil instanciamiento de estos a nuestra aplicación, haciendo todo por nosotros

![image](https://user-images.githubusercontent.com/31891276/128947106-543c8f26-b5b4-4c92-b76c-3e93bb8557ca.png)


## Autoconfiguration y runtime

Configura automáticamente tus aplicaciones basadas en dependencias JAR que agregaste mediante el pom.xml, pero si nosotros realizamos una configuración manual esta es priorizada por Spring Boot.

## Anotaciones para indicar dependencias en Spring Boot

![image](https://user-images.githubusercontent.com/31891276/128947877-8090336a-ac3b-4646-810e-c96bf066bdf1.png)


Una Anotación es una forma de añadir metadatos al código fuente Java que están disponibles para la aplicación en tiempo de ejecución o de compilación. Es una alternativa mas sencilla al uso de XML.


### @Controller:  
Para indicar que esta será la clase que gestionara las peticiones del usuario por get, post, put, patch o delete.  

### @Service: 
Con esta notación especificamos que en esta clase se encontrara toda nuestra lógica de negocio, cálculos o llamadas a otras API externas.  

### @Repository: 
Se usa para las clases o interfaces que funcionaran con el acceso a la base de datos.  

Si nuestra clase o interfaz no tiene una especificación clara como **@Service, @Repository o @Controller**, simplemente recurrimos a @Component y le indicamos que sencillamente es un componente.  

Por otro lado, no es estrictamente necesario que cumplas con colocar una notación especifica, pero es una buena practica.  

![image](https://user-images.githubusercontent.com/31891276/128948237-0fce29e8-751b-46e3-b077-657f9c0c0fc1.png)

![image](https://user-images.githubusercontent.com/31891276/128948250-eb34788b-3ced-4be9-8e5c-634fbe0ee53d.png)

## JAVA JPA

![image](https://user-images.githubusercontent.com/31891276/129125931-97926b42-cb4b-4576-be55-8e3ed3ddcfb4.png)

Hibernet es una implementacion de JPA

![image](https://user-images.githubusercontent.com/31891276/131187172-55b12a0a-5443-4eae-aa71-f2cbbd171dc7.png)

![image](https://user-images.githubusercontent.com/31891276/131197446-2c250a46-7049-4eaf-a895-61908e38775c.png)


![image](https://user-images.githubusercontent.com/31891276/131197455-a94e9981-0e19-4982-baf2-078c85543864.png)
