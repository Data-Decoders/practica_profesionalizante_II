# Informe de salida

## Resumen Ejecutivo

Este informe documenta el proceso y los hallazgos del proyecto de práctica profesionalizante II, centrado en el desarrollo de un modelo predictivo para estimar la severidad del cáncer en pacientes de todo el mundo entre 2015 y 2024. Se abordó el análisis exploratorio de datos (EDA), la identificación de variables sensibles y la evaluación de posibles sesgos mediante herramientas de equidad algorítmica como Fairlearn. El trabajo integró dimensiones técnicas y éticas con el objetivo de construir modelos predictivos más justos, robustos y con aplicabilidad clínica. Se trabajó sobre un dataset sintético balanceado y se lograron visualizaciones e interpretaciones valiosas sobre factores de riesgo, costos, supervivencia y desigualdades en salud.

## Resultados del proyecto

- **Entregables y etapas cumplidas:**
  - Limpieza y descripción inicial del dataset.
  - Análisis exploratorio con estadísticas descriptivas, histogramas, boxplots, mapas de calor y gráficos interactivos.
  - Evaluación de correlaciones entre variables numéricas clave.
  - Identificación y análisis de variables sensibles (género, edad, región).
  - Implementación de métricas de equidad (Fairlearn) y visualización de posibles disparidades por grupo.
  - Elección fundamentada de la variable objetivo (`Target_Severity_Score`).

- **Evaluación del modelo y comparación:**
  - Aunque no se construyó un modelo predictivo final en esta etapa, se avanzó en la selección de variables predictoras y objetivo, justificando su relevancia con evidencia estadística y visual.
  - Se detectaron relaciones claras entre factores como tabaquismo o riesgo genético con la severidad del cáncer, que guiarán el modelado futuro.

- **Relevancia para el negocio o aplicación médica:**
  - La predicción de la severidad del cáncer puede apoyar la priorización de tratamientos, distribución de recursos sanitarios y mejora en la toma de decisiones clínicas.
  - Además, el enfoque en equidad garantiza que las herramientas de IA no reproduzcan desigualdades estructurales en el sistema de salud.

## Lecciones aprendidas

- **Principales desafíos:**
  - Comprender la relación entre variables clínicas y sociales sin sesgos implícitos.
  - Identificar cuándo un dataset balanceado artificialmente puede ocultar patrones reales.
  - Dificultades en interpretar correlaciones complejas sin caer en asociaciones espurias.

- **Manejo de datos y modelado:**
  - La estandarización de escalas numéricas facilitó la comparación entre factores de riesgo.
  - Las técnicas visuales fueron esenciales para detectar valores atípicos y validar hipótesis.
  - La necesidad de transformar variables categóricas (como el tipo o etapa del cáncer) fue clave para su futura inclusión en modelos de machine learning.

- **Recomendaciones:**
  - Incluir validación cruzada y particiones del dataset en etapas tempranas.
  - En proyectos futuros, utilizar datos reales complementados con conocimiento clínico.
  - Mantener siempre una revisión ética paralela al pipeline técnico.

## Impacto del proyecto

- **Impacto potencial:**
  - Este proyecto sienta las bases para construir modelos clínicos predictivos sensibles a cuestiones éticas, algo crítico en medicina de precisión.
  - La metodología adoptada puede aplicarse a otros dominios sensibles como seguros de salud o asignación de tratamientos personalizados.

- **Oportunidades futuras:**
  - Implementar modelos de regresión y clasificación usando `Target_Severity_Score`.
  - Incorporar interpretabilidad de modelos (SHAP, LIME).
  - Explorar técnicas de fairness-aware learning en la etapa de modelado.

## Conclusiones

- El proyecto alcanzó sus objetivos en cuanto a exploración, análisis y evaluación de equidad del dataset.
- Se construyó una base sólida de conocimiento para el desarrollo posterior de modelos predictivos.
- Se demostró la importancia de analizar los datos desde una perspectiva técnica y ética simultáneamente.
- Se recomienda continuar el proyecto con foco en el entrenamiento de modelos y su validación en contextos reales.

## Agradecimientos

- Agradecemos al docente **Carlos Charletti** por su acompañamiento pedagógico y orientación técnica.
- Reconocemos el esfuerzo colectivo del equipo de trabajo: **Erick López**, **Christian Nüesch** y **Débora Zurita**, por su compromiso, colaboración y responsabilidad.
