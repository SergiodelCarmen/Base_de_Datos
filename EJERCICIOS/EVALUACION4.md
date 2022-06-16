## Práctica 8.
### Disparadores (Triggers)

Objetivo: Demostrar las operaciones que se realizan en una base de datos.

Ejercicio: Crea una base de datos llamada test que contenga una tabla llamada
alumnos con las siguientes columnas. (valor 18)

Evaluación:

Creación de la base de datos : 9 puntos.

Creación de los Disparadores(Triggers): 9 puntos.

Tabla alumnos:

● id (entero sin signo)

● nombre (cadena de caracteres)

● apellido1 (cadena de caracteres)

● apellido2 (cadena de caracteres)

● nota (número real)

De acuerdo a los datos anteriores, se crea la BD y tabla de la siguiente manera:

CREATE DATABASE test;

USE test;

CREATE TABLE alumnos(

id INT UNSIGNED PRIMARY KEY,

nombre VARCHAR(100),

apellido1 VARCHAR(100),

apellido2 VARCHAR(100),

nota FLOAT

);



Una vez creada la tabla escriba dos triggers con las siguientes características:

● Trigger 1: trigger_check_nota_before_insert

  o Se ejecuta sobre la tabla alumnos.
  
  o Se ejecuta antes de una operación de inserción.
  
  o Se almacena la leyenda 'se ingreso un registro'
  

Para almacenar el primer trigger, debemos crear una tabla con el nombre ingreso_registro:
  
CREATE TABLE ingreso_registro(
  
accion VARCHAR(100),

insertado DATETIME

);


Posteriormente, el trigger:

CREATE TRIGGER trigger_check_nota_before_insert BEFORE INSERT ON 

alumnos FOR EACH ROW

INSERT INTO ingreso_registro VALUES ('se creó un registro', NOW());

  

● Trigger2 : trigger_check_nota_before_update
  o Se ejecuta sobre la tabla alumnos.
  
  o Se ejecuta antes de una operación de actualización.
  
  o Se ingresa la leyenda 'se modifico un regisstro'
  

Para almacenar el primer trigger, debemos crear otra tabla con el nombre modificacion_registro:
  
CREATE TABLE modificacion_registro(
  
actividad VARCHAR(100),

modificacion DATETIME

);


Posteriormente, el trigger:

CREATE TRIGGER trigger_check_nota_before_update BEFORE UPDATE ON 

alumnos FOR EACH ROW

INSERT INTO modificacion_registro VALUES ('se modificó un registro', NOW());

  
Una vez creados los triggers escribe varias sentencias de inserción y actualización
sobre la tabla alumnos y verifica que los triggers se están ejecutando
correctamente.

Las sentencias que se ejecutaron, fueron las siguientes para la inserción de valores:

USE test;

INSERT INTO alumnos VALUES (1001, 'Sergio', 'del Carmen', 'Robles', 9.6);

Y al hacer la consulta de la tabla de inserción, tenemos:

![image](https://user-images.githubusercontent.com/104698382/173986887-c97c5126-00f2-48db-867e-e1e8bc9b61cf.png)

Insertamos 2 registros más:

INSERT INTO alumnos VALUES (1002, 'Kevin Elias', 'Araujo', 'González', 8.8);
INSERT INTO alumnos VALUES (1003, 'Mitzi Maleni', 'Jaramillo', 'Araujo', 9.9);

![image](https://user-images.githubusercontent.com/104698382/173987135-17edfd98-827a-4110-8490-73a8186ce990.png)


Las sentencias que se ejecutaron, fueron las siguientes para la modificación de valores:

USE test;

UPDATE alumnos

SET apellido2='Hernández', nota=9.5

WHERE nombre='Sergio';

![image](https://user-images.githubusercontent.com/104698382/173988173-0cc9fa94-e64a-45de-9323-fd290343279f.png)

Hacemos 2 modificaciones más:

USE test; 

UPDATE alumnos 

SET apellido1='Guerra', nota=8.5

WHERE nombre='Kevin Elías';

UPDATE alumnos

SET nombre='Laura', nota=10

WHERE apellido1='Jaramillo';


![image](https://user-images.githubusercontent.com/104698382/173988490-b5eb0400-9dc4-496f-8130-cc90cd75533b.png)


Para comprobar los resultados, ejecutamos la sentencia SELECT * FROM alumnos para verificar los cambios en la tabla principal:

![image](https://user-images.githubusercontent.com/104698382/173988649-beef7381-7673-42ae-babd-d95bac27b09c.png)

y observamos que sí realizó los cambios.

