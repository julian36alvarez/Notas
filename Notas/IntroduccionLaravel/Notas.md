# Laravel

## 1. Herramientas necesarias para trabajar con PHP y Laravel  

En este gran curso puedes utilizar la versión 6 de Laravel, la cual actualmente se encuentra en un estado de LTS (Long-term Support), esto quiere decir que a diferencia de las versiones 7 y 8 Laravel 6 tendrá soporte por un periodo más prolongado hasta el 3 de septiembre de 2022 y puedes tener la tranquilidad de podrás aprender de este gran framework sin dificultades.

### Software de Instalación

En resumen necesitamos convertir a nuestro equipo en un servidor web, para ellos básicamente instalamos:  

Servidor web: Apache o Nginx.  
Lenguaje: PHP.  
Base de datos: MySql o MariaDB.  
Hay varias opciones, yo te recomiendo instalar las mas sencillas porque nuestro enfoque es la programación no la administración de servidores y estos conceptos hay que entenderlos bien, sin darnos cuenta estamos haciendo de nuestro computador un servidor web y un servidor de base de datos.

XAMPP: https://www.apachefriends.org/es/download.html.  

MAMP: https://www.mamp.info/en/downloads/.  

En Mac Usando brew en Mac podrías instalar valet y por separado a PHP y MySql. El tutorial completo está en la doc de Laravel https://laravel.com/docs/6.x/valet básicamente sería:  

brew update.  
brew install php.  
brew install mysql.  
composer global require laravel/valet.  
Por último valet install.  
También existe la opción de usar Homestead, esto es más avanzado y requiere una configuración mayor, aquí la doc https://laravel.com/docs/6.x/homestead  

### Instalación de Laravel  

Podemos usar composer directamente o instalar un software llamado "instalador de Laravel".

## Validación de datos (rutas, vistas, formularios y controladores)

