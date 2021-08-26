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

+ anyMatch()  
+ allMatch()  
+ noneMatch()  
+ findAny()  
+ findFirst()  
+ min()  
+ max()  
+ reduce()  
+ count()  
+ toArray()  
+ collect()  
+ forEach()  

### Operaciones terminales de coincidencia

Las operaciones anyMatch, allMatch y noneMatch sirven para determinar si en un Stream hay elementos que cumplan con un cierto Predicate. Esto puede ser una forma simple de validar los datos de un Stream. Son terminales pues las tres retornan un boolean:  

        //Nos indica si un stream contiene un elemento según el Predicate que le pasemos:
        Stream numbersStream = Stream.of(1, 2, 3, 4, 5, 6, 7, 11);
        boolean biggerThanTen = numbersStream.anyMatch(i -> i > 10); //true porque tenemos el 11

        //allMatch
        //Nos indica si todos los elementos de un Stream cumplen con un cierto Predicate:
        Stream agesStream = Stream.of(19, 21, 35, 45, 12);
        boolean allLegalDrinkingAge = agesStream.allMatch(age -> age > 18); //false, tenemos un menor

        //noneMatch
        //Nos indica si todos los elementos de un Stream NO CUMPLEN un cierto Predicate:
        Stream oddNumbers = Stream.of(1, 3, 5, 7, 9, 11);
        boolean allAreOdd = oddNumbers.noneMatch(i -> i % 2 == 0);
        
### Operaciones terminales de búsqueda.

findAny, findFirst
Estas operaciones retornan un Optional como resultado de buscar un elemento dentro del Stream.  

La diferencia entre ambas es que findFirst retornara un Optional conteniendo el primer elemento en el Stream si el Stream tiene definida previamente una operación de ordenamiento o para encontrar elementos. De lo contrario, funcionará igual que findAny, tratando de devolver cualquier elemento presente en el Stream de forma no determinista (random)  

Si el elemento encontrado es null, tendrás que lidiar con una molesta NullPointerException. Si el Stream esta vacío, el retorno es equivalente a Optional.empty().  

La principal razón para usar estas operaciones es poder usar los elementos de un Stream después haber filtrado y convertido tipos de datos. Con Optional nos aseguramos que, aún si no hubiera resultados, podremos seguir trabajando sin excepciones o escribiendo condicionales para validar los datos. 

## Operaciones terminales de reducción

min, max
Son dos operaciones cuya finalidad es obtener el elemento más pequeño (min) o el elemento más grande (max) de un Stream usando un Comparator. Puede haber casos de Stream vacíos, es por ello que las dos operaciones retornan un Optional para en esos casos poder usar Optional.empty.

La interfaz Comparator es una @FunctionalInterface, por lo que es sencillo usar min y max con lambdas.

        Stream bigNumbers = Stream.of(100L, 200L, 1000L, 5L);
        Optional minimumOptional = bigNumbers.min((numberX, numberY) -> (int) Math.min(numberX, numberY));
        
reduce
Esta operación existe en tres formas:

    reduce(valorInicial, BinaryOperator)
    reduce(BinaryAccumulator)
    reduce(valorInicial, BinaryFunction, BinaryOperator)
    
reduce(BinaryAccumulator)
Retorna un Optional del mismo tipo que el Stream, con un solo valor resultante de aplicar el BinaryAccumulator sobre cada elemento o Optional.empty() si el stream estaba vacío. Puede generar un NullPointerException en casos donde el resultado de BinaryAccumulator sea null.  

        Stream aLongStoryStream = Stream.of("Cuando", "despertó,", "el", "dinosaurio", "todavía", "estaba", "allí.");
        Optional longStoryOptional = aLongStoryStream.reduce((previousStory, nextPart) -> previousStory + " " + nextPart);
        longStoryOptional.ifPresent(System.out::println); //"Cuando despertó, el dinosaurio todavía estaba allí."
        
