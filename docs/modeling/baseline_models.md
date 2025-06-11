## Descripción del modelo

El modelo *baseline* es el primer modelo construido y se utiliza para establecer una línea base para el rendimiento de los modelos posteriores. En este proyecto se estableció un modelo *baseline* principal entrenado sin variables sensibles (SVS) como la edad, el género o la región. El objetivo era crear un modelo de clasificación que fuera ético y justo, evitando que las predicciones se basaran en características que pudieran generar discriminación.

Mediante la función `compare_models()` de la librería PyCaret se evaluaron múltiples algoritmos de clasificación y el que obtuvo el mejor rendimiento fue la **Regresión Logística** (`LogisticRegression`), el cual fue seleccionado como el modelo *baseline* final. Se entrenó un segundo modelo comparativo que sí incluía las variables sensibles (CVS) para evaluar su impacto en el rendimiento y la equidad.

## Variables de entrada

La siguiente es la lista de las variables de entrada utilizadas en el modelo *baseline* (SVS), de acuerdo con la información extraída del dataframe `datos_procesados_svs`:
* `Genetic_Risk`
* `Air_Pollution`
* `Alcohol_Use`
* `Smoking`
* `Obesity_Level`
* `Cancer_Stage`
* `Cancer_Type_Cervical`
* `Cancer_Type_Colon`
* `Cancer_Type_Leukemia`
* `Cancer_Type_Liver`
* `Cancer_Type_Lung`
* `Cancer_Type_Prostate`
* `Cancer_Type_Skin`

## Variable objetivo

El nombre de la variable objetivo utilizada en el modelo es `Target_Severity_Level`. Esta es una variable categórica creada a partir de la variable numérica `Target_Severity_Score` y representa el nivel de gravedad del cáncer en tres clases: "Baja" (0), "Media" (1) y "Alta" (2).

## Evaluación del modelo

### Métricas de evaluación

Para evaluar el rendimiento del modelo se utilizaron métricas estándar de clasificación provistas por la librería PyCaret. Las métricas evaluadas por la función `compare_models()` incluyen:

* Accuracy
* AUC (Area Under the Curve)
* Recall (Sensibilidad)
* Precision
* F1-Score
* Kappa
* MCC (Matthews Correlation Coefficient)

A continuación se muestran los resultados obtenidos para el modelo **Logistic Regression** seleccionado como modelo *baseline* por su buen rendimiento general:

| Modelo              | Accuracy | AUC    | Recall | Precision | F1     | Kappa  | MCC    |
|---------------------|----------|--------|--------|-----------|--------|--------|--------|
| Logistic Regression | 0.7034   | 0.8805 | 0.7034 | 0.7074    | 0.7052 | 0.5552 | 0.5553 |

Estos valores indican que el modelo tiene un rendimiento equilibrado con buena capacidad para identificar correctamente los distintos niveles de severidad. Sin embargo como se detalla en el análisis posterior, presenta ciertas dificultades al clasificar los casos de severidad "media".

Además se generó una **Matriz de Confusión** para analizar visualmente los aciertos y errores del modelo para cada clase.

### Resultados de evaluación

La siguiente tabla es la matriz de confusión para el modelo *baseline* de Regresión Logística (SVS) en el conjunto de prueba.

| Clase Verdadera | Predicción: Baja (0) | Predicción: Media (1) | Predicción: Alta (2) |
| :--- | :--- | :--- | :--- |
| **Baja (0)** | 3813 | 1205 | 0 |
| **Media (1)**| 1071 | 2893 | 1018 |
| **Alta (2)** | 0 | 1141 | 3814 |

## Análisis de los resultados

El análisis del modelo *baseline* de Regresión Logística (SVS) revela las siguientes fortalezas y debilidades:

**Fortalezas:**
* **Modelo Ético:** Al no incluir variables sensibles como género, edad o país, el modelo reduce el riesgo de generar predicciones sesgadas o discriminatorias.
* **Interpretabilidad:** El gráfico de importancia de variables muestra que los predictores más influyentes son `Smoking`, `Genetic_Risk`, `Alcohol_Use` y `Air_Pollution`. Esto tiene sentido desde una perspectiva clínica y hace que el comportamiento del modelo sea comprensible.

**Debilidades:**
* **Confusión entre clases:** La matriz de confusión evidencia que el modelo tiene dificultades para distinguir la clase "Media". Una cantidad significativa de casos de severidad media son clasificados erróneamente como "Baja" (1071 casos) o "Alta" (1018 casos).
* **Errores en clases extremas:** Aunque el modelo es bueno para no confundir casos de severidad "Baja" con "Alta" (y viceversa), sí comete errores al clasificar casos de "Baja" como "Media" (1205 casos) y casos de "Alta" como "Media" (1141 casos).

## Conclusiones

El modelo *baseline* de Regresión Logística (SVS) cumple su propósito de establecer una base de rendimiento sólida y ética. Su principal ventaja es que evita el uso de datos personales sensibles, alineándose con un enfoque de IA responsable.

Sin embargo, su rendimiento muestra un área de mejora clara: la clasificación de casos con severidad intermedia. La alta tasa de error en esta categoría sugiere que el modelo lineal podría ser demasiado simple para capturar la complejidad de las interacciones entre las variables.

Posibles áreas de mejora incluyen la experimentación con modelos más complejos (como los basados en ensambles), la aplicación de técnicas de ingeniería de características más avanzadas y el uso de métodos de mitigación de sesgo si se detectaran disparidades en análisis posteriores. La comparación con el modelo CVS (con variables sensibles) permitirá cuantificar el impacto de estas variables en la precisión y la equidad.

## Referencias

- La construcción y evaluación del modelo *baseline* se basaron en el documento "Práctica Profesionalizante II - Proyecto ABP" con las librerías y metodologías descritas en él.
- Documentación de PyCaret: https://pycaret.org/
