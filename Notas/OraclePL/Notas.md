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
      
**exit when** 

      DECLARE
      v_contador number := 0;
      BEGIN
      loop
          v_contador := v_contador+1;
          DBMS_OUTPUT.PUT_LINE('El numero es :' || v_contador);
          exit when v_contador = 7;

      end loop;    

      END;


## Continue: 

      DECLARE
      v_contador number := 0;
      BEGIN
      loop
          v_contador := v_contador+1;

          if v_contador = 3 then 
              continue;
          end if;
          DBMS_OUTPUT.PUT_LINE('El numero es :' || v_contador);
          exit when v_contador = 7;

      end loop;    

      END;
   
## While

      DECLARE
      v_contador number := 0;
      BEGIN
      while v_contador < 7  loop 
          v_contador := v_contador+1;
          DBMS_OUTPUT.PUT_LINE('El numero es :' || v_contador);
       end loop;
      END;
      
## For

      DECLARE
      v_texto varchar(25);
      v_contador number := 0;
      BEGIN

      v_texto := 'El valor del numero es:'  ;
      for numero in 1..7 loop 
          DBMS_OUTPUT.PUT_LINE(v_texto || numero);
       end loop;
      END;
      
   # Cursores
   
   trabajan sobre el contex area, que es el area de memoria privada de oracle.
   
   
   Cursores implicitos: son creados automaticamente por oracle DML (Insert , update, delete)
   
   SQL%Found devuelve true  
   SQL%NoFound devuelve true   
   SQL%rowcount Devuelve el numero de filas devuelto o afectado.
   
      DECLARE
      v_cantidad number;
      v_afecto boolean;
      v_afecto_txt VARCHAR(25);
      BEGIN
      update employees e
      set e.salary = e.salary *1.5
      where e.department_id=20;

      v_cantidad := SQL%ROWCOUNT;
      v_afecto := sql%found;

      case v_afecto
      when true then v_afecto_txt := 'si';
      when false then v_afecto_txt := 'no';
      end case;
      DBMS_OUTPUT.put_line(v_afecto_txt);
      DBMS_OUTPUT.put_line(v_cantidad);

      END;
      
      
  xxx
  
      DECLARE
      v_cantidad number;
      v_afecto boolean;
      v_afecto_txt VARCHAR(25);
      v_salario employees.salary%TYPE;
      BEGIN
      update employees e
      set e.salary = e.salary *1.5
      where e.department_id=453528;

      v_cantidad := SQL%ROWCOUNT;
      v_afecto := sql%found;

      case v_afecto
      when true then v_afecto_txt := 'si';
      when false then v_afecto_txt := 'no';
      end case;
      DBMS_OUTPUT.put_line(v_afecto_txt);
      DBMS_OUTPUT.put_line(v_cantidad);

      select  e.salary
      into v_salario
      from employees e where e.employee_id=201;
      v_cantidad := SQL%ROWCOUNT;
      v_afecto := sql%found;
      case v_afecto
      when true then v_afecto_txt := 'si';
      when false then v_afecto_txt := 'no';
      end case;
      DBMS_OUTPUT.put_line(v_afecto_txt);
      DBMS_OUTPUT.put_line(v_cantidad);
      DBMS_OUTPUT.put_line(v_salario);
      END;
   
## Cursores Explicitos.


