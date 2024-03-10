# Práctica de Pandas: Introducción a Pandas y Preparación del Entorno

## Introducción a Pandas y su importancia en el análisis de datos

Pandas es una librería de Python que ofrece estructuras de datos y herramientas de análisis de datos de alto nivel y fácil de usar. Pandas se basa en otras librerías como NumPy y Matplotlib, y permite manipular, transformar, limpiar, visualizar y explorar datos de forma eficiente y sencilla. Pandas es ampliamente utilizada en el campo de la ciencia de datos, el aprendizaje automático, la estadística y otras disciplinas que requieren trabajar con datos estructurados o tabulares.

Algunas de las ventajas de usar Pandas son:

- Permite leer y escribir datos en diferentes formatos, como CSV, Excel, JSON, SQL, etc.
- Ofrece estructuras de datos flexibles y expresivas, como las Series y los DataFrames, que facilitan el manejo de datos de diferentes tipos y dimensiones.
- Proporciona una gran variedad de funciones y métodos para realizar operaciones básicas y avanzadas sobre los datos, como selección, filtrado, agrupación, agregación, ordenación, fusión, pivoteo, etc.
- Incorpora funcionalidades para el análisis estadístico y la generación de gráficos a partir de los datos.
- Soporta el manejo de datos faltantes, duplicados, erróneos o inconsistentes, y ofrece técnicas para su detección, eliminación o imputación.
- Facilita la integración con otras librerías de Python, como Scikit-learn, TensorFlow, PyTorch, etc.

## Instalación y configuración de Pandas en el entorno de desarrollo

Para poder utilizar Pandas, es necesario tener instalado Python en el sistema operativo. Se recomienda usar una versión de Python igual o superior a la 3.6. Además, se aconseja utilizar un entorno virtual para aislar las dependencias de cada proyecto y evitar posibles conflictos.

Para instalar Pandas, se puede utilizar el gestor de paquetes de Python, pip, ejecutando el siguiente comando en la terminal o en la línea de comandos del entorno de desarrollo integrado (IDE):

```bash
pip install pandas
```

También se puede instalar Pandas junto con otras librerías científicas de Python mediante el gestor de paquetes Anaconda, ejecutando el siguiente comando:

```bash
conda install pandas
```

Para verificar que Pandas se ha instalado correctamente, se puede ejecutar el siguiente código en el intérprete interactivo de Python o en el IDE:

```python
import pandas as pd
print(pd.__version__)
```

Si no se produce ningún error y se muestra la versión de Pandas, significa que la instalación ha sido exitosa.

## Importación de Pandas y exploración de sus principales componentes

Para poder utilizar las funciones y métodos de Pandas en un script de Python, es necesario importar la librería. Por convención, se suele importar Pandas con el alias 'pd', de la siguiente forma:

```python
import pandas as pd
```

De esta manera, se puede acceder a las funcionalidades de Pandas mediante el prefijo 'pd'.

Las principales estructuras de datos de Pandas son las Series y los DataFrames. Una Serie es un arreglo unidimensional de datos etiquetados, que puede almacenar datos de cualquier tipo, como enteros, flotantes, cadenas, booleanos, etc. Un DataFrame es una estructura bidimensional de datos etiquetados, que se puede ver como una tabla con filas y columnas, donde cada columna puede tener un tipo de dato diferente.

Para crear una Serie, se puede utilizar el constructor `pd.Series(data, index)`, donde `data` es una lista, un diccionario, un arreglo de NumPy o un valor escalar, y `index` es una lista de etiquetas para los datos. Si no se especifica el `index`, se asignan valores enteros desde 0 por defecto. Por ejemplo:

```python
# Crear una Serie a partir de una lista
s1 = pd.Series([10, 20, 30, 40])
print(s1)

# Crear una Serie a partir de un diccionario
s2 = pd.Series({'a': 100, 'b': 200, 'c': 300})
print(s2)

# Crear una Serie a partir de un valor escalar
s3 = pd.Series(5, index=['x', 'y', 'z'])
print(s3)
```

