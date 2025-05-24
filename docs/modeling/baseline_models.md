# Reporte del Modelo Baseline

Este documento contiene los resultados del modelo baseline.

## Descripción del modelo

El modelo baseline utilizado es el **Dummy Regressor**. Este modelo predice el valor medio de la variable objetivo para todos los ejemplos, y se utiliza como punto de referencia para evaluar el rendimiento de modelos más complejos.

## Variables de entrada

- Age
- Gender
- Country_Region
- Year
- Genetic_Risk
- Air_Pollution
- Alcohol_Use
- Smoking
- Obesity_Level
- Cancer_Type
- Cancer_Stage
- Treatment_Cost_USD
- Survival_Years

## Variable objetivo

- Target_Severity_Score

## Evaluación del modelo

### Métricas de evaluación

Se utilizaron las siguientes métricas para evaluar el rendimiento del modelo baseline:
- MAE (Mean Absolute Error)
- MSE (Mean Squared Error)
- RMSE (Root Mean Squared Error)
- R2 (Coeficiente de determinación)
- RMSLE (Root Mean Squared Log Error)
- MAPE (Mean Absolute Percentage Error)

### Resultados de evaluación

| Modelo         | MAE    | MSE     | RMSE   | R2      | RMSLE  | MAPE   | TT (Sec) |
|----------------|--------|---------|--------|---------|--------|--------|----------|
| Dummy Regressor| 0.9690 | 1.4463  | 1.2025 | -0.0003 | 0.2140 | 0.2246 | 0.7790   |

## Análisis de los resultados

El modelo Dummy Regressor presenta un desempeño pobre, como se espera para un modelo baseline que no utiliza información de las variables de entrada. Sus métricas de error son altas y el valor de R2 es cercano a cero o negativo, lo que indica que no explica la variabilidad de la variable objetivo.

## Conclusiones

El modelo baseline establece un punto de referencia mínimo de rendimiento. Cualquier modelo que supere este baseline puede considerarse útil para el problema. En este caso, se buscaron modelos más avanzados que mejoren sustancialmente las métricas respecto a este baseline.

## Referencias

- Documentación de PyCaret: https://pycaret.org/
- Scikit-learn DummyRegressor: https://scikit-learn.org/stable/modules/generated/sklearn.dummy.DummyRegressor.html