reduce(valorInicial, BinaryOperator)  
Retorna un valor del mismo tipo que el Stream después de aplicar BinaryOperator sobre cada elemento del Stream. En caso de un Stream vacío, el valorInicial es retornado.  

    Stream firstTenNumbersStream = Stream.iterate(0, i -> i + 1).limit(10);
    int sumOfFirstTen = firstTenNumbersStream.reduce(0, Integer::sum); //45 -> 0 + 1 + … + 9
    
reduce(valorInicial, BinaryFunction, BinaryOperator)
Genera un valor de tipo V después de aplicar BinaryFunction sobre cada elemento de tipo T en el Stream y obtener un resultado V.  
 
Esta version de reduce usa el BinaryFunction como map + reduce. Es decir, por cada elemento en el Stream se genera un valor V basado en el valorInicial y el resultado anterior de la BinaryFunction. BinaryOperator se utiliza en streams paralelos (stream.parallel()) para determinar el valor que se debe mantener en cada iteración.  

    Stream aLongStoryStreamAgain = Stream.of("Cuando", "despertó,", "el", "dinosaurio", "todavía", "estaba", "allí.");
    int charCount = aLongStoryStreamAgain.reduce(0, (count, word) -> count + word.length(), Integer::sum);

### count
Una operación sencilla: sirve para obtener cuantos elementos hay en el Stream.  

    Stream yearsStream = Stream.of(1990, 1991, 1994, 2000, 2010, 2019, 2020);
    long yearsCount = yearsStream.count(); //7, solo nos dice cuantos datos tuvo el stream.
    
    
La principal razón de usar esta operación es que, al aplicar filter o flatMap, nuestro Stream puede crecer o disminuir de tamaño y, tal vez, de muchas operaciones solo nos interese saber cuántos elementos quedaron presentes en el Stream. Por ejemplo, cuantos archivos se borraron o cuantos se crearon por ejemplo.  

**toArray ** 
Agrega todos los elementos del Stream a un arreglo y nos retorna dicho arreglo. La operación genera un Object[], pero es sposible hacer castings al tipo de dato del Stream.  

**collect  **
Mencionamos la operación collect en la lectura sobre operaciones y collectors, donde mencionamos que:  

Collector es una interfaz que tomara datos de tipo T del Stream, un tipo de dato mutable A, donde se irán agregando los elementos (mutable implica que podemos cambiar su contenido, como un LinkedList) y generara un resultado de tipo R.  
Usando java.util.stream.Collectors podemos convertir sencillamente un Stream en un Set, Map, List, Collection, etc. La clase Collectors ya cuenta con métodos para generar un Collector que corresponda con el tipo de dato que tu Stream esta usando. Incluso vale la pena resaltar que Collectors puede generar un ConcurrentMap que puede ser de utilidad si requieres de multiples threads.  


    public List getJavaCourses(Stream coursesStream) {
        List javaCourses =
            coursesStream.filter(course -> course.contains("Java"))
                .collect(Collectors.toList());

        return javaCourses;
    }
    
### Operaciones terminales de iteración

Tan simple y tan lindo como un clásico for. forEach es una operación que recibe un Consumer y no tiene un valor de retorno (void). La principal utilidad de esta operación es dar un uso final a los elementos del Stream.

Stream> courses = getCourses(); 
courses.forEach(courseList -> System.out.println("Cursos disponibles: " + courseList));  

Las operaciones terminales se encargan de dar un fin y liberar el espacio usado por un Stream. Son también la manera de romper los encadenamientos de métodos entre streams y regresar a nuestro código a un punto de ejecución lineal. Como su nombre lo indica, por lo general, son la ultima operación presente cuando escribes chaining:


## Operaciones intermedias
hablamos de dos tipos de operaciones: intermedias y finales. No se explicaron a profundidad, pero en esta lectura iremos más a fondo en las operaciones intermedias y trataremos de entender qué sucede por dentro de cada una.  