Para crear un DataFrame, se puede utilizar el constructor `pd.DataFrame(data, index, columns)`, donde `data` es una lista de listas, un diccionario de listas, un diccionario de diccionarios, un diccionario de Series, un arreglo de NumPy bidimensional o una Serie, `index` es una lista de etiquetas para las filas y `columns` es una lista de etiquetas para las columnas. Si no se especifican el `index` o las `columns`, se asignan valores enteros desde 0 por defecto. Por ejemplo:

```python
# Crear un DataFrame a partir de una lista de listas
df1 = pd.DataFrame([[1, 2, 3], [4, 5, 6], [7, 8, 9]], columns=['a', 'b', 'c'])
print(df1)

# Crear un DataFrame a partir de un diccionario de listas
df2 = pd.DataFrame({'name': ['Alice', 'Bob', 'Charlie'], 'age': [25, 30, 35], 'gender': ['F', 'M', 'M']})
print(df2)

# Crear un DataFrame a partir de un diccionario de Series
df3 = pd.DataFrame({'s1': s1, 's2': s2})
print(df3)
```

Para leer datos desde un archivo externo, como un CSV, un Excel, un JSON, etc., Pandas ofrece varias funciones, como `pd.read_csv()`, `pd.read_excel()`, `pd.read_json()`, etc. Estas funciones devuelven un DataFrame con los datos del archivo. Por ejemplo, para leer un archivo CSV llamado 'ciudades.csv', se puede hacer lo siguiente:

```python
# Leer un archivo CSV y asignarlo a un DataFrame
df = pd.read_csv('ciudades.csv')
print(df)
```

Para explorar un DataFrame, Pandas ofrece varias propiedades y métodos que permiten obtener información sobre sus características y contenidos. Algunas de estas propiedades y métodos son:

- `df.shape`: devuelve una tupla con el número de filas y columnas del DataFrame.
- `df.columns`: devuelve un objeto Index con los nombres de las columnas del DataFrame.
- `df.index`: devuelve un objeto Index con las etiquetas de las filas del DataFrame.
- `df.dtypes`: devuelve una Serie con los tipos de datos de cada columna del DataFrame.
- `df.info()`: muestra un resumen informativo del DataFrame, incluyendo el índice, las columnas, los tipos de datos, los valores no nulos, el uso de memoria, etc.
- `df.head(n)`: devuelve las primeras n filas del DataFrame. Si no se especifica n, devuelve las primeras 5 filas por defecto.
- `df.tail(n)`: devuelve las últimas n filas del DataFrame. Si no se especifica n, devuelve las últimas 5 filas por defecto.
- `df.sample(n)`: devuelve n filas aleatorias del DataFrame. Si no se especifica n, devuelve una fila por defecto.
- `df.describe()`: devuelve un DataFrame con estadísticas descriptivas de las columnas numéricas del DataFrame, como la media, la desviación estándar, el mínimo, el máximo, los cuartiles, etc.

## Ejercicio

Utiliza el dataset 'spotify-2023.csv' para realizar las siguientes tareas:

- Lee el archivo 'spotify-2023.csv' y asigna los datos a un DataFrame llamado 'canciones'.
- Muestra las primeras 10 filas del DataFrame 'ciudades'.
- Muestra el número de filas y columnas, los nombres de las columnas, los tipos de datos y el uso de memoria del DataFrame 'ciudades'.
- Filtrar el dataset por un país o región de tu interés y analizar las características de las canciones más populares en ese mercado, como el género, el artista, la duración, la energía, la valencia, etc.

## Referencias
- (1) Manipulación y análisis de DataFrames con Pandas. https://dev.to/centroturing/manipulacion-y-analisis-de-dataframes-con-pandas-1dgj.
- (2) Pandas – para trabajar datasets en python – Blog sobre data science .... https://www.datasaurio.com/pandas-para-trabajar-datasets-en-python/.