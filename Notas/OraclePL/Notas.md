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
      


   ## Update Inster Delete.
 
 **Update**  
 
      DECLARE
      v_salario_max number;
      BEGIN
      SELECT MAX(salary) into v_salario_max
      from employees;
      DBMS_OUTPUT.put_line(v_salario_max);
      update employees set salary = 23500 where salary = v_salario_max;
      END;
      
**insert**
 
            DECLARE
            v_region_id number;
            v_contry_name varchar(10);
            BEGIN
            select region_id 
            into v_region_id
            from regions where region_name = 'Asia';

            v_contry_name := 'Korea';
            insert into countries (country_id,country_name,region_id) values ('KR',v_contry_name, v_region_id);
            END;

**Deleted**

      DECLARE
      v_country_id VARCHAR(2);
      BEGIN
      SELECT country_id 
      into v_country_id 
      FROM 
      countries where country_name ='Korea';
      DELETE from countries where country_id=v_country_id;
      END;
## Funciones

UPPER() -- mayusculas
Lowwer

      DECLARE
      v_last_name VARCHAR2(25);
      BEGIN
      select last_name
      into v_last_name
      from employees
      where employee_id=100;
      dbms_output.put_line(v_last_name);
      END;
      
**Fecha**

      DECLARE
      v_fecha date;
      v_fecha2 date;
      BEGIN
      v_fecha := sysdate;
      v_fecha2 := LAST_DAY(v_fecha);
      DBMS_OUTPUT.put_line(v_fecha);
      DBMS_OUTPUT.put_line(v_fecha2);
      END;
      
nvl()-- if null then;
to_char();


** % Type**

      DECLARE
      v_job_id employees.job_id%type;

      BEGIN

      select e.job_id 
      into v_job_id
      from employees e where e.employee_id =134;
      DBMS_OUTPUT.put_line(v_job_id);

      END;

**% row type**

      DECLARE
      v_jov jobs%rowtype;
      v_desc jobs.job_title%type;
      v_mi_salary jobs.max_salary%type;
      BEGIN

      select j.*
      INTO v_jov
      from jobs j where j.job_id = 'IT_PROG';

      v_desc :=v_jov.job_title;
      v_mi_salary := v_jov.max_salary;
      DBMS_OUTPUT.put_line('Para el trabajo con titulo ' || v_desc ||' el salario minimo es: '||v_mi_salary);

      END;


**Insert**

      DECLARE
      v_jov jobs%rowtype;

      BEGIN

      v_jov.job_id := 'DBA';
      v_jov.job_title := 'Administrator DBA';
      v_jov.min_salary := 5000;
      v_jov.max_salary := 11000;

      insert into jobs VALUES v_jov;

      END;
      
**UPDATE**

      DECLARE
      v_jov jobs%rowtype;

      BEGIN

      v_jov.job_id := 'DBA';
      v_jov.job_title := 'Administrator DBA';
      v_jov.min_salary := 6000;
      v_jov.max_salary := 11000;

      UPDATE jobs SET ROW = v_jov WHERE job_id = 'DBA';

      END;
      
set SERVEROUT on

## IF:


      DECLARE
      v_edad number;
      BEGIN
      v_edad :=18;
      if v_edad >= 18 then
        DBMS_OUTPUT.put_line('Es mayor de edad');
      else
          DBMS_OUTPUT.put_line('No Es mayor de edad');
      end if;
      END;
 
 Other     
      
     DECLARE
      v_salary number;
      BEGIN
      select e.salary
      into v_salary
      from employees e
      where e.employee_id =200;
      if v_salary >1000 and v_salary > 5000 then
        DBMS_OUTPUT.put_line('Empleado de categoria C');
      else
          DBMS_OUTPUT.put_line('Empleado de categoria B');
      end if;
      END; 


## Loop

      DECLARE
      v_contador number := 0;
      BEGIN
      loop
          v_contador := v_contador+1;
          DBMS_OUTPUT.PUT_LINE('El numero es :' || v_contador);
          if v_contador = 7 then
              exit;
          end if;

      end loop;    

      END;
      
**exit when    ** 

      DECLARE
      v_contador number := 0;
      BEGIN
      loop
          v_contador := v_contador+1;
          DBMS_OUTPUT.PUT_LINE('El numero es :' || v_contador);
          exit when v_contador = 7;

      end loop;    

      END;
