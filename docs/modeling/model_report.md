# Reporte del Modelo Final

## Resumen Ejecutivo

Este reporte detalla el desarrollo y la evaluación de un modelo de clasificación para predecir la severidad del cáncer. El modelo final seleccionado es un clasificador de **Regresión Logística**, entrenado intencionalmente sin utilizar variables sensibles (enfoque SVS) para garantizar un pronóstico ético y justo.

El modelo alcanzó una **precisión (Accuracy) general del 70.34%** y un **AUC de 0.8805**, lo que indica una capacidad predictiva útil y una excelente habilidad para discriminar entre las diferentes clases de severidad. Sin embargo, un análisis más profundo revela que, si bien el modelo es robusto identificando casos de severidad "Baja" y "Alta", su principal debilidad es la clasificación de casos de severidad "Media", donde presenta una tasa de error considerable. Los factores más influyentes en sus predicciones son el tabaquismo (`Smoking`) y el riesgo genético (`Genetic_Risk`). El modelo final representa una base sólida que prioriza la equidad, con un rendimiento cuantificado que sirve como punto de partida para futuras mejoras.

## Descripción del Problema

El problema central que se buscó resolver fue el desarrollo de un modelo capaz de predecir la severidad del cáncer en un paciente, clasificada en niveles "Bajo", "Medio" o "Alto". Este proyecto se enmarca en un contexto donde los datos de salud pueden contener sesgos históricos y estructurales que afectan a distintos grupos demográficos.

Los objetivos principales fueron:
* Crear un modelo predictivo que pudiera servir como herramienta de apoyo para decisiones médicas y priorización de intervenciones.
* Entender la estructura y calidad de un conjunto de datos de pacientes con cáncer, identificando variables sensibles y predictoras.
* Identificar y analizar la influencia de variables sensibles (género, edad, región) para desarrollar un modelo ético y responsable.
* Garantizar que el modelo final no perpetuara desigualdades ni tomara decisiones discriminatorias, utilizando herramientas como Fairlearn para la auditoría de sesgos.

La justificación del modelo radica en la necesidad de contar con herramientas de pronóstico que no solo sean precisas, sino también justas, asegurando que las predicciones no estén influenciadas por factores demográficos protegidos.

## Descripción del Modelo

El modelo final es un clasificador de **Regresión Logística**. Fue seleccionado automáticamente como el de mejor rendimiento entre varios algoritmos evaluados por la función `compare_models()` de PyCaret. La decisión de designar este modelo como "final" se basa en su buen rendimiento dentro del enfoque SVS (Sin Variables Sensibles), que excluye explícitamente los datos de `Age`, `Gender` y `Country_Region` del entrenamiento para mitigar riesgos de sesgo y discriminación.

La metodología empleada para llegar a este modelo fue la siguiente:
1.  **Análisis Exploratorio y Ético:** Se realizó un análisis exhaustivo para comprender las variables y sus correlaciones. Se aplicaron pruebas estadísticas como Chi-Cuadrado para confirmar que la severidad del cáncer no tenía una asociación estadísticamente significativa con las variables sensibles en el dataset.
2.  **Preprocesamiento de Datos:** Se eliminaron 151 registros (0.3% del total) identificados como valores atípicos. La variable objetivo `Target_Severity_Score` se transformó en una variable categórica `Target_Severity_Level` para el análisis de clasificación. Las variables categóricas como `Cancer_Type` fueron codificadas mediante *One-Hot Encoding*.
3.  **Entrenamiento y Trazabilidad:** Se utilizó PyCaret para configurar el entorno de experimentación y entrenar diferentes modelos. Todo el proceso, incluyendo hiperparámetros, métricas y artefactos, fue registrado y versionado con MLflow para asegurar la trazabilidad y reproducibilidad.

## Evaluación del Modelo

La evaluación del modelo de Regresión Logística (SVS) se realizó utilizando un conjunto de métricas estándar de clasificación, complementadas con un análisis detallado de la matriz de confusión.

A continuación se presentan los resultados obtenidos:

