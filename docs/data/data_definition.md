# Definición de los datos

## Origen de los datos

La fuente de los datos es el "Reporte de casos de cáncer en todo el mundo en los últimos 10 años" de Kaggle, el cual se encuentra en esta dirección web:
https://www.kaggle.com/datasets/zahidmughal2343/global-cancer-patients-2015-2024

## Especificación de los scripts para la carga de datos

Como trabajamos a partir de los datos cargados en el repositorio de GitHub, utilizamos el siguiente script de Python para la carga de los datos:
```python
import pandas as pd

url = 'https://raw.githubusercontent.com/Data-Decoders/practica_profesionalizante_II/master/data/global_cancer_patients_2015_2024.csv'

df = pd.read_csv(url)
```

## Referencias a rutas o bases de datos origen y destino

La ruta o base de datos de origen es:
https://www.kaggle.com/datasets/zahidmughal2343/global-cancer-patients-2015-2024

Aunque por practicidad cargamos los datos en GitHub y ese es nuestro _origen de los datos_ para trabajar:
https://raw.githubusercontent.com/Data-Decoders/practica_profesionalizante_II/master/data/global_cancer_patients_2015_2024.csv

El destino es siempre temporal en la Notebook con la que estemos trabajando (Jupyter o Google Colab).

### Rutas de origen de datos

La ubicación de los archivos de origen de los datos es este repositorio actual, como se mencionó más arriba.

El archivo original de los datos es un solo archivo tipo CSV (comma separated values). Está estructurado en las siguientes columnas:
```
Decimal:  8 cols
String:   5 cols
Integer:  2 cols
Total:   15 cols
```

De momento no se realizaron procedimientos de transformación y limpieza de los datos, ya que los mismos se encontraban preprocesados desde un primer momento.

Sí se realizó un análisis exploratorio, como se detalla en otras secciones de este repositorio.
### Base de datos de destino

Como el dataset fue originalmente obtenido desde Kaggle y posteriormente almacenado en un repositorio de GitHub para facilitar el acceso colaborativo, y debido a que el trabajo se desarrolla íntegramente en Notebooks de Python y se manipula directamente el archivo `.csv`, no se hace uso de una base de datos de destino.

Tampoco fue necesario definir una estructura de base de datos relacional, ya que los datos se procesan de forma directa en memoria a través de pandas y otras herramientas de análisis en Python.
