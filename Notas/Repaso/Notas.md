
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

- Number of thread (users):  
  Indica el número de usuarios concurrentes con los cuales se realizará la prueba  
- Ramp-Up (in seconds): 
    Sirve para realizar pruebas con concurrencia escalonada, es decir luego de cuántos segundos los n usuarios estarán realizando peticiones al mismo tiempo.
- Duration (seconds): Tiempo en segundos que durará la prueba  
    Siendo así la prueba de carga se realizará con 5 usuarios concurrentes durante 60 segundos, los 5 usuarios realizarán peticiones concurrentes a partir del segundo 30, antes de los 30 segundos se realizarán de forma escalonada es decir primero 1 usuario, luego 2 etc.


## Patrón triple A

Es un patrón que sugiere cómo se debería estructurar el código de una prueba unitaria, su nombre se deriva de un acrónimo para preparación, acción y verificación (Arrange, Act, Assert) por sus siglas en inglés.

## Pruebas Unitarias.

Las pruebas unitarias se encargan de validar unidades pequeñas de código(por ejemplo, un método de una clase) , el alcance es muy reducido y está perfectamente acotado. 

## Pruebas de integracion.

Las pruebas de integración son posteriores a la Pruebas Unitarias y están enfocadas en probar cómo es la interacción entre los diferentes módulos del software, como interacciones entre componentes o bases de datos.

# ANGULAR

## Estructura del proyecto

Los archivos de la aplicacion se encuentran en la subcarpeta src. Las pruebas iniciales correspondientes de extremo a extremo se encuentran en la subcarpeta e2e.

El proyecto base esta estructurado en los modulos feature, shared y core. Asegurando una separacion adecuada de las preocupaciones, lo que facilitara la escalabilidad a medida que su aplicacion crezca. Lo siguiente describe brevemente cada tipo de modulo.

### AppModule: 
es el módulo principal de la aplicación, responsable de su arranque y de la combinación de otros módulos.

### Modulo core
Deben estar lo transversal y de una sola instancia en la aplicacion. Por ejemplo: NavBar o interceptor. es decir que se utilizarán en toda la aplicación a nivel global

### Modulo feature
Deben estar los componentes que implementan funcionalidades especificas de la aplicacion. Por ejemplo, el componente datos de contacto el cual es el componente que implementa la feature de contacto. Es posible tener compartidos dentro de esta feature.

+ Crearemos múltiples módulos de funcionalidades para cada característica independiente de nuestra aplicación.

### Modulo shared
Deben estar componentes o utilidades comunes a las diferentes feature. Por ejemplo, un componente de un boton azul que usted desea repetir en varios lugares. Un filtro para ser utilizado en todos los componentes.


+ Servicio: proporciona servicios de utilidad tales como acceso a datos y mensajería.
+ Carga diferida:  
Para evitar posibles problemas de rendimiento en la carga de la aplicación, se hará uso del patrón carga diferida (Lazy-Loading (opens new window)), capacidad incorporada en Angular y que permite aplazar la carga de una parte particular de la aplicación hasta que sea realmente necesaria.

![image](https://user-images.githubusercontent.com/31891276/169514533-5c14fdbd-c499-48a7-aba4-27c195645ed4.png)


CORS: Control de accesos http: los navegadores usan un mecanismo de seguridad en las cabeceras, el endopoint establece las politicas.


## Esctructura de las pruebas Angular.


Usamos **describe** para poner una descripción al grupo de tests que vamos a realizar, sobre todo para organizar los tests y que sea posible hacer seguimiento. 

Con el **it** vamos a establecer un test en particular. En este caso, el test que se realiza es que el componente se debe crear. Simplemente es un test que se genera de forma automática cuando generamos el componente.

Por último, usamos **expect** para definir cómo debe funcionar este test en concreto, en este caso, que es uno de los más simples, tan solo se comprueba que el componente se ha generado.


Además, fijaos que disponemos de varios Callbacks que nos permiten realizar operaciones antes y después de ejecutar los tests, sobre todo para realizar la creación y la eliminación de los registros que vamos a usar durante los tests. Estos Callbacks son los siguientes:  


+ beforeAll() => Se ejecuta antes de realizar todos los tests.
+ afterAll() => Se ejecuta después de finalizar los tests de la suite.
+ beforeEach() => Se ejecuta antes de cada uno de los tests individuales.
+ afterEach() => Se ejecuta al finalizar

## SpyOn


Espia para los objtos, en este caso al servicio

    spyOn(obj, 'method') // obj.method es el metodo que se va a espiar.  

Cambiar el valor retornado por un método.

    spyOn(obj, 'method').andReturn('value');
    
verificar el número exacto de ejecuciones de un método.

    expect(obj.method.callCount).toBe(2);


## HTTPClienteTestingModule.

HTTPTestingControler: Controlador que nos permite manipular el http client, quiere decir que nustras pruebas usan la instancia HTTPTestingControler y no la real que es HttpClient real.

# Protractor
dos archivos para definir las pruebas.

+ po.ts Generador de herramientas.  
      Importa browser , genera una url  
+ e2e-spect Ejecutor de las pruebas.

Protractor browsin -> permite navegar.


ASync ->

await ->
