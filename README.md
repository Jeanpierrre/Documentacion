
control+shift+v
# Documentación de Pandas

Este README proporciona una guía básica sobre las funciones esenciales y conceptos de la biblioteca Pandas en Python.

## Contenido

- [Documentación de Pandas](#documentación-de-pandas)
  - [Contenido](#contenido)
  - [Introducción](#introducción)
  - [Estructuras de Datos](#estructuras-de-datos)
    - [DataFrame](#dataframe)
- [Series](#series)
- [Lectura y Escritura de Datos](#lectura-y-escritura-de-datos)
- [Exportar a Excel](#exportar-a-excel)
- [Manipulación de Datos](#manipulación-de-datos)
  - [Indexación y Selección](#indexación-y-selección)
  - [Operaciones de Agregación](#operaciones-de-agregación)
  - [Operaciones de Filtrado](#operaciones-de-filtrado)
- [Operaciones Numéricas](#operaciones-numéricas)
  - [Operaciones Matemáticas](#operaciones-matemáticas)
  - [Operaciones Estadísticas](#operaciones-estadísticas)
- [Tratamiento de Datos Faltantes](#tratamiento-de-datos-faltantes)
- [Recorrido de datos](#recorrido-de-datos)
- [Visualización de Datos](#visualización-de-datos)

## Introducción

Pandas es una biblioteca de Python que proporciona estructuras de datos flexibles y herramientas para el análisis de datos. Es ampliamente utilizada en el ámbito de la ciencia de datos y ofrece dos estructuras principales: DataFrame y Series.

## Estructuras de Datos

### DataFrame

Un DataFrame es una tabla bidimensional con etiquetas en filas y columnas. Es la estructura principal para trabajar con datos tabulares.

```python
import pandas as pd

# Crear un DataFrame vacío
df = pd.DataFrame()

# Crear un DataFrame desde un diccionario
datos = {'A': [1, 2, 3], 'B': [4, 5, 6]}
df = pd.DataFrame(datos)

```

# Series
Una Serie es una estructura unidimensional similar a un array o lista, y representa una columna en un DataFrame.

```python
# Crear una Serie
serie = pd.Series([10, 20, 30], name='Ejemplo')
```

# Lectura y Escritura de Datos
Pandas facilita la lectura y escritura de datos en diversos formatos, como CSV, Excel y SQL.
```python
# Leer un archivo CSV
df = pd.read_csv('archivo.csv')

#Leer excel sin perdidas
df = pd.read_excel("archivo.xlsx", dtype=str)#evitar perdidas de datos, en el caso de los numeros


# Escribir un DataFrame a un archivo Excel
df.to_excel('archivo.xlsx', index=False)


```
# Exportar a Excel

```python

cabeceras = ['A', 'B', 'C', 'D', 'F']#cabezas
Main = pd.DataFrame(columns=cabeceras)#Asignar al nuevo archivo
Main.to_excel("archivo.xlsx", index=False)

#llenado

nueva_fila = pd.DataFrame('Columnas', columns=prueba.columns)

Main = pd.concat([Main, nueva_fila], ignore_index=True)
```


# Manipulación de Datos

Pandas ofrece diversas funciones para manipular y transformar datos.

## Indexación y Selección
```python

# Seleccionar una columna
columna = df['Nombre_Columna']

# Filtrar filas que cumplen una condición
filtrado = df[df['Columna'] > 10] #df['A']
filtro=(SP['A']==letra) & (SP['B']==letra_1)

# df.loc es un método utilizado en Pandas para la selección y asignación de datos en un DataFrame
df.loc[filas, columnas]

Cantiades= df.loc[:, 'Cantidades'] #acceder a todo
#Seleccionar filas basadas en una condición:

df.loc[df['Columna'] > 10, :]

#utilizar un filtro para mostrar una columna en especifico
Valor=SP.loc[filtrado, 'valor']
```

## Operaciones de Agregación
```python

# Calcular la suma por columna
suma_columnas = df.sum()

# Calcular la media por fila
media_filas = df.mean(axis=1)

```
## Operaciones de Filtrado
```python
# Filtrar filas que cumplen una condición
datos_filtrados = df[df['Columna'] > 10]
```

# Operaciones Numéricas
Pandas y NumPy se integran para realizar operaciones eficientes en datos numéricos.

## Operaciones Matemáticas
```python

# Multiplicar una columna por un escalar
df['Nueva_Columna'] = df['Columna'] * 2
```
## Operaciones Estadísticas
```python

# Calcular la desviación estándar de una columna
desviacion_estandar = np.std(df['Columna'])
```

# Tratamiento de Datos Faltantes

Pandas proporciona herramientas para trabajar con datos faltantes.

```python

# Eliminar filas con datos faltantes
df_sin_nulos = df.dropna()

# Rellenar datos faltantes con un valor específico
df_con_relleno = df.fillna(0)

```
# Recorrido de datos
```python
        for indice, fila in file.iterrows():
```

# Visualización de Datos

Pandas se integra con bibliotecas de visualización como Matplotlib y Seaborn.
```python

import matplotlib.pyplot as plt

# Crear un gráfico de barras
df['Columna'].plot(kind='bar')
plt.show()
```