Se le dice operación intermedia a toda operación dentro de un Stream que como resultado devuelva un nuevo Stream. Es decir, tras invocar una operación intermedia con un cierto tipo de dato, obtendremos como resultado un nuevo Stream conteniendo los datos ya modificados.  

El Stream que recibe la operación intermedia pasa a ser “consumido” posterior a la invocación de la operación, quedando inutilizable para posteriores operaciones. Si decidimos usar el Stream para algún otro tipo de operaciones tendremos un IllegalStateException.  

Viéndolo en código con un ejemplo debe ser mas claro:

        Stream initialCourses = Stream.of("Java", "Spring", "Node.js");

        Stream lettersOnCourses = initialCourses.map(course -> course.length());
        //De este punto en adelante, initialCourses ya no puede agregar mas operaciones.

        Stream evenLengthCourses = lettersOnCourses.filter(courseLength -> courseLength % 2 == 0);
        //lettersOnCourses se consume en este punto y ya no puede agregar mas operaciones. No es posible usar el Stream mas que como referencia.

La interfaz Stream cuenta con un grupo de operaciones intermedias. A lo largo de esta lectura explicaremos cada una de ellas y trataremos de aproximar su funcionalidad. Cada operación tiene implementaciones distintas según la implementación de Stream, en nuestro caso, haremos solo aproximaciones de la lógica que sigue la operación.  

Las operaciones que ya están definidas son:  

+ filter(…)  
+ map(…)  
+ flatMap(…)  
+ distinct(…)  
+ limit(…)  
+ peek(…)  
+ skip(…)  
+ sorted(…)  


Usos comunes de filter es limpiar un Stream de datos que no cumplan un cierto criterio. Como ejemplo podrías pensar en un Stream de transacciones bancarias, mantener el Stream solo aquellas que superen un cierto monto para mandarlas a auditoria, de un grupo de calificaciones de alumnos filtrar únicamente por aquellos que aprobaron con una calificación superior a 6, de un grupo de objetos JSON conservar aquellos que tengan una propiedad en especifico, etc.  

Tu código sera más legible y las razones de por qué estás aplicando cada filtro tendrán más sentido. Como algo adicional podrías mover esta lógica a funciones individuales en caso de que quieras hacer más legible el código, tener más facilidad de escribir pruebas o utilices en más de un lugar la misma lógica para algunas lambdas:  


        courses.filter(Predicates::isAJavaCourse)
            .filter(Predicates::hasEnoughDuration)
            .filter(Predicates::hasSinuheAsInstructor);

        // La lógica es la misma:
        public final class Predicates {
            public static final boolean isAJavaCourse(Course course){
                return course.getName().contains("Java");
            }
        }

map operará sobre cada elemento en el Stream inicial aplicando la Function que le pases como lambda para generar un nuevo elemento y hacerlo parte del Stream resultante:
Si quisiéramos replicar qué hace internamente map sería relativamente sencillo:  


        public  Stream filter(Function mapper) {
            List mappedData = new LinkedList<>();
            for(T t : this.data){
                R r = mapper.apply(t);
                mappedData.add(r);
            }

            return mappedData.stream();
        }
   
### flatMap.

En ocasiones no podremos evitar encontrarnos con streams del tipo Stream>, donde tenemos datos con muchos datos…  

Este tipo de streams es bastante común y puede pasarte por multiples motivos. Se puede tornar difícil operar el Stream inicial si queremos aplicar alguna operación a cada uno de los elementos en cada una de las listas.  

Si mantener la estructura de las listas (o colecciones) no es importante para el procesamiento de los datos que contengan, entonces podemos usar flatMap para simplificar la estructura del Stream, pasándolo de Stream> a Stream.  

        Stream> coursesLists; // Stream{List["Java", "Java 8 Functional", "Spring"], List["React", "Angular", "Vue.js"], List["Big Data", "Pandas"]}
        Stream allCourses; // Stream{ ["Java", "Java 8 Functional", "Spring", "React", "Angular", "Vue.js", "Big Data", "Pandas"]}
        
