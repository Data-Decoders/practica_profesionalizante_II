# Diccionario de datos

## Base de datos

Descripción de la tabla o fuente de datos.

| Variable              | Descripción                          | Tipo de dato | Rango/Valores posibles | Fuente de datos |
| --------------------- | ------------------------------------ | ------------ | ---------------------- | --------------- |
| Patient_ID            | Identificador del paciente           | String       | 50000 valores posibles | Kaggle          |
| Age                   | Edad                                 | Integer      | 20 - 89                | Kaggle          |
| Gender                | Género                               | String       | Male - Female - Other  | Kaggle          |
| Country_Region        | País                                 | String       | Diez países distitntos | Kaggle          |
| Year                  | Año de recolección                   | Integer      | 2015 - 2024            | Kaggle          |
| Genetic_Risk          | Riesgo de padecimiento               | Decimal      | 0 - 10                 | Kaggle          |
| Air_Pollution         | Polución del aire                    | Decimal      | 0 - 10                 | Kaggle          |
| Alcohol_Use           | Consumo de alcohol                   | Decimal      | 0 - 10                 | Kaggle          |
| Smoking               | Consumo de tabaco                    | Decimal      | 0 - 10                 | Kaggle          |
| Obesity_Level         | Nivel de obesidad                    | Decimal      | 0 - 10                 | Kaggle          |
| Cancer_Type           | Tipo de cáncer                       | String       | Ocho valores posibles  | Kaggle          |
| Cancer_Stage          | Estado de avance                     | String       | Stage 0 - Stage IV *   | Kaggle          |
| Treatment_Cost_USD    | Costo del tratamiento                | Decimal      | 5k - 100k              | Kaggle          |
| Survival_Years        | Supervivencia desde el diagnóstico   | Decimal      | 0 - 10                 | Kaggle          |
| Target_Severity_Score | Gravedad del caso para cada paciente | Decimal      | 0.9 - 9.16             | Kaggle          |

- **Variable**: nombre de la variable.
- **Descripción**: breve descripción de la variable.
- **Tipo de dato**: tipo de dato que contiene la variable.
- **Rango/Valores posibles**: rango o valores que puede tomar la variable.
- **Fuente de datos**: fuente de los datos de la variable.

---

\* Nomenclatura para el estado de avance del cáncer:

`Cancer_Stage` describe cuán grande es el tumor, si se ha diseminado a ganglios linfáticos cercanos o a otras partes del cuerpo, y se clasifica de la siguiente forma:
- `Stage 0`: Cáncer in situ (muy temprano, no ha invadido tejidos cercanos).
- `Stage I`: Cáncer pequeño, localizado, sin diseminación.
- `Stage II`: Tumor más grande o ha crecido hacia tejidos cercanos.
- `Stage III`: Diseminado a ganglios linfáticos cercanos.
- `Stage IV`: Cáncer avanzado que se ha diseminado a otras partes del cuerpo (metástasis).

