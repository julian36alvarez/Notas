# Arquitectura en Android

## Patrón de diseño vs. Arquitectura de Diseño

Ya sabemos que una arquitectura nos va a ayudar a que nuestras aplicaciones estén mejor diseñadas y tengan mejor experiencia de usuario. La arquitectura en general no solo podemos usarla en una aplicación móvil sino que deberíamos aplicarla a cualquier proyecto de software.

Patrón de Diseño: Un patrón es un modelo que sirve de muestra para sacar otra cosa igual. Los patrones de diseño son una solución a problemas comunes de código reutilizable.

Organiza un componente o elemento de la aplicación
Algunos Patrones de diseño conocidos:

+ Singleton
+ Adapter
+ Builder
+ Factory

**Arquitectura de Diseño:**  

La arquitectura es el arte y técnica de diseñar, proyectar y construir. Una Arquitectura de Diseño proporciona la estructura, funcionamiento e interacción entre las partes del software.

**Algunas Arquitecturas conocidas**  

+ MVC: Model-View-Controller
+ MVP: Model-View-Presenter
+ MVVM: Model-View-ViewModel


## Modelo de capas (Layers Model).  

La arquitectura va a estar orquestando lo que sucede a nivel de aplicación. Ahora vamos a organizarlo en capas, módulos o partes del software:

## UI o Presentación: 

Encontraremos todo lo que tiene que ver con la interfaz de usuario: botones, imágenes, campos de texto y más.

Business Logic o Reglas de Negocio: Encontraremos toda la lógica de lo que tiene que hacer la aplicación, los casos de uso de la aplicación: login, logout, registrar usuarios y más.

Data: Veremos mucho sobre la persistencia y procesamiento de la información, la mayoría de las aplicaciones deben estar preparadas para soportarlo: leer una base de datos o traer datos de una API.

Arquitecto de Software: Va a analizar las necesidades, va a planear con anticipación, toman decisiones para evitar riesgos y tienen una amplia experiencia resolviendo problemas.

El futuro tú tendrá que reutilizar código creado por otro desarrollador, tocar código creado por ti de hace mucho tiempo, resolver bugs e implementar nuevos features.

En conclusión la Arquitectura de Diseño:

+ Organiza el código para trabajar en equipo.
+ Hace el código más intuitivo de leer y escribir.
+ Permite mantener, testear e integrar nuevos features más rápido y fácil.



## elementos de SOLID Principles

