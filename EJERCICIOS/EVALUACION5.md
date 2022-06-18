## Práctica 9.
### Operaciones en una base de datos.
Objetivo: Demostrar las operaciones que se realizan en una base de datos, aplicar el modelo relacional y el lenguaje SQL

Evaluación: Para poder tener correcto cada ejercicio deberán de mostrar el resultado que se da en cada respuesta.

Se tomará la base de datos creada previamente llamada tienda_informatica en donde se creó la tabla producto.

Lista el nombre de todos los productos que hay en la tabla producto.

USE tienda_informatica;

SELECT descripcion FROM producto

![image](https://user-images.githubusercontent.com/104698382/174445754-db9e1238-75a5-4185-b5d1-dad5d302f978.png)


1. Lista los nombres y los precios de todos los productos de la tabla producto.

USE tienda_informatica;

SELECT descripcion, precio FROM producto

![image](https://user-images.githubusercontent.com/104698382/174445795-4d894f0b-5eca-4d0a-b4b4-0c040ba8b387.png)

2. Lista todas las columnas de la tabla producto.

USE tienda_informatica;

SELECT * FROM producto

![image](https://user-images.githubusercontent.com/104698382/174445835-55ebc276-dad5-4b6d-b508-d32090430d5c.png)


3. Devuelve una lista con el nombre del producto, precio y nombre de fabricante de
todos los productos de la base de datos.

USE tienda_informatica;

SELECT descripcion, precio, fabricante FROM producto

![image](https://user-images.githubusercontent.com/104698382/174445873-d9dd9176-9e03-4d81-901f-d4bcde6b5995.png)


Subconsultas (En la cláusula WHERE)
1. Devuelve todos los productos del fabricante Lenovo. (Sin utilizar INNER
JOIN).

USE tienda_informatica;

SELECT * FROM producto
WHERE fabricante='LENOVO'

![image](https://user-images.githubusercontent.com/104698382/174445991-6d3164f5-54f2-45fd-a4d8-7dd0011fb8ad.png)


2. Devuelve todos los datos de los productos que tienen el mismo precio que el
producto más caro del fabricante Lenovo. (Sin utilizar INNER JOIN).

USE tienda_informatica;

SELECT codigo, descripcion, fabricante, MAX(precio) FROM producto
WHERE fabricante='LENOVO'

![image](https://user-images.githubusercontent.com/104698382/174447515-428bc57c-5cfa-4c0c-ad5f-fbb6eb3a0884.png)


3. Lista el nombre del producto más caro del fabricante Lenovo.

USE tienda_informatica;

SELECT descripcion, MAX(precio) FROM producto
WHERE fabricante='LENOVO'

![image](https://user-images.githubusercontent.com/104698382/174447556-53409a11-83bf-4b37-9748-44ae07776cbd.png)
