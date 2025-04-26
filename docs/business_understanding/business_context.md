# Justificación de la elección del problema

## Impacto social
El cáncer es una de las principales causas de muerte a nivel mundial. Desarrollar un modelo que ayude a predecir la severidad o la probabilidad de supervivencia puede asistir a sistemas de salud en priorizar tratamientos, personalizar terapias y optimizar recursos. Además, incluir el análisis de equidad garantiza que estos modelos no reproduzcan sesgos que podrían perjudicar a poblaciones vulnerables.

## Relevancia
El dataset abarca datos de múltiples regiones, tipos de cáncer y factores de riesgo, lo que lo hace representativo y aplicable a un amplio espectro de escenarios médicos reales. Además, incluye características sensibles como género, región y factores socioambientales, lo que lo hace ideal para aplicar herramientas como Fairlearn y analizar equidad en los resultados.

## Factibilidad
El dataset está estructurado, incluye variables numéricas y categóricas, y permite tanto tareas de clasificación como regresión (ej.: predicción de supervivencia, costo de tratamiento, severidad). Además, está diseñado para uso académico, por lo tanto es adecuado para exploración, modelado y evaluación de equidad. Herramientas como Scikit-learn, MLflow y Fairlearn pueden aplicarse sin restricciones técnicas.

---

# Preguntas de negocio

A partir del contexto del dataset, se pueden definir varias preguntas relevantes, con énfasis en equidad, impacto y modelado:

## ¿Existen diferencias en la predicción de supervivencia según el género del paciente?
- **Enfoque:** Modelo de regresión o clasificación + evaluación de equidad con Fairlearn.
- **Justificación:** Asegurar que todos los géneros reciban predicciones precisas y equitativas.

## ¿Es el modelo de predicción de severidad del cáncer justo entre diferentes regiones geográficas o países?
- **Enfoque:** Clasificación de severidad (baja, media, alta) + fairness regional.
- **Justificación:** Identificar y visibilizar desigualdades en los sistemas de salud globales.

## ¿Los pacientes con factores de riesgo asociados al estilo de vida (alcohol, tabaco, obesidad) reciben un tratamiento más costoso?
- **Enfoque:** Análisis de correlaciones + modelo de predicción de costo.
- **Justificación:** Evaluar si los costos de tratamiento reflejan sesgos o decisiones clínicas objetivas.

## ¿El costo estimado del tratamiento predicho por el modelo es equitativo entre géneros?
- **Enfoque:** Modelo de regresión + evaluación de fairness.
- **Justificación:** Evitar sesgos de género en la predicción de costos médicos.
