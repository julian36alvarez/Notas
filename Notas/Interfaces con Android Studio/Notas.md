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

## 10. RelativeLayout: organizando con referencias.

![image](https://user-images.githubusercontent.com/31891276/124370064-87d38e00-dc38-11eb-9692-bfd1797326da.png)

![image](https://user-images.githubusercontent.com/31891276/124370215-84d99d00-dc3a-11eb-97c8-fe357c0a8a70.png)

para que el elemento esté alineado arriba utilizamos

    layout_alingParentTop="true"

si queremos que el elemento esté alineado abajo

    layout_alingParentBottom="true"
    
para que un elemento esté alineado hacia la izquierda

    layout_alingParentStart="true"

para que se pueda alinear a la derecha

layout_alingParentEnd="true"

si queremos que un elemento esté alineado con respecto a otro elemento primero indicamos su posición y le indicamos el elemento con el que queremos que esté alineado

    layout_alingParentEnd="true"
    layout_below="@id/imagen"
    este codigo sirve para alinear el objeto a la derecha con respecto al elemento imagen

si lo que buscamos es que un elemento nos ocupe todo el ancho de la pantalla, RelativeLayout está pensado para eso, porque nosotros le podemos indicar la alineación inicial y final que debería tener en la pantalla.

    layout_alingParentStart="true"
    layout_alingParentEnd="true"

Le estamos diciendo que el objeto esté alineado a la izquierda y derecha de la pantalla, de esta manera ocupará todo el ancho de todo el activity

![image](https://user-images.githubusercontent.com/31891276/124370257-f0bc0580-dc3a-11eb-8999-ae9ec3e51177.png)

![image](https://user-images.githubusercontent.com/31891276/124370270-1c3ef000-dc3b-11eb-9844-24524e59cec3.png)

## 11. RelativeLayout: Uso práctico.

![image](https://user-images.githubusercontent.com/31891276/124371177-d7b85200-dc44-11eb-8852-5ef395a3e53a.png)

Una ventaja de RelativeLayout es que en este se pueden crear interfaces usando menos ViewGroups, lo cuál hace el árbol jerárquico menos pesado.
es una buena práctica en layouts que se quiere abarcar todo el espacio de pantalla, indicar un width de 0dp y usar alignParentStart y alignParentEnd para que el elemento ocupe todo el espacio disponible sin importar el espacio de la pantalla.

    <?xml version="1.0" encoding="utf-8"?>
    <RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
        xmlns:tools="http://schemas.android.com/tools"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:background="@color/music_color_primary"
        android:orientation="vertical">

        <ImageView
            android:id="@+id/ivLoginLogo"
            android:layout_width="140dp"
            android:layout_height="110dp"
            android:layout_alignParentTop="true"
            android:layout_centerHorizontal="true"
            android:src="@drawable/headphone" />

        <EditText
            android:id="@+id/etLoginUserName"
            android:layout_margin="12dp"
            android:drawablePadding="12dp"
            android:layout_below="@id/ivLoginLogo"
            android:layout_alignParentStart="true"
            android:layout_alignParentEnd="true"
            android:drawableStart="@drawable/vector_person"
            android:hint="@string/hint_user"
            android:layout_width="0dp"
            android:layout_height="wrap_content" />
        <EditText
            android:layout_below="@id/etLoginUserName"
            android:drawableStart="@drawable/vector_lock"
            android:layout_margin="12dp"
            android:drawablePadding="12dp"
            android:hint="@string/password"
            android:layout_width="match_parent"
            android:layout_height="wrap_content" />

        <Button
            android:layout_alignParentBottom="true"
            android:background="@color/music_color"
            android:layout_alignParentStart="true"
            android:layout_alignParentEnd="true"
            android:text="@string/button_login"
            android:layout_width="0dp"
            android:layout_margin="12dp"
            android:layout_height="wrap_content" />

    </RelativeLayout>


## 12. FrameLayout: Alineación por region.

![image](https://user-images.githubusercontent.com/31891276/124371349-9aed5a80-dc46-11eb-82ef-78459c719c14.png)

Con FrameLayout podemos organizar vistas unas sobre otras como si fueran capas y ajustar sus atributos layout_gravity para que tomen la posición que indique nuestro diseño. También podemos agregar vistas dinámicas.

## 13. FrameLayout: Uso práctico.

Un dato: Si es cierto q los dp es una unidad de medida que usa android para lo que es el espacio en pantalla. Fue creada para estandarizar una forma de medida, ya que Android tiene una gran cantidad de pantallas con densidades de pixeles muy variadas.
Bueno pero android teniendo esta medida de DPs, divide cualquier pantalla en una cuadricula (como un cuaderno cuadriculado) donde cada cuadradito es de 8dp x 8dp, por esa razon es bueno intentar diseñar teniendo esa regla para las medidas de los views, paddings, margenes, imagenes,iconos,etc. : multiplos de 8 (8dp.16dp, 24 dp), por ejemplo si vas a poner altura a un appBar, no pongas 60, ponle 64, o si pones una altura para esa imageview y quieres poner 20 no pongas 20, ponle 16 o 24, osea siempre intenta llevar tus medidas a multiplos de 8 , es una recomendacion que hacen en la documentacion oficial. esto explica algo que veran constantemente en Android Studio, cuando el IDE autogenera alguna medida normalmente pone 8dp, 16dp, 24dp, etc . por ejemplo cuando estas usando los constraint layout y quieres poner margenes ,android studio te sugiere 8,16,24,etc…esto es por** la famosa regla de 8** anteriormente mencionada.

![image](https://user-images.githubusercontent.com/31891276/124371541-4cd95680-dc48-11eb-92b5-642f18de6833.png)

    <?xml version="1.0" encoding="utf-8"?>
    <FrameLayout xmlns:android="http://schemas.android.com/apk/res/android"
        xmlns:tools="http://schemas.android.com/tools"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:background="@color/music_color_primary"
        android:orientation="vertical">

        <ImageView
            android:layout_gravity="center_horizontal"

            android:id="@+id/ivLoginLogo"
            android:layout_width="140dp"
            android:layout_height="110dp"
            android:src="@drawable/headphone" />

        <EditText
            android:id="@+id/etLoginUsername"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:layout_marginTop="120dp"
            android:layout_marginStart="12dp"
            android:layout_marginEnd="12dp"
            android:drawableStart="@drawable/vector_person"
            android:drawablePadding="12dp"
            android:hint="@string/hint_user" />
        <EditText

            android:drawableStart="@drawable/vector_lock"
            android:layout_marginTop="180dp"
            android:drawablePadding="12dp"
            android:hint="@string/password"
            android:layout_width="match_parent"
            android:layout_height="wrap_content" />

        <Button
            android:layout_gravity="bottom"
            android:layout_width="match_parent"
            android:layout_margin="12dp"
            android:layout_height="wrap_content"
            android:background="@color/music_color"
            android:text="@string/button_login" />

    </FrameLayout>

## 14. Layouts externos: ConstraintLayout.

El ConstraintLayout es que se encarga de que los elementos estén estirados con respectos a otros.
Ejemplo: Si se hiciera invisible el elemento usuario el elemento password heredaría la configuración previa de usuario.

![image](https://user-images.githubusercontent.com/31891276/124371583-c113fa00-dc48-11eb-9ec3-44b80ff02018.png)


Agregar

![image](https://user-images.githubusercontent.com/31891276/124371659-a42bf680-dc49-11eb-8925-e76a97bf2d0f.png)

![image](https://user-images.githubusercontent.com/31891276/124371683-dfc6c080-dc49-11eb-935e-c0ce5659bdaf.png)

Es el Layout por default

![image](https://user-images.githubusercontent.com/31891276/124371714-10a6f580-dc4a-11eb-922d-0edbb306ade7.png)

**Nota Clave:** *para ordenar lo elemntos toca presionar el conjunto de teclas Ctr + Alt + l*

![image](https://user-images.githubusercontent.com/31891276/124372256-2d91f780-dc4f-11eb-83f3-53f288395dc6.png)


    <?xml version="1.0" encoding="utf-8"?>
    <androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
        xmlns:app="http://schemas.android.com/apk/res-auto"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:background="@color/music_color_primary">

        <ImageView
            android:id="@+id/ivLoginLogo"
            android:layout_width="140dp"
            android:layout_height="110dp"
            android:src="@drawable/headphone"
            app:layout_constraintEnd_toEndOf="parent"
            app:layout_constraintStart_toStartOf="parent"
            app:layout_constraintTop_toTopOf="parent" />


        <EditText
            android:id="@+id/etLoginUsername"
            android:layout_width="0dp"
            android:layout_height="wrap_content"
            android:layout_margin="12dp"
            android:layout_marginTop="516dp"
            android:drawableStart="@drawable/vector_person"
            android:hint="@string/hint_user"
            app:layout_constraintEnd_toEndOf="parent"
            app:layout_constraintHorizontal_bias="0.0"
            app:layout_constraintStart_toStartOf="parent"
            app:layout_constraintTop_toBottomOf="@id/ivLoginLogo" />

        <EditText
            android:id="@+id/editText"
            android:layout_width="0dp"
            android:layout_height="wrap_content"
            android:drawableStart="@drawable/vector_lock"
            android:drawablePadding="12dp"
            android:hint="@string/password"
            app:layout_constraintBottom_toTopOf="@id/etLoginUsername"
            app:layout_constraintEnd_toEndOf="parent"
            app:layout_constraintStart_toStartOf="parent" />


        <Button
            android:id="@+id/button"
            android:layout_width="0dp"
            android:layout_height="wrap_content"
            android:background="@color/music_color"
            android:text="@string/button_login"
            android:layout_margin="12dp"
            app:layout_constraintStart_toStartOf="parent"
            app:layout_constraintEnd_toEndOf="parent"
            app:layout_constraintBottom_toBottomOf="parent" />

    </androidx.constraintlayout.widget.ConstraintLayout>


**Algunos short cuts en windows:**
*Ctrl + d al inicio de la línea, la duplica*
*Ctrl + / al incio de la línea, la comenta *
*Ctrl + Alt + Shift comenta varias líneas de código seleccionadas*
