#  ![image](https://user-images.githubusercontent.com/31891276/125542266-d13280dc-06fe-4f4a-84fe-1e458b3dbacb.png) Curso Básico de Testing en Java.

## 1.  Paso a paso para testing básico en Java.

¿Qué es un test?.  
¿Para qué sirve?.  
Tipos de test.  
Partes de un test.  
TDD : Test driven development.  

En el curso programaremos utilizando el editor IntelliJ IDEA, además, usaremos librerías como JUnit y Mockito.  

## 2.  Tipos y beneficios de los tests.  

  - Beneficios.  
  - Comprobar los requerimientos de nuestra aplicación.  
  - Documentación y ejemplos de nuestras clases.  
  - Mediante Test Driven Development (TDD) nos puede ayudar en el diseño de clases.  
  - Confianza al desarrollar.  
  - Confianza para refactorizar nuestro código.  
  - Es una habilidad que se solicita cada vez más en el mercado.  

Existen test automáticos y manuales, los automáticos van a requerir tiempo de desarrollo y algunas veces no serán tan viables, pero de ser posible siempre trata de hacer test automáticos ya que:  

  - Son más rápidos.  
  - Son más fiables.  
  - Son incrementales.  
  - Tipos de test  
  - Unitario: realizan pruebas a una función o clase muy concreta de nuestro proyecto.  
  - Integración: prueban cómo se conectan diferentes componentes de nuestro proyecto.  
  - Funcionales: prueban una funcionalidad de nuestro proyecto, pueden involucrarse varias clases.  
  - Inicio a fin: prueba todo un proceso del proyecto.  
  - Estrés: útil para probar si nuestra aplicación puede soportar grandes cantidades de procesos y peticiones a  

## 3.  Instalación de IntelliJ IDEA, creación del Proyecto con Maven y Tests Unitarios.  


