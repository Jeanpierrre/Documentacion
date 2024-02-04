# Documentación de SQL

## Contenido

- [Documentación de SQL](#documentación-de-sql)
  - [Contenido](#contenido)
  - [Introducción](#introducción)
  - [Consultas Básicas](#consultas-básicas)
    - [SELECT](#select)
    - [INSERT](#insert)
    - [UPDATE](#update)
    - [DELETE](#delete)
  - [Consultas Avanzadas](#consultas-avanzadas)
    - [JOIN](#join)
    - [LEFT JOIN](#left-join)
    - [RIGHT JOIN](#right-join)
    - [FULL JOIN](#full-join)
    - [CROSS JOIN](#cross-join)
    - [Alias tabla](#alias-tabla)
    - [Subconsultas](#subconsultas)
    - [Funciones de Agregación](#funciones-de-agregación)
    - [GROUP BY](#group-by)
    - [ORDER BY](#order-by)

## Introducción

SQL (Structured Query Language) es un lenguaje de programación diseñado para gestionar y recuperar datos almacenados en sistemas de gestión de bases de datos relacionales (RDBMS). A continuación, se presenta una guía rápida sobre las consultas SQL, desde las básicas hasta las más avanzadas.

## Consultas Básicas

### SELECT

```sql
SELECT columna1, columna2 FROM nombre_de_tabla WHERE condicion;
```
```sql
```

### INSERT

```sql
INSERT INTO nombre_de_tabla (columna1, columna2) VALUES (valor1, valor2);

```

### UPDATE
```sql
UPDATE nombre_de_tabla SET columna1 = nuevo_valor WHERE condicion;
```

### DELETE

```sql
DELETE FROM nombre_de_tabla WHERE condicion;
```

## Consultas Avanzadas

### JOIN

La cláusula INNER JOIN se utiliza para combinar filas de dos tablas basándose en una condición de relación entre ellas

```sql
SELECT t1.columna1, t2.columna2
FROM tabla1 AS t1
INNER JOIN tabla2 AS t2 ON t1.columna_relacionada = t2.columna_relacionada;
```
### LEFT JOIN
La cláusula LEFT JOIN devuelve todas las filas de la tabla izquierda (tabla1) y las filas coincidentes de la tabla derecha (tabla2). Si no hay coincidencias, se devuelven valores NULL para las columnas de la tabla derecha.

```sql
SELECT t1.columna1, t2.columna2
FROM tabla1 AS t1
LEFT JOIN tabla2 AS t2 ON t1.columna_relacionada = t2.columna_relacionada;
```
### RIGHT JOIN
La cláusula RIGHT JOIN es similar a LEFT JOIN, pero devuelve todas las filas de la tabla derecha (tabla2) y las filas coincidentes de la tabla izquierda (tabla1). Si no hay coincidencias, se devuelven valores NULL para las columnas de la tabla izquierda.
```sql
SELECT t1.columna1, t2.columna2
FROM tabla1 AS t1
RIGHT JOIN tabla2 AS t2 ON t1.columna_relacionada = t2.columna_relacionada;
```
### FULL JOIN
La cláusula FULL JOIN devuelve todas las filas cuando hay una coincidencia en una de las tablas. Si no hay coincidencias, se devuelven valores NULL para las columnas sin coincidencias.

```sql
SELECT t1.columna1, t2.columna2
FROM tabla1 AS t1
FULL JOIN tabla2 AS t2 ON t1.columna_relacionada = t2.columna_relacionada;

```
### CROSS JOIN
La cláusula CROSS JOIN devuelve el producto cartesiano de ambas tablas, es decir, todas las combinaciones posibles de filas entre las dos tablas.

```sql
SELECT t1.columna1, t2.columna2
FROM tabla1 AS t1
CROSS JOIN tabla2 AS t2;

```


### Alias tabla
El uso de alias (AS t1, AS t2) simplifica la escritura al referenciar columnas de tablas en la consulta.
```sql
SELECT t1.columna1, t2.columna2
FROM tabla1 AS t1
INNER JOIN tabla2 AS t2 ON t1.columna_relacionada = t2.columna_relacionada;

```
### Subconsultas

Las subconsultas permiten realizar consultas anidadas para obtener información específica de otra tabla.

```sql
SELECT columna1, columna2
FROM tabla1
WHERE columna_relacionada IN (SELECT columna_relacionada FROM tabla2 WHERE condicion);

```

### Funciones de Agregación
Las funciones de agregación, como COUNT, se utilizan para realizar operaciones en conjuntos de datos, en este caso, contar el número total de filas.

```sql
SELECT COUNT(*) as total_filas FROM nombre_de_tabla;

```

### GROUP BY
La cláusula GROUP BY se utiliza para agrupar filas basadas en los valores de una columna específica, mientras que las funciones de agregación operan en cada grupo.
```sql
SELECT columna1, COUNT(*) as total
FROM nombre_de_tabla
GROUP BY columna1;

```

### ORDER BY
La cláusula ORDER BY se utiliza para ordenar los resultados en base a una o más columnas, ya sea de forma ascendente (ASC) o descendente (DESC).


```sql
SELECT columna1, columna2
FROM nombre_de_tabla
ORDER BY columna1 ASC, columna2 DESC;


```


