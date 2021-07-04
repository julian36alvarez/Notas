# Clases del Curso Básico de Diseño de Interfaces con Android Studio

![image](https://user-images.githubusercontent.com/31891276/124339808-8b064580-db76-11eb-8822-c3beedecf628.png)

## 1. UI en Android: ¿Por qué? ¿Cómo?

**XML: ** XML(eXtensible Markup Language):
es un lenguaje de etiquetas, es decir, cada paquete de información está delimitado por dos etiquetas/tags
como se hace también en el lenguaje HTML, pero XML separa el contenido de la presentación.

**NameSpace:** Forma de contextualizar lo elementos en XML
Un namespace es una forma de darle contexto a un tag. Nos ayuda a entender dónde un tag tiene valor.
Los namespace provienen xmlns (xml namespace) donde vamos a darle una url de dónde un xml tiene su procedencia. De esta manera xml va a poder entender cuando tiene o no tiene un contexto y cuando puede darle o asignarle un comportamiento

![image](https://user-images.githubusercontent.com/31891276/124339751-277c1800-db76-11eb-8544-7f2d9de8ce77.png)

## 2. Instalando Android Studio

https://developer.android.com/studio

## 3. Enlazando nuestro layout con el código.

**Estructura de res:**

drawable: Representa gráficos (Todo aquello que pueda ser dibujado en una pantalla).
layout: Representa todas las estructuras de pantallas que creemos.
mipmap: Aquí guardaremos iconos.
values: Aquí administraremos los recursos (Colores, cadenas, dimensiones o arreglos).

Recursos más complejos:

font: Aquí guardaremos las fuentes de la aplicación.
anim: Contendrá xml para animaciones.
xml: Contendrá preferencias de usuario y datos más complejos.
raw: Contendrá archivos como vídeos o audios.

![image](https://user-images.githubusercontent.com/31891276/124340966-b5f49780-db7e-11eb-9ccc-829fc784268a.png)

Crear el archivo Dimens.xml es una buena practica para setear dimensiones 

![image](https://user-images.githubusercontent.com/31891276/124341012-023fd780-db7f-11eb-84f6-cc6bbb7ec4f2.png)

## 4. La vista de diseño en Android Studio

Layout

![image](https://user-images.githubusercontent.com/31891276/124341331-27354a00-db81-11eb-95b8-ff426b735060.png)

Seleccionat Vista de diseño

![image](https://user-images.githubusercontent.com/31891276/124341350-492ecc80-db81-11eb-936f-d235bc9c6701.png)

![image](https://user-images.githubusercontent.com/31891276/124341522-85aef800-db82-11eb-835e-db14af4abbcb.png)

Anidacion 

![image](https://user-images.githubusercontent.com/31891276/124341508-729c2800-db82-11eb-9efd-6fd55445d9bc.png)


## 5. La vista de texto en Android Studio

![image](https://user-images.githubusercontent.com/31891276/124341564-d888af80-db82-11eb-8119-8360ffd1a614.png)

![image](https://user-images.githubusercontent.com/31891276/124341597-1685d380-db83-11eb-9452-32674a733e93.png)

para poder referenciar el Layaut creado vamos a nuestro MainActivity:

![image](https://user-images.githubusercontent.com/31891276/124341639-619fe680-db83-11eb-9ab5-6a9cbc516500.png)

De esta forma podemos llamar nuestro componentes al MainActivity.

## 6. ViewGroup y View: Diferencias básicas

![image](https://user-images.githubusercontent.com/31891276/124341716-01f60b00-db84-11eb-9262-cae64a718a40.png)

View: es un elemento que se va a mostrar por pantalla así como tal.

  1. TextView.
  2. ImageView.
  3. EditText.

ViewGroup: es un elemento que sirve para agrupar elementos. Nota: cuando tenemos un grupo de elementos dentro de un ViewGroup, los cambios que hagamos sobre este afectaran los elementos dentro de el.

    <LinearLayout android:gravity="start"
      <TextView />
      <ImageView />
      <EditText />
    </LinearLayout>

Los Views son inline elements

![image](https://user-images.githubusercontent.com/31891276/124341884-64034000-db85-11eb-9284-d72f0fdccf1d.png)

Los ViewsGroup son elementos agrupado dentro de una pantalla. tienen afectacion directa sobre todos sus elementos cuando hay afectaciones.

![image](https://user-images.githubusercontent.com/31891276/124341919-a462be00-db85-11eb-8366-1541c543fcde.png)

## 7. Atributos importantes: alto, ancho y id

Este atributo  ocupa el ancho segun el ancho del texto

    android:layout_height="match_parent"

Este atributo usa toda la pantalla 

![image](https://user-images.githubusercontent.com/31891276/124366166-4c729880-dc13-11eb-8bbe-90ad49d276eb.png)

![image](https://user-images.githubusercontent.com/31891276/124366140-0d444780-dc13-11eb-90c5-6750d67b21de.png)

Atributos importantes: alto, ancho y id

**Width y Height**: Nos permiten definir como un elemento se va a distribuir con respecto a su contenido.

**Wrap content:** Hacer que crezca tanto como el contenido lo requiera.

**Match parent:** Hará que el elemento ocupe toda la pantalla.

**Hint:** Sugerencia para ingresar texto

**Background:** Utilizar una imagen o color de fondo. Para acceder a los colores del archivo se inicia con

    @<archivo>/<color>.

## 8 Otros atributos y el namespace tools
  
**Android id**

Cualquier objeto View puede tener un ID entero asociado para identificarse de forma única dentro del árbol.
Cuando se compila la aplicación, se hace referencia a este ID como un número entero, pero el ID se asigna normalmente en el archivo XML de diseño como una string del atributo id.
Este es un atributo XML común para todos los objetos View (definido por la clase View) y lo utilizarás muy a menudo.
  
La sintaxis de un ID dentro de una etiqueta XML es la siguiente:  android:id="@+id/my_button"

**Atributos específicos y atributos compartidos**
  
Existen atributos compartidos y otros específicos para cada elemento.
Por ejemplo, el atributo android:background, que nos permite establecer un color, es un atributo que existe para todos los elementos de android; el atributo android:hint="Enter password" es un atributo especifico de la View EditText

**Namespace tools**
Si en algún momento no quieres utilizar un atributo especifico y quieres solamente utilizarlo en tiempo de diseño para poder ver como se vería, existe un namespace denominado tools.
Es un namespace que nos permite ver en tiempo de diseño como se verá nuestra aplicación sin generar una versione final de la aplicación con esos valores.

Por ejemplo, si se establece el valor del atributo android:text durante el tiempo de ejecución o si quieres ver el diseño con un valor diferente del valor predeterminado, puedes agregar tools:text para especificar texto solo para la vista previa de diseño
para colocar imagenes.

    @mipmap -@drawable

## 9. LinearLayout: Organizacion lineal

![image](https://user-images.githubusercontent.com/31891276/124366673-fe5f9400-dc16-11eb-8f9a-d06298d638aa.png)

![image](https://user-images.githubusercontent.com/31891276/124366690-1e8f5300-dc17-11eb-9b6e-56d904b9dc5a.png)

Pantallas 

![image](https://user-images.githubusercontent.com/31891276/124366698-323ab980-dc17-11eb-8b4f-5f16a6f066a1.png)

Ejemplo del Diseño

![image](https://user-images.githubusercontent.com/31891276/124370026-fe23c080-dc37-11eb-94bb-2a797c602642.png)

    <?xml version="1.0" encoding="utf-8"?>

    <LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
        xmlns:tools="http://schemas.android.com/tools"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:background="@color/music_color_primary"
        android:orientation="vertical">
        <Space
            android:layout_width="match_parent"
            android:layout_height="0dp"
            android:layout_weight="1" />
        <ImageView
            android:layout_width="140dp"
            android:layout_height="110dp"
            android:layout_gravity="center"
            android:layout_marginTop="50dp"
            android:src="@drawable/headphone" />

        <EditText
            android:layout_margin="12dp"
            android:drawablePadding="12dp"
            android:drawableStart="@drawable/vector_person"
            android:hint="@string/hint_user"
            android:layout_width="match_parent"
            android:layout_height="wrap_content" />
        <EditText
            android:drawableStart="@drawable/vector_lock"
            android:layout_margin="12dp"
            android:drawablePadding="12dp"
            android:hint="@string/password"
            android:layout_width="match_parent"
            android:layout_height="wrap_content" />
        <Space
            android:layout_width="match_parent"
            android:layout_height="0dp"
            android:layout_weight="1" />
        <Button
            android:layout_marginStart="12dp"
            android:layout_marginEnd="12dp"
            android:background="@color/music_color"
            android:text="@string/button_login"
            android:layout_width="match_parent"
            android:layout_height="wrap_content" />

    </LinearLayout>



