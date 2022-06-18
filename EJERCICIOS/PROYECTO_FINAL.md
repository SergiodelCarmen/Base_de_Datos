# Proyecto Final de base de datos.
### Indicaciones de lo que se debe realizar

● Diseña el modelo entidad-relación del siguiente problema.

● Crea el script para la base de datos.
Proveedores

Tenemos que diseñar una base de datos sobre proveedores y disponemos de
la siguiente información:

● De cada proveedor conocemos su nombre, dirección, ciudad, provincia y
un código de proveedor que será único para cada uno de ellos.

● Nos interesa llevar un control de las piezas que nos suministra cada
proveedor. Es importante conocer la cantidad de las diferentes piezas
que nos suministra y en qué fecha lo hace. Tenga en cuenta que un
mismo proveedor nos puede suministrar una pieza con el mismo código
en diferentes fechas. El diseño de la base de datos debe permitir
almacenar un histórico con todas las fechas y las cantidades que nos ha
proporcionado un proveedor.

● Una misma pieza puede ser suministrada por diferentes proveedores.

● De cada pieza conocemos un código que será único, nombre, color,
precio y categoría.

● Pueden existir varias categorías y para cada categoría hay un nombre y
un código de categoría único.

● Una pieza sólo puede pertenecer a una categoría.

A continuación, el diagrama E-R y código SQL de la base de datos:

![image](https://user-images.githubusercontent.com/104698382/174450647-1e865af7-b897-4943-bbb7-abc8a0ee770d.png)


CREATE DATABASE proveedores;

USE proveedores;

-- Creamos tablas no dependientes 

CREATE TABLE categoria ( 
  cod_cat INT UNSIGNED NOT NULL PRIMARY KEY,
  nombre VARCHAR(100) NOT NULL
); 

CREATE TABLE proveedor ( 
  cod_prov VARCHAR(100) NOT NULL PRIMARY KEY,
  nombre VARCHAR(100) NOT NULL,
  direccion VARCHAR(100) NOT NULL,
  ciudad VARCHAR(100) NOT NULL,
  provincia INT UNSIGNED NOT NULL
); 

-- Creamos tablas dependientes 

CREATE TABLE pieza ( 
  cod_pza VARCHAR(100) NOT NULL PRIMARY KEY,
  nombre VARCHAR(100) NOT NULL,
  color VARCHAR(100) NOT NULL,
  precio FLOAT NOT NULL,
  cod_cat1 INT UNSIGNED NOT NULL,
  FOREIGN KEY (cod_cat1) REFERENCES categoria(cod_cat)
); 


-- Creamos tablas de las relaciones 

CREATE TABLE suministra (
  cod_prov1 VARCHAR(100) NOT NULL,
  cod_pza1 VARCHAR(100) NOT NULL,
  cantidad INT UNSIGNED NOT NULL,
  fecha_sum DATE NOT NULL,
  FOREIGN KEY (cod_prov1) REFERENCES proveedor(cod_prov),
  FOREIGN KEY (cod_pza1) REFERENCES pieza(cod_pza)
); 