![image](https://user-images.githubusercontent.com/31891276/125543662-2c624856-631b-40fd-b1ea-09ac1498d25a.png)


## 4. Testing en Java con JUnit para Verificar Contraseñas

package com.julian.javatest.util;

import org.junit.Test;

import java.awt.*;

import static com.julian.javatest.util.PasswordUtil.SecurityLevel.*;
import static org.junit.Assert.*;

    public class PasswordUtilTest {

        @Test
        public void weak_when_has_less_than_8_letters() {
            assertEquals(WEAK, PasswordUtil.assessPassword("123aa!"));
        }

        @Test
        public void weak_when_has_only_letters() {
            assertEquals(WEAK, PasswordUtil.assessPassword("abcdefghjk"));
        }

        @Test
        public void medium_when_has_letters_and_numbers() {
            assertEquals(MEDIUM, PasswordUtil.assessPassword("abcde12345"));
        }

        @Test
        public void strong_when_has_letters_numbers_and_symbols() {
            assertEquals(STRONG, PasswordUtil.assessPassword("abcd123!"));
        }
    }

## 5. Creación de test unitario: lanzar una excepción para alertar sobre un error.

![image](https://user-images.githubusercontent.com/31891276/125883433-330ffd20-26cf-4fef-9be3-303558b4931d.png)
Lanzar Exepcion. 

    package com.julian.javatest.util;

    public class StringUtilTest {
        public static void main(String[] args) {
            String result = StringUtil.repeat("Hola Olixito", 1);
            System.out.println("result = " + result);
            if(result.equals("Hola Olixito")){
                System.out.println("OK");
            }
        }

        private static void assertEquals(String actual, String expected) {

            if (!actual.equals(expected)) {
                throw new RuntimeException(actual + " is not equal to expected " + expected);
            }
        }
    }

## 6. Test unitario con JUnit

![image](https://user-images.githubusercontent.com/31891276/125884764-d27d8e10-750f-4fd1-83be-c56e67ad82a7.png)

![image](https://user-images.githubusercontent.com/31891276/125885024-85648ec6-dc9e-455b-81ee-3036a7ab9470.png)

## 7 Organización de tests con JUnit.

La forma correcta de separar nuestras pruebas es realizar cada una en su propia función, además, el nombre de la función debe describir que estamos probando.

Para indicarle a JUnit que esperamos una excepción lo debemos hacer de la siguiente forma:

    @Test(expected = IllegalArgumentException.class)


**Ejemplo **

        import org.junit.Test;

        import java.awt.*;

        import static com.julian.javatest.util.PasswordUtil.SecurityLevel.*;
        import static org.junit.Assert.*;

        public class PasswordUtilTest {

            @Test
            public void weak_when_has_less_than_8_letters() {
                assertEquals(WEAK, PasswordUtil.assessPassword("123aa!"));
            }

            @Test
            public void weak_when_has_only_letters() {
                assertEquals(WEAK, PasswordUtil.assessPassword("abcdefghjk"));
            }

            @Test
            public void medium_when_has_letters_and_numbers() {
                assertEquals(MEDIUM, PasswordUtil.assessPassword("abcde12345"));
            }

            @Test
            public void strong_when_has_letters_numbers_and_symbols() {
                assertEquals(STRONG, PasswordUtil.assessPassword("abcd123!"));
            }
        }

## 8. Test con Mockito para simular un dado.

[Mockito](https://site.mockito.org/) nos va a servir para simular clases mientras probamos, para añadirlo a nuestro proyecto debemos agregar la dependencia en maven.

      package com.julian.javatest.player;

      import org.junit.Test;
      import org.mockito.Mockito;

      import static org.junit.Assert.*;

      public class PlayerTest {
          @Test
          public void looses_when_dice_number_is_too_low() {
              Dice dice = Mockito.mock(Dice.class);
              Mockito.when(dice.roll()).thenReturn(2);
              Player player = new Player(dice, 3);
              assertEquals(false,player.play());
          }

          @Test
          public void win_when_dice_number_is_big() {
              Dice dice = Mockito.mock(Dice.class);
              Mockito.when(dice.roll()).thenReturn(4);
              Player player = new Player(dice, 3);
              assertEquals(true,player.play());
          }
      }

## 9. Simular el uso de una pasarela de pago.

    package com.julian.javatest.payments;

    import org.junit.Test;
    import org.mockito.Mockito;

    import static org.junit.Assert.*;

    public class PaymentProcessorTest {

        @Test
        public void payment_is_correct() {

            PaymentGateway paymentGateway = Mockito.mock(PaymentGateway.class);
            Mockito.when(paymentGateway.requestPayment(Mockito.any()))
                    .thenReturn(new PaymentResponse(PaymentResponse.PaymentStatus.OK));

            PaymentProcessor paymentProcessor = new PaymentProcessor(paymentGateway);

            assertTrue(paymentProcessor.makePayment(1000));
        }

        @Test
        public void payment_is_wrong() {

            PaymentGateway paymentGateway = Mockito.mock(PaymentGateway.class);
            Mockito.when(paymentGateway.requestPayment(Mockito.any()))
                    .thenReturn(new PaymentResponse(PaymentResponse.PaymentStatus.ERROR));

            PaymentProcessor paymentProcessor = new PaymentProcessor(paymentGateway);

            assertFalse(paymentProcessor.makePayment(1000));
        }
    }

## 10 Análisis de los tests y mejoras.

Nuestros test siguen un mismo proceso:

Se preparan los objetos que vamos a probar.  
  - Llamamos al método que estamos probando.  
  - Comprobamos los resultados.  
  - Podemos reducir la cantidad de código moviendo las partes comunes de preparación a una función que se ejecute antes de cada prueba.  
Con @Before le indicamos a JUnit la función que debe ejecutar antes de cada prueba.  

    package com.platzi.javatests.payments;

    import org.junit.Before;
    import org.junit.Test;
    import org.mockito.Mockito;

    import static org.junit.Assert.*;

    public class PaymentProcessorTest {

        private PaymentGateway paymentGateway;
        private PaymentProcessor paymentProcessor;

        @Before
        public void setup() {

            paymentGateway = Mockito.mock(PaymentGateway.class);
            paymentProcessor = new PaymentProcessor(paymentGateway);
        }

        @Test
        public void payment_is_correct() {

            Mockito.when(paymentGateway.requestPayment(Mockito.any()))
                    .thenReturn(new PaymentResponse(PaymentResponse.PaymentStatus.OK));

            assertTrue(paymentProcessor.makePayment(1000));
        }

        @Test
        public void payment_is_wrong() {

            Mockito.when(paymentGateway.requestPayment(Mockito.any()))
                    .thenReturn(new PaymentResponse(PaymentResponse.PaymentStatus.ERROR));

            assertFalse(paymentProcessor.makePayment(1000));
        }
    }
  
## 12. TDD: Definición, Beneficios, Ciclos y Reglas

El Test Driven Development (TDD) o desarrollo guiado por test, creado por Kent Beck, consiste en escribir primero los test antes que las clases permitiéndote ver si el diseño de una clase es la adecuada.  

### El ciclo del TDD  
**Red:** escribe un test que falle.  
**Green:** escribe el código necesario para que pase el test.  
**Refactor:** mejora el código.  
### Reglas  
Sólo escribirás código de test hasta que falle.  
Sólo escribirás código de producción para pasar el test.  
No escribirás más código de producción del necesario.  

**Red:** Escribirás el mínimo de código test que falle.  
**Green:** Escribirás el mínimo de código de producción que pase el test.  
**Refactor:** sólo cuando los tests estén pasando.  

    
## 13. Ejemplos de TDD: calcular el año bisiesto
## 22.

Normalmente, el desarrollo de los proyectos comienza a partir de requerimientos muy bien especificados. Sin embargo, habrá veces donde el programador debe definirlos o acabar de concretarlos. No importa cuál sea el caso, solo podemos empezar a escribir los tests una vez tenemos los requerimientos.  

Existen diferentes escenarios:  

Típicos  
Extremos  
Incorrectos  
No previstos  
