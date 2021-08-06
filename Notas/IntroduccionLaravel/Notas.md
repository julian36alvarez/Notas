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


