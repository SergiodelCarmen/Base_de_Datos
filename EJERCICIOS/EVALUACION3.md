
## Práctica 4
### Data warehouse

Objetivo: Demostrar la identificación de los elementos que componen data warehouse y
su esquema

Ejercicio:

1. ¿Qué es un DataWarehouse?(valor 2)

Un DWH es una base de datos con estructura OLAP, que se encuentra por encima de las bases de datos transaccionales y que está diseñada para el análisis de los datos que hay en el sistema.

2. Realiza un diseño del modelo en estrella (valor 2)

![image](https://user-images.githubusercontent.com/104698382/173476141-24896c07-ee27-47ea-ba14-3b4a65f33cf3.png)


3. Realiza un diseño del modelo copo de nieve (valor 2)

![image](https://user-images.githubusercontent.com/104698382/173476726-608a50d9-c982-4f0a-bbb0-24ed98627434.png)


## Práctica 7
### Funciones en SQL
Objetivo: Demostrar el uso y aplicación en una base de datos para mejorar la gestión

Ejercicio:

1. Calcula el número total de productos que hay en la tabla productos. (valor 4.5).

Se tomará la base de datos utilizada en la Práctica 6.

USE tienda_informatica;

SELECT COUNT(*)

  FROM producto;
  
  
El resultado obtenido, es 11 de acuerdo a la siguiente imagen:

![image](https://user-images.githubusercontent.com/104698382/173477437-898f30df-cf92-4b74-9353-4ff853f19d70.png)



2. Muestra el número total de productos que tiene cada uno de los fabricantes. El listado
también debe incluir los fabricantes que no tienen ningún producto. El resultado
mostrará dos columnas, una con el nombre del fabricante y otra con el número de
productos que tiene. Ordene el resultado descendentemente por el número de
productos. (valor 4.5).

USE tienda_informatica;

SELECT fabricante, COUNT(fabricante)

  FROM producto 
  
GROUP BY fabricante

ORDER BY COUNT(fabricante) DESC;


El resultado de lo anterior, está en la siguiente imagen:

![image](https://user-images.githubusercontent.com/104698382/173482551-4cf44cbc-f988-4aa0-9629-235dcee74740.png)



3. Muestra el precio máximo, precio mínimo y precio medio de los productos de cada
uno de los fabricantes. El resultado mostrará el nombre del fabricante junto con los
datos que se solicitan. (valor 4.5).

USE tienda_informatica;


SELECT fabricante, MAX(precio), MIN(precio), AVG(precio) FROM producto


GROUP BY(fabricante)

ORDER BY(precio) DESC;

El resultado de lo anterior, está en la siguiente imagen:

![image](https://user-images.githubusercontent.com/104698382/173488216-31432682-65a7-4ac2-94ab-0a3058c920b6.png)



4. Muestra el nombre de cada fabricante, junto con el precio máximo, precio mínimo,
precio medio y el número total de productos de los fabricantes que tienen un precio
medio superior a 200€. Es necesario mostrar el nombre del fabricante. (valor 4.5)

USE tienda_informatica;

SELECT fabricante, MAX(precio), MIN(precio), AVG(precio), COUNT(fabricante) 

FROM producto

GROUP BY(fabricante)

HAVING AVG(precio) > 200

ORDER BY(precio) DESC;


El resultado de lo anterior, está en la siguiente imagen:

![image](https://user-images.githubusercontent.com/104698382/173489642-7a98768b-a167-4339-9773-1d0cb4b927c7.png)



