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
  
  
  ## Select Into
  
      DECLARE
      v_name varchar(15);

      BEGIN
      SELECT e.last_name 
      INTO v_name
      from employees e where e.employee_id = 100;
      DBMS_OUTPUT.put_line(v_name);
      END;
      
   multiple variables
   
      DECLARE
      v_last_name varchar(15);
      v_first_name VARCHAR(15);
      salary NUMBER;
      BEGIN
      SELECT e.last_name, e.first_name, e.salary
      INTO v_last_name, v_first_name, salary
      from employees e where e.employee_id = 100;
      DBMS_OUTPUT.put_line(v_last_name);
      DBMS_OUTPUT.put_line(v_first_name);
      DBMS_OUTPUT.put_line(salary);
      END;
      

      
   