flatMap tiene la siguiente forma:      

    Stream flatMap(Functionsuper T, ? extends Stream> mapper)
    
Lo interesante es que el resultado de la función mapper debe ser un Stream. Stream usará el resultado de mapper para “acumular” elementos en un Stream desde otro Stream. Puede sonar confuso, por lo que ejemplificarlo nos ayudará a entenderlo mejor:  

        //Tenemos esta clase:
        public class PlatziStudent {
            private boolean emailSubscribed;
            private List emails;

            public boolean isEmailSubscribed() {
                return emailSubscribed;
            }

            public List getEmails(){
                return new LinkedList<>(emails); //Creamos una copia de la lista para mantener la clase inmutable por seguridad
            }
        }

        //Primero obtenemos objetos de tipo usuario registrados en Platzi:
        Stream platziStudents = getPlatziUsers().stream();

        // Despues, queremos enviarle un correo a todos los usuarios pero… solo nos interesa obtener su correo para notificarlos:
        Stream allEmailsToNotify = 
                                platziStudents.filter(PlatziStudent::isEmailSubscribed) //Primero evitamos enviar correos a quienes no estén subscritos
                                            .flatMap(student -> student.getEmails().stream()); // La lambda genera un nuevo Stream de la lista de emails de cada studiante.

        sendMonthlyEmails(allEmailsToNotify);
        //El Stream final solo es un Stream de emails, sin mas detalles ni información adicional.
        
        
flatMap es una manera en la que podemos depurar datos de información adicional que no sea necesaria.

### distinct

    Stream distinct()
    
Lo que hace es comparar cada elemento del Stream contra el resto usando el método equals. De esta manera, evita que el Stream contenga elementos duplicados. La operación, al ser intermedia, retorna un nuevo Stream donde los elementos son únicos. Recuerda que para garantizar esto es recomendable que sobrescribas el método equals en tus clases que representen datos.  

### limit
La operación limit recibe un long que determina cuántos elementos del Stream original seran preservados. Si el número es mayor a la cantidad inicial de elementos en el Stream, básicamente, todos los elementos seguirán en el Stream. Un detalle interesante es que algunas implementaciones de Stream pueden estar ordenadas (sorted()) o explícitamente no ordenadas (unordered()), lo que puede cambiar drásticamente el resultado de la operación y el performance.  

    Stream limit(long maxSize)
    
La operación asegura que los elementos en el Stream resultante serán los primeros en aparecer en el Stream. Es por ello que la operación es ligera cuando el Stream es secuencial o se usó la operación unordered() (no disponible en todos los Streams, ya que la operación pertenece a otra clase).  


## peek  
peek funciona como una lupa, como un momento de observación de lo que está pasando en el Stream. Lo que hace esta operación es tomar un Consumer, pasar los datos conforme van estando presentes en el Stream y generar un nuevo Stream idéntico para poder seguir operando. 

        Stream peek(Consumersuper T> consumer)

        Stream serverConnections =
            server.getConnectionsStream()
                .peek(connection -> logConnection(connection, new Date()))
                .filter(…)
                .map(…)
            //Otras operaciones…
            
### skip
Esta operación es contraria a limit(). Mientras limit() reduce los elementos presentes en el Stream a un numero especifico, skip descarta los primeros n elementos y genera un Stream con los elementos restantes en el Stream. 

### sorted
La operación sorted() requiere que los elementos presentes en el Stream implementen la interfaz Comparable para poder hacer un ordenamiento de manera natural dentro del Stream. El Stream resultante contiene todos los elementos pero ya ordenados, hacer un ordenamiento tiene muchas ventajas
