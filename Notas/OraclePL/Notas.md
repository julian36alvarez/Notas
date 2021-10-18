# ORACLE PL -SQL

![image](https://user-images.githubusercontent.com/31891276/137656459-47c2145a-1aa0-41fa-9856-893dc76c10f2.png)

## BLOQUE DE TIPO ANOMIMO

      DECLARE
      --INICIO VARIABLES
      mi_texto VARCHAR(20);

      BEGIN
      -- SECCION EJECUTABLE
      mi_texto := 'Hola Olix!';
      DBMS_OUTPUT.put_line(mi_texto);
      --EXCEPTION
      END;
YA QUE NO TIENE NOMBRE Y NO SE GUARDARA EN DB

## VARIABLES

varchar
number
date
boolean

    DECLARE
    --INICIO VARIABLES
    nombre VARCHAR(20);
    edad number;
    f_nacimiento CONSTANT date := date'2014-03-24';
    acepta_terminos BOOLEAN;

    BEGIN
    -- SECCION EJECUTABLE
    nombre := 'Olix';
    edad := 7;
    acepta_terminos := true;

    DBMS_OUTPUT.PUT_LINE('Nombre: '|| nombre);
    DBMS_OUTPUT.PUT_LINE('Edad: '|| edad);
    DBMS_OUTPUT.PUT_LINE('Nacimiento: '|| f_nacimiento);
    END;
    
 parametro entre 'Olix'
    
    DECLARE
    --INICIO VARIABLES
    nombre VARCHAR(20);
    edad number;
    f_nacimiento CONSTANT date := date'2014-03-24';
    acepta_terminos BOOLEAN;

    BEGIN
    -- SECCION EJECUTABLE
    nombre := &mivalor;
    edad := 7;
    acepta_terminos := true;

    DBMS_OUTPUT.PUT_LINE('Nombre: '|| nombre);
    DBMS_OUTPUT.PUT_LINE('Edad: '|| edad);
    DBMS_OUTPUT.PUT_LINE('Nacimiento: '|| f_nacimiento);
    END;
  
