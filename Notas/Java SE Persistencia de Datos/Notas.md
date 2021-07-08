# Curso de Java SE Persistencia de Datos.


## 1. ¿Cómo empezar? Persistencia de datos y bases de datos relacionales.

![image](https://user-images.githubusercontent.com/31891276/124797811-513b9300-df18-11eb-84d2-59a1532aa5a8.png)

## 2. Conociendo algunas bases de datos relacionales: MySQL, PostgreSQL, Oracle

![image](https://user-images.githubusercontent.com/31891276/124798156-ab3c5880-df18-11eb-9296-6949c326d3fa.png)

## 3. Instalación de MySQL.

## 4. Diseñando nuestra base de datos.

## 5. Creando nuestra base de datos usando DDL PostrGrest

  ![image](https://user-images.githubusercontent.com/31891276/124808860-1724be00-df25-11eb-850b-fb4cf14f2067.png)

## 6. Instalación de Netbeans, IntelliJ Idea

## 7. Creación del proyecto en Java.

en intelliJ Idea, 
![image](https://user-images.githubusercontent.com/31891276/124831727-41847480-df41-11eb-8395-dc2c47af1123.png)

## 8. Conexion PostgreSQL y MySql
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.SQLException;

    public class Conexion {

        public Connection get_MYSQLSQLConction() {
            Connection conection = null;
            try {
                conection = DriverManager.getConnection("jdbc:mysql://127.0.0.1:3306/mensajes_app", "root", "");
                if (conection != null) {
                    System.out.println("Conexion Exitosa MYSQL");
                }
            } catch (SQLException e) {
                System.out.println(e);
            }
            return conection;
        }

        public Connection get_postgreSQLConection() {
            Connection conection = null;
            try {
                conection = DriverManager.getConnection("jdbc:postgresql://127.0.0.1:5432/mensajeria_db", "postgres", "w");
                System.out.println("Conexion Exitosa POSTGRESQL");
                System.out.println("conection = " + conection);
            } catch (SQLException e) {
                System.out.println(e);
            }
            return conection;
        }
    }
    
Este seria nuestra clase main:

    import java.sql.Connection;

    public class Inicio {
        public static void main(String[] args) {

            Conexion connection = new Conexion();

            try(Connection cnMysql= connection.get_MYSQLSQLConction()) {

            }catch (Exception e){
                System.out.println(e);
            }

            try(Connection cnMysql= connection.get_postgreSQLConection()) {

            }catch (Exception e){
                System.out.println(e);
            }

        }
    }

Es importante resaltar que en el archivo pom.xml se agreagaron las dependencias necesarias para los contradores JDBC:

Alt + Insert

![image](https://user-images.githubusercontent.com/31891276/124849201-f2037000-df63-11eb-8d58-9db7a856b0fc.png)

![image](https://user-images.githubusercontent.com/31891276/124849246-08a9c700-df64-11eb-8547-53235ec55e2d.png)

y agregamnos la demendencia.

    <?xml version="1.0" encoding="UTF-8"?>
    <project xmlns="http://maven.apache.org/POM/4.0.0"
             xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
             xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
        <modelVersion>4.0.0</modelVersion>

        <groupId>org.example</groupId>
        <artifactId>mensajes_app</artifactId>
        <version>1.0-SNAPSHOT</version>
        <dependencies>
            <dependency>
                <groupId>org.postgresql</groupId>
                <artifactId>postgresql</artifactId>
                <version>42.2.22.jre7</version>
            </dependency>
            <dependency>
                <groupId>mysql</groupId>
                <artifactId>mysql-connector-java</artifactId>
                <version>8.0.24</version>
            </dependency>
        </dependencies>


        <properties>
            <maven.compiler.source>8</maven.compiler.source>
            <maven.compiler.target>8</maven.compiler.target>
        </properties>
    </project>

## 9. Git Y GitHub.

  1. Creamos el repositorio en GitHub.
  2. Usamos los comandos en la consola de GIT
      
    git init

    git add .

    git commit -m "first commit"

    git remote add origin https://github.com/NOMBRE_USUARIO/NOMBRE_PROYECTO.git

    git push -u origin master
 
 3. Hacemos el Push a nuetro proyecto y subimos los cambios.

## 10. Flujo y lógica de la aplicación.

Usamos la capa DAO para conectarnos a nuestra base de datos. **DAO** Significa Data Access Object.

![image](https://user-images.githubusercontent.com/31891276/124852975-b91ac980-df6a-11eb-86a4-a3d2a68c2c64.png)

https://github.com/julian36alvarez/JavaPersistence.git  
  
## 11.
## 12.
## 13.
## 14.
## 15.
## 16.
## 17.
## 18.
## 19.
## 20.
## 21.
## 22.
## 23.
## 24.