![image](https://user-images.githubusercontent.com/31891276/128508137-b4f742ba-e07f-48e7-9cc0-ad63cf7dd91e.png)


Con composer sería composer  

      create-project --prefer-dist laravel/laravel nombre-app
      
Para instalar una versión específica de Laravel, por ejemplo Laravel 6, debes especificarlo en el comando de instalación así:  

    composer create-project --prefer-dist laravel-laravel dir "6.*"
    
Usas Mac y solo debes actualizar  
Laravel siempre nos obligará a estar actualizado, te comparto este enlace: https://rimorsoft.com/actualizar-a-php-7-3-x-con-homebrew-en-mac, te ayudará mucho si usas Mac y un entorno de trabajo parecido al mio.  

## 3. Entendiendo el ciclo de vida de las solicitudes web.

![image](https://user-images.githubusercontent.com/31891276/128033700-a91e3586-519b-4e0a-b79c-41f1faf44e3b.png)

## Rutas

![image](https://user-images.githubusercontent.com/31891276/128442660-3b927eb3-293c-4ca2-9128-246d7aa1c1bf.png)

Route::resource: Te permite gestionar 7 rutas junto con un controlador  
php artisan make:controller [NombreControlador]: Genera un controlador  
php artisan make:controller [NombreControlador] --resource: Genera un controlador con las 7 funciones necesarias que necesita Route::resource  
php artisan make:controller [NombreControlador] --resource --model: Genera un controlador con las 7 funciones necesarias que necesita Route::resource así como el modelo necesario para ese controlador  

## Middleware

![image](https://user-images.githubusercontent.com/31891276/128446124-7b3729ad-de20-47ad-9be8-23c7bafc8ccd.png)


Un middleware. La función principal es proporcionar una fácil y conveniente capa para filtrar las solicitudes HTTP. Existen diferentes maneras de hacerlo y de hecho Laravel incluye un middleware que verifica si el usuario está autenticado.  

Puedes crear un middleware de registro y tener logs detallados de cada solicitud entrante, cualquier cosa que se te ocurra respecto a HTTP puedes llevarla a cabo usando esta tecnología.  
### Middleware Personalizado.

      php artisan make:middleware Subscribed

Este se crea en app/Http/Middleware/Subscribed.php. Con él puedes verificar si el usuario está suscrito a mi plan de pago de mi sistema web. O crear un middleware que revise si el usuario que se intenta registrar es mayor de edad.

      $ php artisan make:middleware VerifyAge
      
En ambos casos tendremos nuestros middleware estarán creados en app\Http\Middleware\. Dentro de cada archivo debemos colocar la lógica de acceso correcto. Por ejemplo:

      namespace App\Http\Middleware;

      use Closure;

      class Subscribed
      {
          //...
          public function handle($request, Closure $next)
          {
              if ( ! $request->user()->subscribed) {
                  return abort(403, 'Sin suscripción activa');
              }

              return $next($request);
          }
      }

403: La solicitud fue legal, fue correcta, pero el servidor no la responderá porque el cliente no tiene los privilegios o permisos.
 Y respecto a la edad podemos hacer lo siguiente:
 
 
       namespace App\Http\Middleware;

      use Closure;

      class VerifyAge
      {
          //...
          public function handle($request, Closure $next)
          {
              if ($request->get('age') < 18) {
                  return redirect('guidelines');
              }

              return $next($request);
          }
      }
      
Aquí dirigimos al usuario a una vista que tenga los textos apropiados para explicarle porqué no podemos seguir con el registro.
### Registro de las Clases Middleware

      namespace App\Http;

      use Illuminate\Foundation\Http\Kernel as HttpKernel;

      class Kernel extends HttpKernel
      {
          //...
          protected $middleware = [];

          //...
          protected $middlewareGroups = [];

          //...
          protected $routeMiddleware = [
              'auth' => \App\Http\Middleware\Authenticate::class,
              'subscribed' => \App\Http\Middleware\Subscribed::class,
              'verify-age' => \App\Http\Middleware\VerifyAge::class,
          ];

          //...
          protected $middlewarePriority = [];
      }

Y luego podemos usarla y aplicarla donde corresponde. Veamos en una ruta varios ejemplos:

      Route::get('/example', 'ExampleController@...')
          ->middleware('auth', 'subscribed', 'verify-age');

Acá y en el video de la clase vimos la forma correcta de proteger a nuestras rutas o métodos en controladores, lo importante es definir qué queremos proteger o interceder y crear la lógica en un archivo aparte. Una persona con poca experiencia usaría estos if pero en las vistas, en cada método de un controlador o en cada una de las rutas. Esto funcionaria pero no es la manera correcta de trabajar.          



## Blade: sistema de plantillas avanzado.

Blade es el sistema de plantillas de Laravel. Todo lo que tiene que ver con vistas estará en resources

**@yield(‘contenido’)** → Esto le indica a Laravel que aquí se va registrar el contenido, y le pondremos dentro un nombre identificador.  
**@extends(‘archivo’)** → Para indicar de quién vamos a utilizar el @yield  
**@section(‘contenido’)** → Con este le indicamos a Laravel el @yeild donde va llevar el contenido que escribamos dentro de este.  
**@include(‘contenido’)** → Incluye el código de otros archivos al archivo que lo está incluyendo.  


*Cuando utilizamos @yield y @section, estamos haciendo que Laravel extraiga lo que tenemos dentro del @section y inyecta en el archivo que le indicamos con @extends para al final poner el contenido donde se encuentra el @yield.*

En cambio con @include, Laravel trae el contenido que está en el archivo que incluimos y lo pone en el archivo actual.  

Laravel realmente muestra en el navegador el resultado que el creo con las plantillas blade que hemos creado, este resultado lo guarda en storage → views.  

## componente Laravel/UI

![image](https://user-images.githubusercontent.com/31891276/128647777-d54346db-81d2-4b07-b35f-7693784dee1a.png)



