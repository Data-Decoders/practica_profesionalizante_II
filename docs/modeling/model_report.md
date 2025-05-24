# Reporte del Modelo Final

## Resumen Ejecutivo

El modelo final seleccionado fue **Ridge Regression**, el cual presentó el mejor desempeño en la predicción de la severidad del cáncer, medida por la variable `Target_Severity_Score`. Este modelo alcanzó un MAE de 0.0069, MSE de 0.0001, RMSE de 0.0085 y un R2 de 0.9999, superando ampliamente al modelo baseline. Los resultados sugieren que el modelo es capaz de predecir con gran precisión la severidad del cáncer en los pacientes del dataset analizado.

## Descripción del Problema

El objetivo del proyecto es construir un modelo de machine learning capaz de predecir la severidad del cáncer (`Target_Severity_Score`) en pacientes, utilizando información demográfica, clínica y de estilo de vida. Este problema es relevante para anticipar la evolución de la enfermedad y apoyar la toma de decisiones médicas.

## Descripción del Modelo

El modelo final es una **Ridge Regression**, una variante de la regresión lineal que incluye regularización L2 para evitar el sobreajuste, especialmente útil cuando existen variables correlacionadas. Se eligió este modelo por su capacidad de generalizar bien y su bajo error en las métricas evaluadas. El entrenamiento y comparación de modelos se realizó usando PyCaret y el seguimiento de experimentos se gestionó con MLflow para garantizar la trazabilidad y reproducibilidad.

## Evaluación del Modelo

Las métricas obtenidas en la evaluación del modelo Ridge Regression fueron:

| Modelo             | MAE    | MSE     | RMSE   | R2      | RMSLE  | MAPE   | TT (Sec) |
|--------------------|--------|---------|--------|---------|--------|--------|----------|
| Ridge Regression   | 0.0069 | 0.0001  | 0.0085 | 0.9999  | 0.0017 | 0.0016 | 0.7460   |

El valor de R2 cercano a 1 y los bajos valores de MAE, MSE y RMSE indican un altísimo poder predictivo y mínima desviación respecto a los valores reales. El modelo supera ampliamente al baseline y a otros modelos evaluados.

## Conclusiones y Recomendaciones

El modelo Ridge Regression es altamente recomendable para predecir la severidad del cáncer con los datos disponibles. Entre sus fortalezas destacan la precisión y la robustez frente a la multicolinealidad. Como recomendación, se sugiere evaluar el desempeño en nuevos conjuntos de datos y considerar técnicas adicionales de interpretación de modelos para su uso en contextos clínicos.

## Referencias

- Documentación de PyCaret: https://pycaret.org/
- Ridge Regression (Scikit-learn): https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.Ridge.html
- Documentación MLflow: https://mlflow.org/
