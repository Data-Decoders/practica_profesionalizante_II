# Project Charter - Entendimiento del Negocio

## Nombre del Proyecto

Predicción y Análisis de Pacientes con Cáncer a Nivel Global utilizando Machine Learning (2015-2024)




## Objetivo del Proyecto

Desarrollar un modelo de aprendizaje automático que prediga la probabilidad de que un paciente reciba un diagnóstico de cáncer metastásico dentro de los 90 días posteriores a un examen de detección. Este enfoque se alinea con investigaciones recientes que utilizan conjuntos de datos oncológicos para mejorar la detección temprana y el tratamiento del cáncer.

Este objetivo permite aplicar técnicas de machine learning supervisado, como árboles de decisión, bosques aleatorios o redes neuronales, y evaluar su rendimiento en un contexto de salud real. Además, fomenta la comprensión de la importancia de la calidad de los datos, la selección de características y la validación de modelos en aplicaciones médicas.​

También se pueden explorar desigualdades en la atención médica, analizar tendencias globales en la incidencia del cáncer y proponer soluciones basadas en datos para mejorar los resultados de los pacientes.




## Alcance del Proyecto

### Incluye:

- Disponemos de los datos relacionados con pacientes de cáncer a nivel mundial durante el periodo 2015-2024. Estos datos incluyen las siguientes variables principales:
    - Tipo de cáncer
    - Edad del paciente
    - Género del paciente
    - País de residencia del paciente
    - Año del diagnóstico
    - Riesgo genético
    - Polución en el aire
    - Uso de alcohol y tabaco
    - Nivel de obesidad
    - Tipo de cáncer
    - Estadío del cáncer al momento del diagnóstico
    - Costo en dólares del tratamiento recibido
    - Años que un paciente ha sobrevivido desde el diagnóstico
    - Gravedad o severidad del cáncer

- Criterios de éxito del proyecto:
	1. **Precisión del modelo**: Evaluar métricas como la precisión, el recall, la puntuación F1 y el área bajo la curva ROC (AUC) para determinar la eficacia del modelo en la clasificación o predicción de casos.​
	2. **Interpretabilidad y explicabilidad**: Asegurar que el modelo sea comprensible para profesionales de la salud, permitiendo una interpretación clara de cómo se toman las decisiones.​
	3. **Calidad y cantidad de datos**: Garantizar que los datos utilizados sean de alta calidad y representativos para entrenar modelos robustos y generalizables.​
	4. **Alineación con objetivos de negocio**: Definir y seguir indicadores clave de rendimiento (KPI) que reflejen los objetivos específicos del proyecto, como la reducción de costos o la mejora en la toma de decisiones clínicas.

### Excluye:

- Lo que no está incluido en el proyecto:
	1. **Diagnóstico clínico real o definitivo**. No se va a usar el modelo como sustituto de una evaluación médica profesional, tiene un propósito académico, no clínico.
	2. **Intervenciones médicas o tratamientos** ya que el proyecto no incluirá recomendaciones sobre quimioterapia, cirugías, medicamentos, etc., eso requiere validación médica y aprobación ética.
	3. **Datos personales identificables**
	4. **Implementación en tiempo real o en producción**. No se implementará un sistema que opere en hospitales o con pacientes reales. Es solo con un propósito académico.
	5. **Uso de modelos black-box sin interpretación**. Aunque se podrán usar modelos complejos (como redes neuronales), se intentará evitar aquellos que no se puedan explicar.
	6. **Generalización a otras enfermedades**. El modelo se va a limitar al dominio del cáncer, no predecir otras patologías para las cuales no se poseen datos ni está entrenado.
	7. **Uso comercial**. No debe hay intención de vender o monetizar el proyecto, a menos que sea parte de una iniciativa avalada por la institución.




## Metodología

Se utilizará la metodología Team Data Science Process (TDSP) para llevar a cabo el proyecto, la cual es una metodología ágil e iterativa desarrollada por Microsoft para proyectos de ciencia de datos. Dicha metodología fue diseñada para mejorar la colaboración en equipos multidisciplinarios, y su objetivo principal es implementar soluciones analíticas predictivas y aplicaciones de IA de manera eficiente.




## Cronograma

| Etapa | Duración Estimada | Fechas |
|------|---------|-------|
| Entendimiento del negocio y carga de datos | 2 semanas | del 1 de mayo al 15 de mayo |
| Preprocesamiento, análisis exploratorio | 4 semanas | del 16 de mayo al 15 de junio |
| Modelamiento y extracción de características | 4 semanas | del 16 de junio al 15 de julio |
| Despliegue | 2 semanas | del 16 de julio al 31 de julio |
| Evaluación y entrega final | 3 semanas | del 1 de agosto al 21 de agosto |

Hay que tener en cuenta que estas fechas son de ejemplo, estas deben ajustarse de acuerdo al proyecto.




## Equipo del Proyecto

- [Nombre y cargo del líder del proyecto]
- [Nombre y cargo de los miembros del equipo]




## Presupuesto

[Descripción del presupuesto asignado al proyecto]




## Stakeholders

- [Nombre y cargo de los stakeholders del proyecto]
- [Descripción de la relación con los stakeholders]
- [Expectativas de los stakeholders]




## Aprobaciones

- [Nombre y cargo del aprobador del proyecto]
- [Firma del aprobador]
- [Fecha de aprobación]
