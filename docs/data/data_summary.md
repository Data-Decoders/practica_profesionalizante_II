# Reporte de Datos

Este documento contiene los resultados del análisis exploratorio de datos.








<br>
<br>
<br>

## Resumen general de los datos

El dataset analizado contiene información detallada sobre pacientes con distintos tipos de cáncer, recopilada entre los años 2015 y 2024. En total, se dispone de 50,000 observaciones y 15 variables. Las variables cubren aspectos demográficos, clínicos, de hábitos y ambientales, así como información sobre costos y severidad de la enfermedad.
### Estructura y tipos de variables

- **Variables numéricas (8):**
    Incluyen edad, año de diagnóstico, factores de riesgo (genético, contaminación, alcohol, tabaco, obesidad), costo del tratamiento, años de supervivencia y puntaje de severidad.
- **Variables categóricas (5):**
    Género, país/región, tipo de cáncer, estadio del cáncer y un identificador único de paciente.
- **Variable objetivo:**
    `Target_Severity_Score` (puntaje de severidad), de tipo numérico y continua.

### Distribución de las variables

- **Numéricas:**
    La edad de los pacientes varía entre 20 y 89 años, con una media de 54.4 años y una desviación estándar de 20.2. Los factores de riesgo (genético, contaminación, alcohol, tabaco, obesidad) tienen distribuciones similares, con medias cercanas a 5 y rangos de 0 a 10. El costo del tratamiento oscila entre 5,000 y casi 100,000 USD, con una media de 52,467 USD. Los años de supervivencia tienen una media de 5 años, y el puntaje de severidad (`Target_Severity_Score`) varía entre 0.9 y 9.16, con una media de 4.95.
- **Categóricas:**  
    El género está distribuido en tres categorías ('Male', 'Female', y una tercera opción). Hay 10 regiones o países diferentes, 8 tipos de cáncer y 5 estadios de la enfermedad, siendo 'Colon' y 'Stage II' las categorías más frecuentes en sus respectivas variables.

### Visualización y análisis de la distribución

Se generaron histogramas y boxplots para todas las variables numéricas. Estos gráficos permitieron identificar la presencia de algunas asimetrías y valores extremos (outliers), especialmente en variables como el costo del tratamiento y los factores de riesgo. Sin embargo, la mayoría de las variables numéricas presentan distribuciones aproximadamente simétricas y centradas en sus medias.

