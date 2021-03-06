# Programación Orientada a Objetos en PHP

## 1. Introducción

En resumen la programacion orientada aobjetos es una técnica o paradigma.  

![image](https://user-images.githubusercontent.com/31891276/127934972-062ced44-60d6-444d-9740-823e656bb545.png)

![image](https://user-images.githubusercontent.com/31891276/127935063-ba054bd4-f7e8-459d-8276-43724976aedc.png)

## 2. Deuda Técnica  

La deuda técnica es el coste y los intereses a pagar por hacer mal las cosas. El sobre esfuerzo a pagar para mantener un producto software mal hecho, y lo que conlleva, como el coste de la mala imagen frente a los clientes, etc  

**Cómo evitar la deuda técnica**  
- Tenemos que programar con pruebas.  
- Documentar a tiempo.  
- Refactorizar (mejorar) de inmediato nuestro código.  

## 3.  Code smell

Hace referencia al mal olor del código. Este concepto no se refiere a errores técnicos, sino a errores de orden y diseño. Esto sucede mucho cuando intentamos crear soluciones a partir de otras soluciones.
La solución a estos casos es crear una abstracción.

**Cómo evitarlo**  
Para esto debemos hacer una programación más limpia, y reusable. Tenemos que evitar crear grandes métodos, o sea, programación estructura dentro de clases. También evitar crear grandes clases o superclases.  
Y sin duda, nosotros debemos evitar a toda costa copiar y pegar código.  

## 4.  Código espagueti.

Un código espagueti es código que está estructurado mediante if, while, for netamente, todo en un mismo archivo donde solamente buscamos resolver el problema. Cuando creamos código estructurado corremos peligro de crear código espagueti. La OOP nos ayuda evitarlo.  

**Cómo evitar el código espagueti**  
- Resolver el problema  
- Crea de forma lógica y coherente diferentes métodos que reemplacen tus estructuras de control.  
- Crea una o varias clases dependiendo el caso.  

## 5. Inclusión de archivos. 

include : Como la palabra lo dice, incluye un archivo dentro de otro. Cuando el archivo no es encontrado o tiene algún error, el sistema lanzara un warning pero seguirá trabajando  

require (): Funciona igual que include la única diferencia es que este arrojara un fatal error a nivel de compilación y todo el sistema dejara de funcionar hasta que se solucione el problema.  
  
requiere_once (): Funciona igual que requiere excepto que PHP verificará si el archivo ya ha sido incluido y si es así, no se incluye (require) de nuevo.  

include_once : Tiene un comportamiento similar al de la sentencia include, siendo la única diferencia de que si el código del fichero ya ha sido incluido, no se volverá a incluir, e include_once devolverá TRUE. Como su nombre indica, el fichero será incluido solamente una vez.  

## 6. Introducción a clases y objetos.
  
## 7. Abstracción.
Pensar el resultado final antes de programar, nos ayuda a aislar separar o sacar.
  
## 8. Alcance o Encapsulamiento.
  
El alcance hace referencia al encapsulamiento o principio de ocultación. Esto nos ayuda cuando estamos trabajando con herencia.

    <?php

    class User {
        // public
        // protected
        // private

        public const PAGINATE = 25;

        public $username;
        // protected $username;
        // private  $username;

        public function getUsername() {
            # code...
        }

        // Poner en mayúsculas nos ayuda crear rutas absolutas y no relativas var_dump(__DIR__);
    }

Para esconder datos vamos a utilizar los modificadores de acceso:  

Public → Puede ser accedido por todos, o seá por cualquier elemento o clase.  
Protected → Podrá ser accedido a nivel de la clases, paquetes y Subclases (las clases hijas ← clases padres).  
Defaulf → Este nos permite el acceso a nivel de clases y paquetes. O sea, que a nivel de herencia no puede ser accedido.  
Private → Solo puede ser accedido a nivel de clases, esto quiere decir, que solo puedes ser modificado a nivel de la clase, o sea, por ella misma.  

## 9. Modularidad

Esta no es una técnica de programación, pero si es algo con lo que debemos cumplir para que a futuro se más fácil la mantenibilidad. Este concepto aplica views, models, controllers, helpers, etc.

## 10 Polimorfismo.

El polimorfismo solamente significa varias formas. Esto quiere decir que si un mismo elemento si se comporta de diferentes maneras y otorga diferentes resultados quiere decir que aplica el término de polimorfismo.

    <?php

    abstract class Base {
        protected $name;

        private function getClassName() {
            return get_called_class();
        }

        public function login() {
            return "<p>Mi nombre es $this->name desde la clase {$this->getClassName()} <br><p>";
        }
    }

    class Admin extends Base {
        public function __construct($name) {
            $this->name = $name;
        }
    }

    class User extends Base {
        public function __construct($name) {
            $this->name = $name;
        }
    }

    class Guest extends Base {
        protected $name = 'invitado';
    }

    $guest = new Guest();
    echo $guest->login();

    $admin = new Admin('Helena');
    echo $admin->login();

    $user = new User('John Moore');
    echo $user->login();
    
## 11. Polimorfismo: interfaz  

En programación avanzada siempre vamos a trabajar sobre interfaces. Vamos a trabajar con estas porque es lo que enviamos, o sea, que lo enviamos a nivel de configuración.

Nos vamos a encargar de preparar todo el código necesario, así no trabajamos sobre _usuarios _sino sobre la interfaz de usuarios.

## 12. Herencia.

- La herencia nos permitirá crear nuevas clases a partir de otras. O sea, vamos reutilizar código. Quiere decir, que vamos a hacer una abstracción para generar una súper clases general que después utilicemos para crear otras clases  

- En la herencia también tendremos una jerarquía de padre e hijo.
En OOP, la clase padre siempre la encontraremos como la ‘Súperclase’ y los hijos como ‘subclase’. 

Y a través de encapsulamiento vamos a poder definir que puede heredar el hijo y que no.
El método constructor nos permite inicializar las variables del objeto.  

Para evitar que se incumpla los principios SOLID 2 y 3, podemos utilizar la palabra reservada final al principio del método. También, podemos utilizar este la palabra reservado final en una clase, pero esto significa que no puede ser heredada.  

## 13. Interfaces.

Una interfaz se desarrolla y se implementa en una clase, al implementarla nosotros estamos obligados a desarrollar todos los métodos que la interfaz define.  

Esto quiere decir, que una interfaz no puede hacer nada por si sola, lo que significa que las clases hijas están encargadas de definir el comportamiento de todos los métodos abstractos de forma obligatoria.  

En palabras más sencillas, las interfaces serán contratos que indicarán que es lo que se debe de hacer sin proveer ninguna funcionalidad.  

## Resumen

La programación orientada a objetos es una forma de programar, un paradigma o una técnica.  Recordemos que para programar de esta forma en realidad debemos crear objetos, y un objeto es una instancia de una clase y una clase es el molde. Ejemplo:

- Programación orientada a objetos: es la técnica.
- PHP: es el lenguaje de programación (donde implementamos la técnica).

Podemos resumir los diferentes conceptos de la siguiente manera:

- **Herencia:** compartir métodos entre clases padres y clases hijas.  
Abstracción: significa aislar, separar y sacar.  
- **Polimorfismo:** capacidad o virtud que tienen los métodos donde, por ejemplo, un mismo método puede tener diferentes comportamientos y dar diferentes resultados.  
- **Modularidad:** este principio básicamente nos ayuda a tener cada vez piezas de código más pequeñas y entendibles, donde cada pieza es un módulo y muchos módulos forman el sistema entero.  
- **Encapsulamiento:** un objeto debe estar aislado y ser un módulo natural. Esto se cumple aplicando la protección a las propiedades impidiendo su modificación y básicamente se refiere a controlar el acceso.  


Al entender este estilo conseguimos organizar mucho mejor nuestro código agrupando tareas comunes para crear una sola solución y usarla las veces que sean necesarias en nuestro proyecto. Evitamos con esto repetir código y ganamos mucho al dar mantenimiento en el futuro.  

Comienza con la palabra reservada class.  
El código va entre llaves { }.  
La información se guarda en propiedades que pueden ser públicas, privadas o protegidas.  
Cada acción la colocamos en métodos que básicamente son funciones o bloques de código dentro de una clase.  
$this es una variable reservada por el lenguaje que podemos usar para acceder a elementos propios, siempre y cuando estemos en la instancia de la clase.  
new es la palabra clave usada para crear un objeto a partir de una clase.  
