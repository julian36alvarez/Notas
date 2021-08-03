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
