# Notas de Bases Técnicas de Andorid 

## Clase 13 . Qué es y como funciona Gradle.
Grade es un sistema integrado a Andorid y desarrollado por google que permite integrar dependencias, crear un sistema de archivos y generar un ejecutable  APK
Gradle es un sistema de compilación que reune en un uno solo las mejores prestaciones de otros sistemas de compilación. Está basado en JVM (Java Virtual Machine), lo que          significa que puedes escribir tu propio script en java, y que Android Studio lo entenderá y lo usará.

![src/gradle.png](src/gradle.png)

### Clase 14 Generación de un apk en Android.

APK es la extensión de los archivos ejecutables en Android su significado es application package, generarlo tiene un proceso interesante y se lleva a cabo bajo un proceso de compilación.

  1. El compilador de Android convierte tu código fuente a un tipo de bytecode pero más eficiente para la máquina virtual de Android estos son archivos .dex.

  2. Gradle empaqueta los archivos .dex y todos los recursos que usaste en la aplicación, imágenes, audios, videos, etc. generando un .apk
  3. Gradle firma tu apk resultante usando una keystore.
  4. Se puede generar un apk a modo de solo pruebas o general un apk listo para ser lanzado a la tienda, para cada caso será el tipo de keystore que debas usar.
  5. Como detalle notarás que al ejecutar el empaquetado intervendrá zipalign quien generará una versión optimizada del .apk para el teléfono



![src/apkAndorid.png](src/apkAndorid.png)
![src/apkAndorid2.png](src/apkAndorid2.png)


### Clase 15 Google Play Services.

Cuando queremos trabajar una aplicacion o integrar servicios de google debemos trabajar con estas librerias. por ejemplo login con google. 

  1. Instalar el .apk de Google Play Services.
  2. Incluir la librería del servicio que vayas a usar.

### Clase 16 Google Play Services.

 servicios de Google que tienes disponible para integrar a tus proyectos Android como librerías:
 API	BIBLIOTECA
    **Google+:**	com.google.android.gms:play-services-plus:15.0.0
    **Google Account Login:**	com.google.android.gms:play-services-auth:15.0.0
    **Google Actions, Base Client Library:**	com.google.and roid.gms: play-services-base:15.0.0
    **Google Sign In:**	com.google.android.gms:play-services-identity:15.0.0
    **Google Analytics:**	com.google.android.gms:play-services-analytics:15.0.0
    **Google Awareness:**	com.google.android.gms:play-services-awareness:15.0.0
    **Google Cast:**	com.google.android.gms:play-services-cast:15.0.0
    **Google Cloud Messaging:**	com.google.android.gms:play-services-gcm:15.0.0
    **Google Drive:**	com.google.android.gms:play-services-drive:15.0.0
    **Google Fit:**	com.google.android.gms:play-services-fitness:15.0.0
    **Google Location and Activity Recognition:**	com.google.android.gms:play-services-location:15.0.0
    **Google Maps:**	com.google.android.gms:play-services-maps:15.0.0
    **Google Mobile Ads:**	com.google.android.gms:play-services-ads:15.0.0
    **Google Places:**	com.google.android.gms:play-services-places:15.0.0
    **Mobile Vision:**	com.google.android.gms:play-services-vision:15.0.0
    **Google Nearby:**	com.google.android.gms:play-services-nearby:15.0.0
    **Google Panorama Viewer:**	com.google.android.gms:play-services-panorama:15.0.0
    **Google Play Game Services:**	com.google.android.gms:play-services-games:15.0.0
    **SafetyNet:**	com.google.android.gms:play-services-safetynet :15.0.0
    **Android Pay:**	com.google.android.gms:play-services-wallet :15.0.0
    **Wear OS by Google:**	com.google.android.gms:play-services-wearable:15 .0.0
    
    https://developers.google.com/android/guides/setup
    
    
### Clase 16 Google Play Services.

    
