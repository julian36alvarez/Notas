# Java SE Avanzado


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


Lo primero que debes saber es que tiene tres implementaciones:

+ HashTable
+ LinkedHashMap
+ HashMap
+ SortedMap ➡️ TreeMap

![image](https://user-images.githubusercontent.com/31891276/141701621-d8a970a1-3c74-4269-b919-9f5170d40ae2.png)  


La interfaz Map no hereda de la interfaz Collection porque representa una estructura de datos de Mapeo y no de colección simple de objetos. Esta estructura es más compleja, pues cada elemento deberá venir en pareja con otro dato que funcionará como la llave del elemento.  

### Map<K,V>  

+ Donde K es el key o clave
+ Donde V es el value o valor
 Podemos declarar un map de la siguiente forma:

    Map<Integer, String> map = new HashMap<Integer, String>();
    Map<Integer, String> treeMap = new TreeMap<Integer, String>();
    Map<Integer, String> linkedHashMap = new LinkedHashMap<Integer, String>();
    
Como observas solo se puede construir el objeto con tres elementos que implementan de ella: HashMap, TreeMap y LinkedHashMap dejando fuera HashTable y SortedMap. SortedMap estará fuera pues es una interfaz y HashTable ha quedado deprecada pues tiene métodos redundantes en otras clases. Mira la funcionalidad de cada uno.  

Como te conté hace un momento Map tiene implementaciones:  

HashMap: Los elementos no se ordenan. No aceptan claves duplicadas ni valores nulos.
LinkedHashMap Ordena los elementos conforme se van insertando; provocando que las búsquedas sean más lentas que las demás clases.
TreeMap El Mapa lo ordena de forma “natural”. Por ejemplo, si la clave son valores enteros (como luego veremos), los ordena de menos a mayor.
Para iterar alguno de estos será necesario utilizar la interface Iterator y para recorrerlo lo haremos un bucle while así como se muestra:

## Para HashMap

    // Imprimimos el Map con un Iterador
    Iterator it = map.keySet().iterator();
    while(it.hasNext()){
      Integer key = it.next();
      System.out.println("Clave: " + key + " -> Valor: " + map.get(key));
    }


## Para LinkedHashMap

    // Imprimimos el Map con un Iterador
    Iterator it = linkedHashMap.keySet().iterator();
    while(it.hasNext()){
      Integer key = it.next();
      System.out.println("Clave: " + key + " -> Valor: " + linkedHashMap.get(key));
    }
    
## Para TreeMap

    // Imprimimos el Map con un Iterador
    Iterator it = treeMap.keySet().iterator();
    while(it.hasNext()){
      Integer key = it.next();
      System.out.println("Clave: " + key + " -> Valor: " + treeMap.get(key));
    }
    


![image](https://user-images.githubusercontent.com/31891276/141701787-1efd837d-8f16-4ccf-95de-b3c09e4365c2.png)


![image](https://user-images.githubusercontent.com/31891276/141702174-4cac32e5-9dfe-49bd-bc9a-0172c17fc55c.png)


# JDBC 

Clases:  
+ DriverManager: Nos permite crear una instancia de la conexión
+ Connection: Genera la sesión, maneja todo el ciclo de vida de una sesión cuando nos conectamos a una base de datos.
+ Statement: Nos ayuda a traer datos de una tabla.
+ PreparedStatement: Hace lo mismo que Statement con la diferencia de que éste nos permite recibir parámetros para la clausula where.
+ ResultSet: Es una interfaz que nos ayudará a manejar los datos obtenidos convirtiendo los datos en objetos.


![image](https://user-images.githubusercontent.com/31891276/141702531-b8f5dd35-9a1f-4b10-a20e-08cec892e5d9.png)

![image](https://user-images.githubusercontent.com/31891276/141702538-c58fd7bc-8dcd-4166-bf23-4ec18e0ddb48.png)


**Interfaces funcionales**

Concepto nuevo en Java SE 8 y que es la base para que podamos escribir expresiones lambda. Una interface funcional se define como una interface que tiene uno y solo un método abstracto y que éste sea diferente a los métodos definidos en java.lang.Object (a saber: equals, hashcode, clone, etc.). La interface puede tener métodos por defecto y estáticos sin que esto afecte su condición de ser interface funcional.  

Existe una nueva anotación denominada @FunctionalInterface que permite al compilador realizar la validación de que la interface tenga solamente un método abstracto
  

## Programación funcional, paradigma de programación.

### Paradigma declarativa vs imperativa
+ Imperativa: Estructurados, Procedimental, OOP, Otros
+ Declarativa: Funcional, Lógica, Otros

### Programación Imperativa: Cómo?
+ Enfoque: delimitar todos los pasos para resolver el problema.
+ Programación funcional: Qué?
+ Enfoque: declarar qué está haciendo el programa

Núcleo de la Programación funcional: funciones
entrada dato -> función -> salida dato

Funciones de orden superior, característica de programación funcional
entrada como función -> función como operación -> salida como función

## Stream y Filter

![image](https://user-images.githubusercontent.com/31891276/141707098-fab69426-64e2-406e-87e2-7000516da369.png)

## Tipos Lamba

Existen 4 tipos de expresiones Lambda:

Funciones (Function): Recibe como argumento dos parámetros de los cuales el primero T corresponde al tipo (objeto) de entrada y el segundo R como el tipo de salida de aquella operación.

     Function<String, Integer> function = s -> s.length() + s.indexOf(" "); 
     // 10 + 4?Integer result = function.apply("Hola mundo"); 
     // Tiene 10 caracteres y el " " se ubica 										      
     // en la posición 4.
     
Consumidores (Consumer): Un consumidor es aquella expresión que recibe un parámetro de entrada T pero que no retorna o genera ningún valor de salida. Son funciones terminales.

     Consumer<String> consumer = s -> System.out.println(s.toLowerCase()); 
     consumer.accept("Hola Mundo");
     
Proveedores (Supplier): Un proveedor es una expresión que no recibe parámetros de entrada pero que retornan o generan un tipo de salida T.

    Supplier<String> supplier = () -> "Hola mundo"; 
    supplier.get();
    Salida: "Hola mundo"
    
Predicados (Predicate): Los predicados son expresiones que aceptan expresiones booleanas, es decir, condiciones lógicas.

    Predicate<String> predicate = (str) -> str.length() > 6; 
    predicate.test("Hola mundo");
    Salida: true
    
    