![image](https://user-images.githubusercontent.com/31891276/143285739-5faa00f2-6aae-4fdd-ac94-7feea2a63368.png)


+ L Liskov Substitution: Deberíamos poder usar una clase hija para sustituir a una clase padre sin obtener errores.
+ I Interface segregation: Si una interfaz crece demasiado pierde su objetivo y viola el primer principio.
+ D Dependency Inversion: Depende de una abstracción, no de algo concreto.

Evolución de arquitectura de Android.

MVC (Model-View-Controller): Es donde teníamos todas las responsabilidades y todas las acciones de la aplicación en una sola clase, la clase activity (main.Activity).

MVP (Model-View-Presenter): Separa las capas de modelo donde vamos a tener todas las conexiones. Después tenemos un presentador; es la capa donde mantiene la comunicación entre el modelo de datos y la user interface. Después esta arquitectura tuvo una evolución, donde se decidió que deberíamos seguir los principios de la arquitectura limpia, la cual nos dice que debemos exponer las entidades y que las entidades deben ser lo mas importante de la aplicación, mas allá de todas las capas que estén por debajo.

MVVM (Model-View-ViewModel): en la vista tenemos activities y/o fragments, despues en la capa de view model vamos a tener clases que funcionen en un hilo adicional de la aplicación para eso vamos a tener clases como : AsyncTask, Rxjava y LiveData. Y por ultimo esta la capa de model que aqui vamos a tener toda la interacción con una base de datos para conectarla y hacer que los datos lleguen a la user interface.
Android Jetpack: Arquitectura de componentes(network resources)


![image](https://user-images.githubusercontent.com/31891276/143492526-61bf3ff1-c333-45d0-a69b-dafca6813260.png)

MVC fue la primera arquitectura con la cual empezó todo. Es importante conocerla en caso de que te encuentres con ella y sepas cómo migrar hacía una mejor arquitectura.

El View se va a componer de nuestra interfaz: botones y campos de texto.

El Controller será toda la lógica de negocio. Puede tener la lógica de lo que realizará un botón.

Ambos elementos estarán definidos en un solo lugar.

El Model tendrá la conexión a una base de datos o una API.

## Clean Architecture

El término Clean se refiere a las buenas prácticas que se puede tener sobre cierto elemento en la programación.  

+ Clean Code
+ Clean Architecture
+ Clean Code va a referirse a la forma en cómo hacemos que el código sea lo más limpio posible, para ello hay muchas buenas prácticas que van desde el cómo se nombran las variables, la forma en cómo construimos funciones, cómo comentamos el código, la alineación, la abstracción de objetos y estructuras, etc. todo esto con el fin de hacer el código mucho más entendible en el presente y futuro, testeable y fácil de integrar.

+ Clean Architecture:  
En esta ocasión hablaremos sobre Clean en la Arquitectura de software especialmente en Android.

El principal objetivo de una Arquitectura limpia es la capacidad de separar el código en su diferentes responsabilidades.

¿Recuerdas las 3 capas básicas del modelo de capas que te presenté anteriormente?

+ Presentation Layer
+ Business Logic Layer
+ Data Layer
+ Estas son las tres responsabilidades base sobre las cuales trabaja la arquitectura limpia.

Clean Architecture es un término introducido por Rober C. Martin mejor conocido como Uncle Bob o el Tío Bob. Él recopiló los modelos de capas más utilizados en una versión mejorada a la que llamó Clean Architecture

A continuación te presento 5 principios sobre los cuales se basó:

1. Es independiente de cualquier framework. La arquitectura limpia debe ser capaz de aplicarse a cualquier sistema sin importar el lenguaje de programación o las librerías que utilice. Las capas deben quedar tan bien separadas que pueden sobrevivir individualmente sin necesidad de externos.

2. Testeable. Entre más pura sea una función, clase, módulo etc. más fácil será predecir el resultado a obtener. Cuando hablamos de que algo sea puro nos referímos a que no tenga efectos colaterales. Lee este artículo para que entiendas mucho más sobre los efectos colaterales y funciones puras. (Importante de leer para completar la lección). Cada módulo tanto de UI, base de datos, conexión a API Rest, etc. debe ser capaz de ser testeado individualmente.

3. Independiente de la Interfaz de Usuario. Uno de los componentes que sufren cambios más constantemente es la interfaz de usuario, la UI debe ser capaz de cambiar sin alterar todo el sistema y si vamos más allá, esta capa debería vivir tan independiente que podría ser desensamblada y ser sustitída por otra. Por ejemplo. Cambiar una UI Móvil por una en modo consola.

4. Independiente de la base de datos. Así como el punto anterior, esta capa debe ser tan modular que es posible agregarle múltiples fuentes de datos, e incluso múltiples fuentes del mismo tipo de datos. Por ejemplo, manejar varias bases de datos: MySQL, PostgreSQL, Redis, etc.

5. Independiente de cualquier elemento externo. Si en algún punto nuestro sistema necesita de una librería, otro sistema o cualquier otro elemento a conectar, debería ser fácilmente ensamblado y también debería ser modularizado. De hecho para el sistema esta capa externa debería ser transparente.

Estos principios fueron graficados por el Tío Bob en el siguiente diagrama:

![image](https://user-images.githubusercontent.com/31891276/143685762-a1b0c86a-57a6-467a-b829-e883b85c5c01.png)

![image](https://user-images.githubusercontent.com/31891276/143685772-5ae3bc69-0a5c-470d-8c27-165cc22bf7fa.png)

![image](https://user-images.githubusercontent.com/31891276/143685781-203ca7fd-e722-499c-95a6-712fbf19460a.png)

### Ahora expliquemos cada elemento.

En realidad nosotros en este punto ya tenemos experiencia con la separación de capas, de hecho ya aplicamos dos arquitecturas MVC y MVP para hacerlas Clean subdividiremos un poco más pero eso lo veremos más adelante, ahora solo quiero explicarte cada elemento a forma de recordatorio:

1. Entities. Las entidades son los modelos definidos que interactuarán en el sistema. Estas deben ser lo sufucientemente abstractas para ser usados por múltiples aplicaciones en el negocio.

2. Use Cases (Casos de uso). Aquí se contienen las reglas que le dan sentido a la aplicación, Los casos de uso dirigen el flujo a las entidades y las orquestan para cumplir con el negocio.

3. Repositories y Presenters. Interface Adapters. Esta es la capa intercesora que convierte los datos extraídos por la interfaz de usuario y la capa de datos en el formato más conveniente para los casos de uso.

4. UI y Data Source. Frameworks y Drivers. En esta capa van todos los detalles tanto para mostrar datos en la UI como para obtener los datos requeridos.

Como ves hasta el momento nuestro proyecto ha tratado de seguir las reglas Clean Architecture, estas tendrán sus propias variaciones dependiendo de la Arquitectura aplicada, pero en general esto es lo que marca una Arquitectura limpia en el software.

##  arquitectura MVVM.

En general la arquitectura MVVM es diferente a MVP porque en esta arquitectura vamos a necesitar que los datos se estén manejando de una forma más automatizada y mucho más real time. Podemos usar varias versiones MVVM, una de ellas es data binding que es de las más antiguas y existen en muchos otros frameworks como .NET de Microsoft. También tenemos a Live data y RxJava o RxAndroid que son características de la programación reactiva que podemos utilizar para hacer la actualización de datos en tiempo real.


### Data Binding:
Android Data Binding es una biblioteca de soporte que nos permite vincular los componentes de la interfaz de usuario a las fuentes de datos de forma declarativa en lugar de mediante programación, es potencialmente realmente potente y complejo, pero si se usa de manera efectiva, puede reducir la capacidad de presentación.
