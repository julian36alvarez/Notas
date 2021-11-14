# Java SE Avanazdo


# Clases Abstractas.

**Es una clase que no se puede instanciar y se usa unicamente para definir subclases.**

¿Cuando es una clase abstracta?  

Es cuando uno de sus métodos no tiene implementación.  

¿Cuando se utilizan clases abstractas?  
Cuando deseamos definir una abstracción que englobe objetos de distinto tipos y queramos hacer uso del polimorfismo.

![image](https://user-images.githubusercontent.com/31891276/140630910-646220bb-5d80-4a2d-9df5-04f75e74541a.png)


![image](https://user-images.githubusercontent.com/31891276/140630934-7308652f-b9e1-4475-ac9a-27ea29f01c3d.png)


![image](https://user-images.githubusercontent.com/31891276/140630936-9a97f848-f11e-4384-b0db-d59987ff3793.png)


## Clases Abstractas: 

Nos permite hacer nuestros programas muchos mas mantenibles y mas robustos de forma que podamos implementar nuevos módulos dentro del software en el futuro de una forma muy sencilla  
Polimorfismo  

* Herencia: Polimorfismo a nivel de herencia se daba en los++ MÉTODOS SOBREESCRITOS++ y ademas que significa MUCHAS FORMAS cuando sobrescribimos métodos en herencia decimos que ese objeto puede comportarse de una forma distinta.(las clases podrían no necesitar heredar la implementación de un método y a veces no necesitamos crear instancias de una clase padre).
* Interfaces: Polimorfismo implementado en interfaces, similar a herencia, pero la diferencia era que en interfaces si podemos implementar absolutamente todos los métodos, métodos sobrescritos y muchas formas.(a veces no necesitamos implementar todos los métodos).
Clase Abstracta: Es una fusión entre las cosas que le faltan a la interfaz por implementar y las cosas que le faltan a la herencia por cubrir.
Clase Abstracta:

No implementaremos todos los métodos
No crearemos instancias.



# Diferencias entre una clase Abstracta vs Interfaces  

## Clase Abstracta:  

+ Se podrán definir métodos con implementación y sin implementación (abstract).
+ No se pueden usar instancias (crear objetos).
+ Se utilizará para definir subclases. Siempre será heredada para poder utilizar y sobrescribir los métodos de su clase padre.
+ La herencia de los atributos y métodos se hará de forma líneal. De una clase padre a una clase hija.
+ Se pueden ir heredando métodos abstractos y no abstractos.
+ Redefinir nuevas clases sin crear nuevos objetos.
+ Se piensa en una clase abstracta cuando el enfoque es más en objetos (de las subclases).
+ Se pueden encontrar clases como Figure que se pueden crear clases como Circle, Square, Triangle.

## Interfaces:

+ Nuevos modificadores de acceso (default y private). Esto permite añadir comportamiento a los métodos.
+ Se podrán definir métodos con implementación y sin implementación.
+ Los métodos se pueden implementar en muchas familias de clases. Por lo cual no es líneal.
+ Se utiliza una interface cuando existen métodos que se pueden implementar en muchas familias (La relación va más allá entre dos clases).
+ Se piensa en una interface cuando el enfoque es más en las acciones que pueden tener en común muchos objetos.
+ Se encuentra acciones como Drawable Dibujable, Runnable Ejecutable, Callable Llamable, Visualizable Visualizable.
+ Una buena práctica es que el diseño de las aplicaciones siempre esté orientado a interfaces y no a la implementación. Crear buenas abstracciones. Encontrar el comportamiento común. Enfocarse en la declaración de los métodos.


![image](https://user-images.githubusercontent.com/31891276/141701592-a8bbd943-aaf0-4264-8b2a-660af77984e6.png)

