# Programación Funcional con JAVA

La programacion funcional es un paradigma o un estilo enfocado a tener casos especificos a solicionar, estamos preocupados por resolver el problema

Funciones  
Datos  

![image](https://user-images.githubusercontent.com/31891276/127792367-78819817-dd35-4c8a-bfae-36ae46d9e96a.png)

## 2. Que es una funcion

Es un tipo de dato, En la programación funcional una función es un tipo de dato que opera sobre un dato X y genera un dato Y.

Las funciones se definen, almacenan o declaran bajo demanda como cualquier otro tipo de dato.  

Pueden definirse funciones con respecto a otras funciones esPar(x) = !esNon(x).  

Pueden definirse funciones con respecto a sí mismas (Recursividad).  

Pueden existir funciones que toman a otras funciones como parámetros: f(x, g(x)) = x2 * (gx)  

![image](https://user-images.githubusercontent.com/31891276/127792573-4ce555ce-fc12-48bf-b124-876691233eb0.png)

![image](https://user-images.githubusercontent.com/31891276/127792609-30a23541-49c8-4cc8-b327-3b8db3cb64dc.png)

## 3. Funciones como ciudadanos de primera clase

![image](https://user-images.githubusercontent.com/31891276/127792731-28ee04d3-cc57-4310-944d-a28d991ef45e.png)

![image](https://user-images.githubusercontent.com/31891276/127792751-c8003937-2671-446c-bab3-2a2375a5f810.png)

## 4. Funciones puras.

![image](https://user-images.githubusercontent.com/31891276/127792822-5e9ad8fc-6b51-49e0-90aa-90a82a50c8cc.png)  
**Función pura:** determinista (resultado predecible). Fácil de probar. Su resultado será siempre el mismo al recibir siempre los mismos parámetros. No dependen del contexto, siempre generará el mismo resultado y no generará efectos secundarios, es decir no afectará datos de entrada ni otros datos relativos a otros flujos de datos. No dependen del estado del sistema.

**Función impura:** no determinista. Dependen del estado del sistema. Dependen de su contexto. Pueden generar efectos secundarios, es decir, pueden afectar a otros flujos de datos o verse afectadas por otros flujos de datos subyacentes. No son predecibles.

Una función pura puede invocar a una función pura, pero no a una impura. Si una función pura invoca a una impura se transformará entonces en una función impura ya que la naturaleza de la impura hará impredecible el resultado de la función pura, ya sea por resultado o por los efectos secundarios y contexto que impliquen la función pura.

![image](https://user-images.githubusercontent.com/31891276/127795286-1a1d773a-1fdd-40f0-a7ed-f85751e3f38e.png)

### Ejemplo de Funcion Pura

![image](https://user-images.githubusercontent.com/31891276/127795297-658390f3-a898-413f-9142-8639d126a2e7.png)

## 5. Entendiendo los efectos secundarios.  

![image](https://user-images.githubusercontent.com/31891276/127795413-462e860f-b9c8-474b-8097-b2169b774275.png)  

Un efecto secundario es todo cambio observable desde fuera del sistema es un efecto secundario. Los efectos secundarios son inevitables (porque terminan siendo necesarios), algunos ejemplos son:

CRUD sobre archivos.  
CRUD sobre una base de datos.  
Enviar/Recibir una llamada de red.  
Alterar un objeto/variable usada por otras funciones.  
Sin embargo, se deben reducir los efectos secundarios, porque ayuda a tener una mejor estructura del código (favoreciendo la generación de funciones puras, la modularidad y la testeabilidad).  

![image](https://user-images.githubusercontent.com/31891276/127795467-d61b8d02-a0fd-49fa-8fdf-c8e9bb68634a.png)  

![image](https://user-images.githubusercontent.com/31891276/127795511-29d1186f-4a7b-49ac-b4f9-284e0325cea8.png)  

## 6. Funciones de orden mayor

![image](https://user-images.githubusercontent.com/31891276/127795602-05080c6a-44ca-47e7-a87d-9929b9524f36.png)

funcion de orden mayor toma una funcion como otro parametro o retorna una funcion

![image](https://user-images.githubusercontent.com/31891276/127795729-eb6608bc-afee-4ff6-b5f8-2a1252788b04.png)

## 7. Funciones Lambda

![image](https://user-images.githubusercontent.com/31891276/127795761-047a4e9f-a988-4bef-b09d-7e7b654ad665.png)

Función = Tiene un nombre.  
Lambda = Función que no tiene un nombre.  

Por qué usar lambdas?  
Es un comportamiento único.  
Es una regla que solo se requiere en un lugar.  
Es una función muy simple (1 línea).  

![image](https://user-images.githubusercontent.com/31891276/127795815-f4b899f9-c559-417a-b252-7f3fa08b3ac6.png)

![image](https://user-images.githubusercontent.com/31891276/127795856-ddcd03d1-475b-452a-9017-4831ccdd517a.png)  

## 8. Inmutabilidad

![image](https://user-images.githubusercontent.com/31891276/127862348-fd166e5f-e035-4289-853f-1a87233a8a10.png)

![image](https://user-images.githubusercontent.com/31891276/127862580-745f71a2-7c41-4573-931f-947ff4040a82.png)

## 9 -10 REPO

    https://github.com/sierisimo/JavaSE-Functional-platzi

## 13 Revisando el paquete java.util.function: Consumer y Supplier

Consumer: Es una expresion lambda que acepta un solo valor y no devuelven valor alguno.  
Ejemplo: Una funcion que reciba una lista de archivos y borre cada uno de ellos, sin devolver nada.  

Supplier: Es una expresion que no tienen parámetros pero devuelven un resultado.  
Ejemplo: Se crea un supplier de tipo CLIArguments llamado generator que no recibe ni un parametro pero que crea un nuevo objeto CLIArguments y retorna generator, Se pueden crear archivos bajo demanda.  


## 14.

Estas funciones extienden de Function. Quiere decir que tienen el método apply.  
 
**UnaryOPerator** --> Solo se especifica un solo tipo de dato. Se entiende que tendrá como resultado el mismo tipo.  

**BinaryOperator** --> Solo se especifica un tipo de dato. Se entiende que tendrá 2 parámetros de entrada y el uno de retorno del mismo tipo de dato.  

**Bifunction** --> 2 parámetros de entrada, se tiene que especificar el tipo de dato. Puede tener diferentes tipos de entradas como también diferente tipo de salida  

## 15 SAM y FunctionalInterface

usar interfaz como funcion, solo se puede un metodo si le agregamosotro metodo da error.
![image](https://user-images.githubusercontent.com/31891276/130169576-a835c52d-ee5f-4cb0-b978-85c07c196630.png)

## 16. Operador de Referencia
::  

Con el operador de referencia vamos a poder llamar métodos de otras clases ya establecidos en la aplicación de una forma más sencilla siempre y cuando cumpla las condiciones donde lo vayamos a utilizar

        public class NombresUtils {
            public static void main(String[] args) {
                List<String> teachers = getList("Nico", "Juan", "Pepito");
                Consumer<String> printer = text -> System.out.println(text);

                teachers.forEach(printer);
                System.out.println("-------");
                teachers.forEach(e -> System.out.println(e));
                System.out.println("-------");
                teachers.forEach(System.out::println);
            }

            static <T> List<T> getList(T... elements){
                return Arrays.asList(elements);
            }
        }
        
 ## 17.  inferencia de tipos
 
 infiere el dato tipado  
 
 ## 18. funciones lambda 
 
 **Sintaxis de lambdas**  

Si la lambda NO recibe argumentos:  
( ) -> operación  

Si la lambda recibe 1 argumento:  
_argumento -> operación  
( argumento ) -> operación_  

Si la lambda recibe mas de 1 argumento:  
( argumento1, argumento2) -> operación  

Si la lambda recibe varias operaciones:  
( ) -> { operacion1; return operación2; }  
argumento -> { operacion1; return operacion2; }  
( argumento ) -> { operacion1; return operacion2; }  
( argumento1, argumento2) -> { operacion1; return operacion2 }  

Si la lambda tiene mas de una operación debemos retornar un valor mediante. return

Pero si NO devuelve nada, solo hay que indicar el tipo de entrada vacío.  

( ) -> { operación }  

Para evitar errores es mejor usar  
( ) -> { operación }  
para cualquier caso.  

## Entendiendo los Streams

![image](https://user-images.githubusercontent.com/31891276/130381065-ab3235dd-ff6c-4a0c-879f-51c8f108581a.png)

### ¿Que son los Streams?  

Los Stream se utilizan para procesar colecciones de objetos. Una secuencia es una secuencia de objetos que admite varios métodos que se pueden canalizar para producir el resultado deseado.  

Las características de la secuencia de Java son:  

Un flujo no es una estructura de datos, sino que toma información de las colecciones.  
  
Los flujos no cambian la estructura de datos original, solo proporcionan el resultado según los métodos canalizados.  

Cada operación intermedia se ejecuta de forma perezosa y devuelve un flujo como resultado, por lo que se pueden canalizar varias operaciones intermedias. Las operaciones de terminal marcan el final de la secuencia y devuelven el resultado.  

**Intermediate Operations:  **
map: el método de mapa se utiliza para devolver una secuencia que consta de los resultados de aplicar la función dada a los elementos de esta secuencia.

    List number = Arrays.asList(2,3,4,5); 
    List square = number.stream().map(x->x*x).collect(Collectors.toList());
    
filter: The filter method is used to select elements as per the Predicate passed as argument.

    List names = Arrays.asList("Reflection","Collection","Stream"); 
    List result = names.stream().filter(s->s.startsWith("S")).collect(Collectors.toList());
    
sorted: The sorted method is used to sort the stream. 

    List names = Arrays.asList("Reflection","Collection","Stream"); 
    List result = names.stream().sorted().collect(Collectors.toList());
    
Terminal Operations:

collect: The collect method is used to return the result of the intermediate operations performed on the stream.

    List number = Arrays.asList(2,3,4,5,3); 
    Set square = number.stream().map(x->x*x).collect(Collectors.toSet());
    
forEach: The forEach method is used to iterate through every element of the stream.

    List number = Arrays.asList(2,3,4,5); 
    number.stream().map(x->x*x).forEach(y->System.out.println(y));

reduce: The reduce method is used to reduce the elements of a stream to a single value. The reduce method takes a BinaryOperator as a parameter.

    List number = Arrays.asList(2,3,4,5); 
    int even = number.stream().filter(x->x%2==0).reduce(0,(ans,i)-> ans+i);
    
## Lambdas, operaciones y retornos

Usando Stream nos podemos simplificar algunas operaciones, como es el filtrado, el mapeo, conversiones y más. Sin embargo, no es del todo claro cuándo una operación nos devuelve otro Stream para trabajar y cuándo nos da un resultado final…  

¡O al menos no era claro hasta ahora!  

Cuando hablamos de pasar lambdas a una operación de Stream, en realidad, estamos delegando a Java la creación de un objecto basado en una interfaz.

Por ejemplo:  

    Stream<String> coursesStream = Utils.getListOf("Java", "Node.js", "Kotlin").stream();

    Stream<String> javaCoursesStream = coursesStream.filter(course -> course.contains("Java"));


    // En realidad, es lo mismo que:

    Stream<String> explicitOperationStream = coursesStream.filter(new Predicate<String>() {
        public boolean test(String st) {
            return st.contains("Java");
        }
    });

+ **Consumer ** recibe un dato de tipo T y no genera ningún resultado  
+ **Function** toma un dato de tipo T y genera un resultado de tipo R  
+ **Predicate** toma un dato de tipo T y evalúa si el dato cumple una condición  
+ **Supplier** no recibe ningún dato, pero genera un dato de tipo T cada vez que es invocado  
+ **UnaryOperator** recibe un dato de tipo T y genera un resultado de tipo T  


Streams de tipo específico y Paralelismo
    
They should be used when the output of the operation is not needed to be dependent on the order of elements present in source collection (i.e. on which the stream is created)

Parallel Streams can be used in case of aggregate functions

Parallel Streams quickly iterate over the large-sized collections

Parallel Streams can be used if developers have performance implications with the Sequential Streams

If the environment is not multi-threaded, then Parallel Stream creates thread and can affect the new requests coming in
    
## Operaciones Terminales
    
Las operaciones terminales son aquellas operaciones que como resultado no generan un nuevo Stream. Su resultado puede variar según la operación. La utilidad de estas es poder generar un valor final a todas nuestras operaciones o consumir los datos finales. La razón principal para querer esto es que los datos deberán salir en algún punto de nuestro control y es con las operaciones terminales que hacemos esto.  

Pensemos, por ejemplo, en un servidor web. Recibe una petición de datos, convierte la petición en un Stream, procesa los datos usando filter o map, convierte de JSON a datos locales que sean manipulables por código Java y hace consumo de una base de datos. Todo esto mediante streams de diferentes tipos. Pero eventualmente tiene que devolver una respuesta para quien le hizo la petición.   

¿Qué pasa si quien hizo la petición no esta usando Java? No podemos enviarle un objeto de tipo Stream a un código hecho en Python o en JavaScript… es ahi donde una operación final nos ayuda a convertir nuestro Stream de Java en algún tipo de dato que sea mas comprensible.  

Otro ejemplo claro es si estamos creando una librería o creando código que más gente en nuestro equipo usará. Al crear nuestros métodos y clases usamos streams por aquí y lambdas por allá, pero al exponer estos métodos para uso de otros desarrolladores no podemos obligarlos a usar Stream.  

Las razones son variadas. No queremos obligar y limitar a quienes usen nuestro código a trabajar con un solo tipo dato. No sabemos qué versión de Java está usando quien use nuestro código. No sabemos si Stream está disponible en su parte del código (por ejemplo, en Android no estaba disponible del todo), etc.  

Es por ello que quisiéramos proveer de algo mas simple: listas, primitivos o incluso dar algún mecanismo para poder usar código externo de nuestro lado.  

Las operaciones terminales más comunes que se encuentran en Stream son:  

-anyMatch()
-allMatch()
-noneMatch()
-findAny()
-findFirst()
-min()
-max()
-reduce()
-count()
-toArray()
-collect()
-forEach()
