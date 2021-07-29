# Transferencia de conocimiento aplicaciones.

## ActivacionesCRM.  

El FRONT del activador se encuentra dentro del CRM portal (sostenibilidad) de Tigo. El Portal CRM es la plataforma CORE de la Unidad Móvil para el soporte a los procesos de venta, posventa y en general todos los procesos de servicio al cliente a usuarios de líneas móviles Tigo.
En Tigo contamos con diferentes familias o tipos de planes, que pueden ser activados de acuerdo con las necesidades de los clientes, estos se pueden clasificar:  
Activaciones:  
    • Prepago  
    • Control  
    • Arma Tu Plan (ATP)  
    • Postpago  
    • Financiación con Terceros (Credivalores)  
    • Portabilidad  
    • Ventas Segmentadas  
    
![image](https://user-images.githubusercontent.com/31891276/127529510-4addcfd8-85a3-4be8-a861-75b2a94467a4.png)

### Diferencias entre archivos EAR y WAR
La mayor diferencia entre los archivos JAR, WAR y EAR es el hecho de que están dirigidos a diferentes entornos. 
Un archivo EAR requiere un servidor de aplicaciones totalmente compatible con la plataforma Java, Enterprise Edition (Java EE) o Jakarta Enterprise Edition (EE), 
como WebSphere o JBoss, para ejecutarse. Un archivo WAR solo requiere un servidor de aplicaciones compatible con Java EE Web Profile para ejecutarse, y un archivo JAR
solo requiere una instalación Java.

![image](https://user-images.githubusercontent.com/31891276/127529649-9b091bb0-1ec2-48b7-96bd-b4dcae7a9275.png)

![image](https://user-images.githubusercontent.com/31891276/127529680-0887edf0-b289-41f4-9cb6-a77c9fd55bd0.png)


Gestión de configuración.

URL Línea Base 
        
     http://10.100.82.12/Accenture-T2/CRM-Portal/APP-ActivadoresStandalone

Versionamiento GIT:

    http://netvm-pgit01

Merge:

Se pueden presentar dos escenarios para la realización del Merge.  
     1. ** Merge de la línea base:  **
    cuando se pasa un requerimiento a producción rama X, desde la línea base se hace Merge con la rama X  
     2. ** Merge de una rama: **
    cuando hay un requerimiento en ejecución rama X (línea base + requerimiento), y en el periodo de ejecución pasa producción otro requerimiento con rama Z.
En este caso se crea una rama J la cual contiene la línea base(línea base + rama Z) y se hace un Merge con la rama X.

### Actualización de Línea Base  
Se realiza una semana después que se hace un paso a producción y con estabilización de los sistemas.

Procesos de Release o Versionamiento para Salidas (Dsllo, Integración o Pro)

    1. Salida a desarrollo: Se crea una rama reléase la cual va a
    contener el requerimiento + lo que está en la línea base. Se
    crea una carpeta con el nombre del requerimiento la cual va a
    contener la rama reléase.
    2. Salida a pruebas: Se copia la carpeta de desarrollo a pruebas.
    3. Salida a producción: Se copia la carpeta de pruebas a
    producción. Se hace un merge de la línea base con la rama
    reléase.