| Métrica | Valor | Interpretación |
| :--- | :--- | :--- |
| **Accuracy** | 0.7034 | El modelo clasifica correctamente el 70.34% de todos los casos. |
| **AUC** | 0.8805 | Valor muy bueno. Indica una excelente capacidad del modelo para distinguir entre las clases de severidad. |
| **Recall** | 0.7034 | En promedio, el modelo identifica correctamente el 70.34% de los casos positivos para cada clase. |
| **Precision** | 0.7074 | Cuando el modelo predice una clase, acierta el 70.74% de las veces. |
| **F1-Score** | 0.7052 | Puntuación que balancea Precision y Recall. Un valor de 0.7052 indica un rendimiento aceptable. |
| **Kappa** | 0.5552 | Métrica que mide la concordancia. Un valor de 0.55 indica una concordancia moderada. |
| **MCC** | 0.5553 | Coeficiente de correlación robusto para clasificación. Un valor de 0.55 indica una calidad de predicción moderada. |

Además de las métricas agregadas, se presenta la **matriz de confusión** para un análisis más granular de los errores por clase:

| Clase Verdadera | Predicción: Baja (0) | Predicción: Media (1) | Predicción: Alta (2) |
| :--- | :--- | :--- | :--- |
| **Baja (0)** | 3813 | 1205 | 0 |
| **Media (1)**| 1071 | 2893 | 1018 |
| **Alta (2)** | 0 | 1141 | 3814 |

### Interpretación detallada de los resultados
* Las métricas generales como **Accuracy (70.34%)** y **F1-Score (70.52%)** sugieren un rendimiento general moderado pero útil. El **AUC (0.8805)** es el punto más fuerte, indicando que el modelo es muy bueno diferenciando entre un caso de severidad alta y uno de severidad baja.
* Sin embargo, estas métricas globales ocultan la principal debilidad del modelo: el **rendimiento desigual entre las clases**. La matriz de confusión muestra claramente que el modelo tiene serias dificultades con la clase **"Media"**. Casi la mitad de los casos de esta categoría son clasificados incorrectamente como "Baja" o "Alta".
* El modelo es muy fiable al no confundir los extremos: **ningún caso de severidad "Baja" fue clasificado como "Alta" y viceversa**. Esto es crucial en un contexto clínico, ya que evita los errores más graves de pronóstico.
* La importancia de variables confirma que la exclusión de datos sensibles no impidió que el modelo aprendiera patrones lógicos, basando sus predicciones en factores de riesgo clínicamente relevantes como el tabaquismo y la genética.

## Conclusiones

El modelo de Regresión Logística cumple el objetivo principal de ser una herramienta de pronóstico ética, al demostrar una capacidad predictiva útil sin depender de variables demográficas sensibles. Con una precisión general del 70.34% y un AUC de 0.88, el modelo es un punto de partida validado y robusto.

Su principal limitación es la dificultad para discernir con precisión los casos de severidad "Media", donde la tasa de error es considerablemente alta. Esta debilidad sugiere que un modelo lineal simple puede no ser suficiente para capturar las complejas interacciones entre los factores de riesgo que definen un pronóstico intermedio.

Para futuras iteraciones, se recomienda explorar las siguientes áreas de mejora:
1.  **Técnicas de modelado avanzadas:** Experimentar con algoritmos no lineales (ej. Gradient Boosting, Random Forest) que podrían capturar mejor las relaciones complejas en los datos.
2.  **Clasificación ordinal:** Utilizar modelos diseñados específicamente para problemas de clasificación ordinal ya que las clases de severidad ("Baja", "Media", "Alta") tienen un orden inherente.
3.  **Creación de variables de interacción:** Investigar la creación de variables de interacción entre los predictores más importantes (`Smoking`, `Genetic_Risk`, etc.) para potencialmente mejorar la separación entre clases.

En definitiva el modelo final es un éxito como *baseline* ético, proporcionando una base medible y transparente sobre la cual construir soluciones más sofisticadas.

## Referencias

- Documentación de PyCaret: https://pycaret.org/
- Documentación MLflow: https://mlflow.org/