![image](https://user-images.githubusercontent.com/31891276/137813715-865db5d4-5467-484b-b033-0389032b4425.png)

![image](https://user-images.githubusercontent.com/31891276/137813727-55e233ec-629e-414f-9ea8-bab40c896d26.png)

![image](https://user-images.githubusercontent.com/31891276/137813737-14c41c1b-ba41-48b0-b090-f611f40d7e4a.png)


      DECLARE
      cursor empleados is
      select e.first_name, e.last_name, e.hire_date
      from employees e
      where e.hire_date BETWEEN DATE'2002-01-01' and date'2002-12-31';
      v_nombre VARCHAR(25);
      v_apellido varchar(25);
      v_contratacion date;
      BEGIN

      open empleados;

      loop 
      FETCH empleados into v_nombre,v_apellido,v_contratacion;

      exit when empleados%notfound;
      DBMS_OUTPUT.put_line('Nombre: '||v_nombre||' Apellido: '||v_apellido||' Contratacion: '||v_contratacion);
      end loop;
      close empleados;
      END;
      
      
   Cursor con for:
   
   
      DECLARE
      cursor empleados is
      select e.first_name, e.last_name, e.hire_date
      from employees e
      where e.hire_date BETWEEN DATE'2002-01-01' and date'2002-12-31';

      BEGIN
      for reg in empleados loop
      DBMS_OUTPUT.put_line('Nombre: '||reg.first_name||' Apellido: '||reg.last_name||' Contratacion: '||reg.hire_date);
      end loop;
      END;
      
      
Con parametros:

      DECLARE
      cursor empleados(p_desde date, p_hasta date) is
      select e.first_name, e.last_name, e.hire_date
      from employees e
      where e.hire_date BETWEEN p_desde and p_hasta;
      v_desde date;
      v_hasta date;
      BEGIN
      v_desde := date'2002-01-01';

      select max(hire_date)
      into v_hasta
      from employees
      where department_id = 100;
      --v_hasta := date'2003-12-31';
      for reg in empleados(v_desde,v_hasta) loop
      DBMS_OUTPUT.put_line('Nombre: '||reg.first_name||' Apellido: '||reg.last_name||' Contratacion: '||reg.hire_date);
      end loop;
      END;

Update cursor



      DECLARE
      cursor empleados is
      select e.*
      from employees e
      where e.hire_date <= date'2005-12-31' and e.commission_pct is null
      for update;
      v_porcentaje_comision  number;
      BEGIN

          for emp in empleados loop
             v_porcentaje_comision :=0;
              if emp.salary BETWEEN 1000 and 5000 then
                v_porcentaje_comision := 0.1;
              elsif emp.salary BETWEEN 5001 and 10000 then
                v_porcentaje_comision := 0.2;
              elsif emp.salary > 10000  then
                v_porcentaje_comision := 0.3;
              end if; 
              DBMS_OUTPUT.put_line('Empleado: '||emp.first_name||' Apellido: '||emp.last_name||' con id: '||emp.employee_id||' Clifica para comision');
              DBMS_OUTPUT.put_line('$ Comision: '||v_porcentaje_comision || '%');

              update employees set commission_pct = v_porcentaje_comision
              where current of empleados;
          end loop;
      END;


## EXCEPTIONS

            DECLARE
            v_busqueda employees.first_name%TYPE;
            v_telefono employees.phone_number%TYPE;
            BEGIN
            v_busqueda := 'DEDED';
            select e.phone_number
            into v_telefono
            from employees e
            where e.first_name = v_busqueda;
            DBMS_OUTPUT.PUT_LINE('el telefono es: '|| v_telefono);
            EXCEPTION
            WHEN TOO_MANY_ROWS THEN
            DBMS_OUTPUT.PUT_LINE('VERIFIQUE EL NUMERO DE FILAS');
            WHEN NO_DATA_FOUND THEN
            DBMS_OUTPUT.PUT_LINE('VERIFIQUE EL NOMBRE');
            END;
            
 # Funciones
 
       create or REPLACE FUNCTION pedidos_pendientes return VARCHAR2
      is 
      v_cantidad number;
      begin
      select count(*) into v_cantidad
      from pedidos where fechaentregado is null;
      return v_cantidad;
      end;
      

## Funciones con parametros.


      CREATE or replace function calcular_valor_pedido(p_idpedido number)
      RETURN number is

          cursor articulos(v_idpedido number) is
          select pa.cantidad, a.precio
          from pedidos_articulos pa
          inner join articulos a on a.idarticulo = pa.idarticulo
          where pa.idpedido =v_idpedido;

          v_total number := 0;
          v_porcentaje_costo_entrega number;
          v_costo_entrega number;
          begin

          select c.costoentrega
          into v_porcentaje_costo_entrega
          from canales_venta c
          inner join pedidos p on c.idcanalventa = p.idcanalventa
          where p.idpedido = p.idpedido;

              for art in articulos(p_idpedido) loop
                  v_total:= v_total+(art.precio*art.cantidad);
              end loop;
          v_costo_entrega := (v_porcentaje_costo_entrega*v_total) /100;   
          v_total := v_total + v_costo_entrega;

          exception when OTHERS then

          DBMS_OUTPUT.PUT_LINE('Hubo un error');
      end;


usando la funcion

      select calcular_valor_pedido(2)
      from dual;
      
      
![image](https://user-images.githubusercontent.com/31891276/137826671-7680af9b-bdbb-4182-a199-09dd01af782c.png)

  ??
  
      select p.*, calcular_valor_pedido(p.idpedido) from pedidos p  
      
![image](https://user-images.githubusercontent.com/31891276/137826740-effc3e9e-302b-487c-a5f9-43e47faa2082.png)


      create or replace procedure ordenar_a_fabrica is

      cursor articulos is
      select a.idarticulo, a.stock,a.idsucursal
      from articulos_sucursales a;
      v_mejorprecio number;
      v_idfabricante number;
      v_siguiente_id number;
      begin

          for art in articulos loop

              if art.stock = 0 then
               select min (precio)
               into v_mejorprecio
               from articulos_fabricantes af
               where af.idarticulo = art.idarticulo
               group by idarticulo;

               select af.idfabricante
               into v_idfabricante
               from articulos_fabricantes af
               where af.idarticulo = v_mejorprecio;

               select max(idpedidofabrica)+1
               into v_siguiente_id 
               from pedido_fabrica;

               insert into pedido_fabrica (idpedidofabrica,idsucursal,idarticulo,idfabricante,fechapedido,cantidad)
               values(v_siguiente_id,art.idsucursal, art.idarticulo,v_idfabricante,sysdate,10);

               end if;
           end loop;
       end;
 
 
 
  ![image](https://user-images.githubusercontent.com/31891276/137832090-e3350515-d345-4f53-b324-990208a94d7d.png)
  
  ![image](https://user-images.githubusercontent.com/31891276/137832117-65110d5f-0e85-4349-a56e-ed54cf417248.png)



            create or replace procedure imprimir_pedido (p_idpedido in number, p_resumen_pedido out clob)
            is

            v_res_pedido clob;
            br varchar2(1) := chr(10);
            sep varchar2(35) := br||'--------------------------------'||br;
            v_datos_cliente varchar2(140);
            v_direccion_cliente varchar2(140);
            v_precio_final number;

            cursor pedidos_articulo(id_pedido number) is
            select p.cantidad,a.nombre,a.precio
            from pedidos_articulos p
            inner join articulos a on p.idarticulo = a.idarticulo
            where p.idpedido = id_pedido;

            begin

                v_res_pedido := sep;
                v_res_pedido:= v_res_pedido||'PEDIDO N??: '||p_idpedido;
                v_res_pedido := v_res_pedido||sep;

                select c.apellido||', '||c.nombre||'. DOC: '||c.documento, d.calle||' '||d.numero||' - Piso: '||d.piso||' '||d.departamento
                into v_datos_cliente,v_direccion_cliente
                from pedidos p
                inner join clientes c on p.idcliente = c.idcliente
                inner join direcciones d on d.idcliente = p.iddireccion
                where p.idpedido = p_idpedido;

                v_res_pedido := v_res_pedido||'CLIENTE: '||v_datos_cliente||br||'DIRECCION: '||v_direccion_cliente||sep;
                v_res_pedido := v_res_pedido||sep||'A R T I C U L O S'||sep;

                for art in pedidos_articulo(p_idpedido) loop

                    v_res_pedido := v_res_pedido||art.nombre||'(x'||art.cantidad||')........$'||art.precio||br;

                end loop;

                v_precio_final := calcular_valor_pedido(p_idpedido);
                v_res_pedido:=v_res_pedido||sep||'TOTAL: $'||v_precio_final||sep;


                p_resumen_pedido := v_res_pedido;

            end;
            
            
            
  Ejecutar:
  
      declare

      v_id_pedido number;
      v_resumen clob;

      begin

          v_id_pedido := 3;

          imprimir_pedido(v_id_pedido,v_resumen);
          dbms_output.put_line(v_resumen);

      end;
  
## Triggers


![image](https://user-images.githubusercontent.com/31891276/137947930-22e98c41-bfda-439e-a379-6324c2eb6180.png)

![image](https://user-images.githubusercontent.com/31891276/137947985-8f3535ef-eb45-424c-8a5e-18cde234f9ed.png)

![image](https://user-images.githubusercontent.com/31891276/137948032-b0ce5d5b-0ffd-4823-977f-c96a5eb65d9c.png)




