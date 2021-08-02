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