![image](https://github.com/user-attachments/assets/ad300f4c-60c5-4899-bf17-c2094ca917e8)
_Histogramas de las variables numéricas_

<br>

![image](https://github.com/user-attachments/assets/0a162d8c-1a60-479f-b2ac-d9cdba0755b3)
_Boxplots de las variables numéricas_

### Correlaciones

El análisis de correlación revela que las variables con mayor relación con la severidad (`Target_Severity_Score`) son el riesgo genético, el tabaquismo, la contaminación del aire y el consumo de alcohol, todas con correlaciones superiores a 0.35. El costo del tratamiento muestra una correlación negativa moderada con la severidad, lo que sugiere que los casos más severos pueden asociarse a mayores costos.








<br>
<br>
<br>

## Resumen de calidad de los datos

El análisis muestra que no existen valores faltantes en ninguna de las variables del dataset. Todas las columnas presentan 50,000 registros completos, lo cual facilita el análisis y el modelado posterior.








<br>
<br>
<br>

## Variable objetivo

La variable objetivo del presente análisis es **`Target_Severity_Score`**, que representa un puntaje numérico y continuo asociado a la severidad del cáncer en cada paciente. Esta es nuestra variable clave para los modelos predictivos y para la comprensión clínica, ya que resume en un solo valor la gravedad del caso considerando múltiples factores de riesgo y características del paciente.

### Distribución estadística

Según el resumen estadístico, `Target_Severity_Score` presenta las siguientes características:
- **Cantidad de observaciones:** 50,000
- **Media:** 4.95
- **Desviación estándar:** 1.20
- **Valor mínimo:** 0.90
- **Percentil 25%:** 4.12
- **Mediana (50%):** 4.95
- **Percentil 75%:** 5.78
- **Valor máximo:** 9.16

La mediana y la media prácticamente coinciden, lo que sugiere una distribución bastante simétrica en torno al valor central. La dispersión es moderada, con la mayoría de los valores comprendidos entre 4 y 6, pero existen casos de severidad tanto baja como muy alta.

### Visualización de la distribución

Para analizar visualmente el comportamiento de la variable objetivo se generaron los siguientes gráficos:

#### Histograma con curva de densidad (KDE)

El histograma de `Target_Severity_Score` muestra una distribución aproximadamente normal, centrada en torno al valor 5. La curva de densidad (KDE) refuerza esta observación, indicando que la mayoría de los pacientes presentan un puntaje de severidad moderado. Sin embargo, se observa una ligera cola hacia la derecha, lo que indica la presencia de algunos casos con severidad alta.

![image](https://github.com/user-attachments/assets/7a7bd6da-cb51-4a02-bcfb-a4538bf4fe58)

#### Boxplot

El boxplot revela que la mayor parte de los datos se concentra entre los valores 4.12 y 5.78, con pocos valores atípicos (outliers) por encima de 8. Esto sugiere que los casos de severidad extrema son poco frecuentes, pero existen y deben ser tenidos en cuenta en el análisis clínico y predictivo.

![image](https://github.com/user-attachments/assets/1a4506bb-149e-4714-ab58-5c57ff727540)

### Interpretación

La variable `Target_Severity_Score` es adecuada como objetivo para modelado predictivo por su naturaleza continua y su capacidad para reflejar matices en la gravedad de la enfermedad. La simetría de su distribución facilita el uso de técnicas estadísticas y de machine learning que asumen normalidad en la variable dependiente. Además, la existencia de casos severos, aunque poco frecuentes, puede ser relevante para tareas de clasificación de riesgo o priorización clínica.








<br>
<br>
<br>

## Variables individuales

Análisis detallado de cada variable individual del dataset, incluyendo estadísticas descriptivas, interpretación de los gráficos de distribución, relación con la variable objetivo y posibles transformaciones recomendadas para cada una.

### Variables numéricas

#### Age (Edad)
- **Estadísticas**: 
    - Media: 54.4 años
    - Desviación estándar: 20.2
    - Mínimo: 20
    - Máximo: 89
    - Percentiles 25/50/75: 37 / 54 / 72
- **Distribución**:
    - El histograma muestra una distribución aproximadamente uniforme, sin sesgos marcados ni acumulaciones inusuales.
- **Relación con la variable objetivo**:
    - La correlación con `Target_Severity_Score` es prácticamente nula (-0.001), por lo que la edad no parece influir directamente en la severidad.
- **Posibles transformaciones**:
    - Normalización o estandarización si se utiliza en modelos sensibles a la escala.

#### Year (Año de diagnóstico)
- **Estadísticas**:
    - Rango: 2015 a 2024
    - Media: 2019.5
    - Distribución: uniforme, con igual cantidad de registros por año.
- **Relación con la variable objetivo**:
    - Correlación mínima (0.002).
- **Posibles transformaciones**:
    - Puede tratarse como variable categórica (one-hot) o usarse para crear variables de tendencia temporal.

#### Genetic_Risk (Riesgo genético)
- **Estadísticas**:
    - Media: 5.0
    - Desviación estándar: 2.89
    - Rango: 0 a 10
- **Distribución**:
    - Aproximadamente uniforme.
- **Relación con la variable objetivo**:
    - Fuerte correlación positiva (0.48).
    - A mayor riesgo genético, mayor severidad.
- **Posibles transformaciones**:
    - Normalización o estandarización.

#### Air_Pollution (Contaminación del aire)
- **Estadísticas**:
    - Media: 5.01
    - Desviación estándar: 2.89
    - Rango: 0 a 10
- **Distribución**:
    - Aproximadamente uniforme.
- **Relación con la variable objetivo**:
    - Correlación positiva moderada (0.37).
- **Posibles transformaciones**:
    - Normalización o estandarización.

#### Alcohol_Use (Consumo de alcohol)
- **Estadísticas**:
    - Media: 5.01
    - Desviación estándar: 2.89
    - Rango: 0 a 10
- **Distribución**:
    - Aproximadamente uniforme.
- **Relación con la variable objetivo**:
    - Correlación positiva moderada (0.36).
- **Posibles transformaciones**:
    - Normalización o estandarización.

#### Smoking (Tabaquismo)
- **Estadísticas**:
    - Media: 4.99
    - Desviación estándar: 2.88
    - Rango: 0 a 10
- **Distribución**:
    - Aproximadamente uniforme.
- **Relación con la variable objetivo**:
    - Fuerte correlación positiva (0.48).
- **Posibles transformaciones**:
    - Normalización o estandarización.

#### Obesity_Level (Nivel de obesidad)
- **Estadísticas**:
    - Media: 4.99
    - Desviación estándar: 2.89
    - Rango: 0 a 10
- **Distribución**:
    - Aproximadamente uniforme.
- **Relación con la variable objetivo**:
    - Correlación positiva baja (0.25).
- **Posibles transformaciones**:
    - Normalización o estandarización.

#### Treatment_Cost_USD (Costo del tratamiento)
- **Estadísticas**:
    - Media: 52,467 USD
    - Desviación estándar: 27,363 USD
    - Rango: 5,000 a 99,999 USD
- **Distribución**:
    - Ligeramente asimétrica, con presencia de valores altos (outliers).
- **Relación con la variable objetivo**:
    - Correlación negativa moderada (-0.47): a mayor severidad, mayor costo.
- **Posibles transformaciones**:
    - Transformación logarítmica para reducir asimetría y el impacto de outliers.

#### Survival_Years (Años de supervivencia)
- **Estadísticas**:
    - Media: 5.0
    - Desviación estándar: 2.88
    - Rango: 0 a 10
- **Distribución**:
    - Aproximadamente uniforme.
- **Relación con la variable objetivo**:
    - Correlación muy baja (0.004).
- **Posibles transformaciones**:
    - Transformación logarítmica si se detecta asimetría en análisis más avanzados.

#### Target_Severity_Score (Puntaje de severidad, variable objetivo)
- **Estadísticas**:
    - Media: 4.95
    - Desviación estándar: 1.20
    - Rango: 0.9 a 9.16
- **Distribución**:
    - Aproximadamente normal, centrada en 5, con ligera cola derecha.
- **Transformaciones**:
    - No se recomienda transformar la variable objetivo para modelos de regresión estándar.

### Variables categóricas

#### Gender (Género)
- **Categorías**: Male, Female, (posible tercera opción)
- **Distribución**:
    - Masculino: 34%
    - Femenino: 33%
    - Otro: 33%
- **Relación con la variable objetivo**:
    - Diferencias leves entre géneros en la severidad promedio.
- **Posibles transformaciones**:
    - Codificación one-hot o label encoding.

#### Country_Region (País/Región)
- **Categorías**: 10 países/regiones
- **Distribución**:
    - Australia y China son los más frecuentes.
- **Relación con la variable objetivo**:
    - Puede captar diferencias geográficas en severidad.
- **Posibles transformaciones**:
    - Codificación one-hot o agrupación por regiones.

#### Cancer_Type (Tipo de cáncer)
- **Categorías**: 8 tipos
- **Distribución**:
    - Colon es el más frecuente.
- **Relación con la variable objetivo**:
    - Diferencias marcadas de severidad según tipo.
- **Posibles transformaciones**:
    - Codificación one-hot.

#### Cancer_Stage (Estadio del cáncer)
- **Categorías**: 5 estadios (Stage 0 a Stage IV)
- **Distribución**:
    - Stage II es el más frecuente.
- **Relación con la variable objetivo**:
    - Relación ordinal clara: mayor estadio, mayor severidad.
- **Posibles transformaciones**:
    - Codificación ordinal o one-hot.

#### Patient_ID
- **Descripción**:
    - Identificador único, irrelevante para modelado.
- **Transformaciones**:
    - No utilizar como variable predictora.

### Resumen de transformaciones recomendadas

|Variable|Transformación recomendada|
|---|---|
|Age|Normalización/estandarización|
|Year|Categórica/numérica, crear variables temporales|
|Genetic_Risk|Normalización/estandarización|
|Air_Pollution|Normalización/estandarización|
|Alcohol_Use|Normalización/estandarización|
|Smoking|Normalización/estandarización|
|Obesity_Level|Normalización/estandarización|
|Treatment_Cost_USD|Logarítmica|
|Survival_Years|Logarítmica (si asimétrica)|
|Gender|One-hot/label encoding|
|Country_Region|One-hot/agrupación regional|
|Cancer_Type|One-hot|
|Cancer_Stage|Ordinal/one-hot|








<br>
<br>
<br>

## Ranking de variables

### Metodología de análisis

Para determinar la importancia de las variables predictoras respecto a la variable objetivo `Target_Severity_Score`, se han aplicado diferentes técnicas:
1. **Correlación de Pearson**: Medición directa de la relación lineal entre cada variable y el puntaje de severidad. 
2. **Análisis visual de relaciones bivariadas**: Exploración gráfica de patrones entre predictores y la variable objetivo.
3. **Interpretación contextual**: Análisis de la relevancia clínica y epidemiológica de cada factor de riesgo.

### Ranking de variables por correlación con la severidad

|Ranking|Variable|Correlación|Tipo de relación|
|---|---|---|---|
|1|Smoking (Tabaquismo)|0.48|Positiva fuerte|
|2|Genetic_Risk (Riesgo genético)|0.47|Positiva fuerte|
|3|Treatment_Cost_USD (Costo del tratamiento)|-0.46|Negativa fuerte|
|4|Air_Pollution (Contaminación del aire)|0.37|Positiva moderada|
|5|Alcohol_Use (Consumo de alcohol)|0.36|Positiva moderada|
|6|Obesity_Level (Nivel de obesidad)|0.25|Positiva débil|
|7|Survival_Years (Años de supervivencia)|0.004|Despreciable|
|8|Year (Año de diagnóstico)|0.002|Despreciable|
|9|Age (Edad)|-0.001|Despreciable|

### Interpretación del ranking

1. **Factores de alto impacto** (correlación > 0.4):    
    - **Tabaquismo y riesgo genético**: Son los factores más determinantes de la severidad del cáncer, ambos con correlaciones cercanas a 0.5, indicando una fuerte relación positiva. Esto sugiere que intervenciones para reducir el consumo de tabaco podrían tener un impacto significativo en la severidad.
    - **Costo del tratamiento**: Muestra una fuerte correlación negativa (-0.46), lo que podría indicar que tratamientos más costosos se asocian con casos menos severos, posiblemente debido a una intervención más temprana o efectiva.
2. **Factores de impacto moderado** (correlación 0.25-0.4):
    - **Contaminación del aire y consumo de alcohol**: Con correlaciones de 0.37 y 0.36 respectivamente, representan factores ambientales y de estilo de vida modificables.
    - **Obesidad**: Con una correlación de 0.25, aunque más débil, sigue siendo relevante como factor de riesgo.
3. **Factores de bajo impacto** (correlación < 0.01):
    - **Edad, año de diagnóstico y años de supervivencia**: Sorprendentemente, estas variables muestran correlaciones prácticamente nulas con la severidad, lo que contradice algunas expectativas clínicas.

### Variables categóricas

Aunque no incluidas **de momento** en el análisis de correlación, las variables categóricas también pueden tener un impacto significativo:
- **Cancer_Stage**: Probablemente tenga una fuerte relación con la severidad, aunque al ser ordinal requiere un análisis diferente.
- **Cancer_Type**: Diferentes tipos de cáncer podrían asociarse con distintos niveles de severidad.
- **Country_Region**: Podría reflejar diferencias en sistemas de salud y acceso a tratamiento.

### Directrices extra para el modelado predictivo

1. **Priorizar variables de alto impacto**: Tabaquismo, riesgo genético y costo del tratamiento deberían ser incluidas en el modelo predictivo.
2. **Transformaciones pendientes**:
    - Para variables numéricas con fuertes correlaciones, normalización o estandarización.
    - Para Treatment_Cost_USD, consideraremos la transformación logarítmica dada su distribución.
    - Para variables categóricas, codificación apropiada (one-hot o ordinal según corresponda).
3. **Consideraciones adicionales**:
    - Nos falta evaluar posibles interacciones entre variables importantes (por ejemplo, tabaquismo y contaminación).
    - Consideraremos métodos de selección de características más avanzados como PCA o técnicas basadas en modelos de árbol para capturar relaciones no lineales.








<br>
<br>
<br>

## Relación entre variables explicativas y variable objetivo

En esta sección se presenta un análisis de la relación entre las variables explicativas y la variable objetivo. Se utilizan gráficos como la matriz de correlación y el diagrama de dispersión para entender mejor la relación entre las variables. Además, se pueden utilizar técnicas como la regresión lineal para modelar la relación entre las variables.



