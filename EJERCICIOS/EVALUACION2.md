## Práctica 3.
### Introducción a SQL
Objetivo: Demostrar la correcta identificación de los conceptos del lenguaje SQL
Ejercicio:

1. Menciona los comandos DML: (valor .85)

SELECT, INSERT, UPDATE, DELETE.

2. Menciona 3 tipos de datos que existen: (valor .85)

CHAR, VARCHAR(X), INTEGER O INT.


3. ¿Qué diferencia existe entre TRUNCATE y DELETE?(valor .85)

Existen 4 diferencias básicas entre TRUNCATE y DELETE:
TRUNCATE es una operación de DDL, mientras que DELETE es una operación DML.
TRUNCATE elimina todo el contenido de la tabla. mientras que DELETE hace un borrado selectivo (algunos registros).
TRUNCATE no se ejecuta si existen registros de FK, mientras que DELETE puede hacerlo mientras los registros o la FK esté deshabilitada.
TRUNCATE es la forma más rápida de eliminar el contenido de una tabla, mientras que DELETE es más lenta.


4. ¿Para qué se utiliza el atributo UNIQUE?(valor .85)

Nos permite establecer este atributo a los campos que requerimos tengan datos que no se puedan repetir.

5. ¿Qué diferencia hay entre los tipos de datos VARCHAR y CHAR? (valor .85)

Los CHAR están definidos por un número finito de caracteres, los cuales ocupan una cantidad fija de memoria. Los VARCHAR, podemos indicarle una cantidad mayor y siempre tendrán la cantidad de memoria que ocupen dado los datos del usuario.

6. Defina brevemente el significado de las siglas SQL(valor .85)
SQL significa Structured Query Language, en español Lenguaje de consulta estructurado, es un lenguaje estándar e interactivo de acceso a bases de datos relacionales que permite especificar diversos tipos de operaciones en ellas, gracias a la utilización del álgebra y de cálculos relacionales, el SQL brinda la posibilidad de realizar consultas con el objetivo de recuperar información de las bases de datos de manera sencilla.


7. Defina brevemente qué es MySQL WorkBench (valor .85)

Es un sistema gestor de base de datos (software y aplicaciones), que soporta el lenguaje SQL. Es un software de código abierto.

## Práctica 5.
### Gestores de base de datos

Objetivo: Categorizar los distintos gestores de base de datos que existen y señalar las
ventajas y desventajas.

Evaluación: Conoce los tipos de gestores de base de datos 3 puntos.

Domina sus diferencias de los gestores de base de datos mencionados 3 puntos

Ejercicio:

En un mapa conceptual presenta 3 gestores de bases de datos, sus características
principales, las ventajas y desventajas. (valor 6)

![image](https://user-images.githubusercontent.com/104698382/173464808-0d6aaeba-eae9-4da3-bc61-b780a71e613e.png)



## Práctica 6.
### Herramienta en línea y ejercicio necesarios para realizar las prácticas

Creación de base de datos.

Objetivo: Demostrar mediante la creación de una base de datos el uso y la aplicación de
las funciones

Ejercicio: Creación de la base de datos (valor 18 puntos)

Tienda de informática

![image](https://user-images.githubusercontent.com/91554777/170415101-717bca19-3644-46a9-8a57-8d5940c5d283.png)

Se trata de una sola tabla que no tiene relaciones con otras tablas por lo que el modelo y el código SQL quedan de la siguiente manera:


Modelo entidad/relación

![image](https://user-images.githubusercontent.com/104698382/173466286-c609e5aa-e501-4048-b358-6023b76442c0.png)


Base de datos para MySQL

Se generó el siguiente código:

CREATE DATABASE tienda_informatica;

USE tienda_informatica;


-- Creación de la única tabla.


CREATE TABLE producto(

codigo VARCHAR(100) NOT NULL PRIMARY KEY,

descripcion VARCHAR(200) NOT NULL,

precio FLOAT UNSIGNED NOT NULL,

fabricante VARCHAR(100) NOT NULL

);


INSERT INTO producto VALUES ('DD-23', 'Disco duro SATA3 1 TB', 86.99, 'SEAGATE');

INSERT INTO producto VALUES ('MM-34', 'Memoria RAM DDR4 8 GB', 120.6, 'CRUCIAL');

INSERT INTO producto VALUES ('DD-98', 'Disco SSD 1 TB', 150.99, 'SAMSUNG');

INSERT INTO producto VALUES ('MM-98', 'GeForce GTX 1050Ti', 185.7, 'GIGABYTE');

INSERT INTO producto VALUES ('MM-23', 'GeForce GTX 1080 Xtreme', 755.6, 'CRUCIAL');

INSERT INTO producto VALUES ('MT-12', 'Monitor 24 LED Full HD', 202.1, 'ASUS');

INSERT INTO producto VALUES ('MT-08', 'Monitor 27 LED Full HD', 245.99, 'ASUS');

INSERT INTO producto VALUES ('LP-19', 'Portátil Yoga 520', 559.2, 'LENOVO');

INSERT INTO producto VALUES ('LP-11', 'Portátil IdeaPAD 320', 444.2, 'LENOVO');

INSERT INTO producto VALUES ('IM-56', 'Impresora HP Deskjet 3720', 59.99, 'HP');

INSERT INTO producto VALUES ('IP-54', 'Impresora HP Laserjet Pro M26nw', 180.3, 'HP');


Se puede consultar en:
https://www.db-fiddle.com/f/nuZQZABixVNoGsYs6J1feM/0

Imagen de la ejecución:
![image](https://user-images.githubusercontent.com/104698382/173467765-71aeb69a-3015-4502-b817-f284963467cb.png)

