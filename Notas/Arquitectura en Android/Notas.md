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

El Model tendrá la conexión a una base de datos o una API
