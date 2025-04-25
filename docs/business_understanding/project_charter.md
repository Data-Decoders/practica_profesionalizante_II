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
| Definición del Problema | 2 semanas | del 14 de abril al 25 de abril |
| Análisis Exploratorio (EDA) y Fairlearn | 2 semanas | del 28 de abril al 9 de mayo |
| Preparando los Datos | 2 semanas | del 12 de mayo al 23 de mayo |
| Modelado Inicial y Experimentación con MLflow | 2 semanas | del 26 de mayo al 2 de junio |
| Despliegue del Modelo en Producción | 2 semanas | del 9 de junio al 20 de junio |

Estas fechas pueden ser ajustadas a medida que se desarrolla el proyecto.




## Equipo del Proyecto

- CHARLETTI, Carlos - Project Manager
- LOPEZ Erick - Data Engineer
- NÜESCH, Christian - Data Scientist
- ZURITA, Abigail - Ethical Reviewer
_Quitando el Project Manager, todos somos alumnos e intercambiaremos y complementaremos roles_




## Presupuesto

| Concepto | Costo estimado (USD) | Detalles |
|------|------|------|
| Computación en la nube (opcional) | $100 | En caso de que se use Google Colab Pro, AWS, o Azure para entrenar modelos |
| Herramientas y software | $0 | La mayoría del stack es open-source: Python, Jupyter, Scikit-learn, TensorFlow, etc. |
| Adquisición de datos | $0 | Dataset gratuito en Kaggle |
| Materiales de apoyo (libros, papers) | $50 | Libros, cursos online |
| Asesorías o revisiones externas (opcional) | $100 – $200 | Si se lega a necesitar a algún experto para revisar el modelo o los resultados |
| Infraestructura local (laptop/GPU) | $0 | Como el equipo ya tiene los recursos, este costo se omite |

### Total estimado:

- Con recursos existentes (infraestructura de instituto): $0 – $100
- Con servicios externos o nube intensiva: $100 – $400
- Proyecto más profesional o semicomercial: $500 – $1,000+



## Stakeholders

- Instituto Superior Politécnico de Córdoba - Casa de estudio
- MERCADO, Gladys Laura - Coordinadora de la carrera
- MANZANELLI, Tatiana - Reemplazo de la coordinadora

Las personas que integramos el equipo del proyecto somos alumnos del instituto

Las expectativas de los stakeholders son vincular directamente a los estudiantes con el entorno laboral, fomentando su adaptación a dinámicas profesionales, el trabajo en equipo y la capacidad de comunicación con otros especialistas y clientes.




## Aprobaciones

- [Nombre y cargo del aprobador del proyecto]
- [Firma del aprobador]
- [Fecha de aprobación]
