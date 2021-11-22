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
