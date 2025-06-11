# Despliegue de modelos

## Infraestructura

- **Nombre del modelo:** `modelo_severidad_cancer_svs.pkl`

- **Plataforma de despliegue:** Render (https://render.com)

- **Requisitos técnicos:**
  - **Lenguaje:** Python 3.10+
  - **Bibliotecas necesarias:**  
    - `streamlit`  
    - `pandas`  
    - `pycaret==3.3.2`  
    - `scikit-learn==1.4.2`  
    - `joblib==1.3.2`  
    - `mlflow==2.16.0`  
    - `requests`
  - **Hardware mínimo:**  
    - 1 CPU virtual  
    - 512 MB de RAM (mínimo sugerido para Render)

- **Requisitos de seguridad:**
  - Se desactivó temporalmente la protección XSRF en Streamlit para garantizar compatibilidad en Render (`--server.enableXsrfProtection=false`)
  - Actualmente sin autenticación o cifrado, dado que se trata de una aplicación de acceso libre para demostración. En producción se recomienda:
    - Autenticación básica o con OAuth2.
    - HTTPS en toda la comunicación.
    - Validación de entrada más estricta.

- **Diagrama de arquitectura:**  
  ![Arquitectura del despliegue](https://i.ibb.co/t9DrM9B/diagrama-arquitectura.png)

## Código de despliegue

- **Archivo principal:** `deploy.py`

- **Rutas de acceso a los archivos:**
  - `deploy.py` (lógica principal de la aplicación Streamlit)
  - `requirements.txt` (lista de dependencias)
  - `modelo_severidad_cancer_svs.pkl` (modelo serializado, cargado desde GitHub o manualmente)
  - `mlruns/` y `mlmlartifacts/` (directorios generados por MLflow en entrenamiento, no requeridos en Render)

- **Variables de entorno:**
  - `$PORT`: Variable asignada automáticamente por Render para definir el puerto del servicio web.
  - *Opcionalmente se pueden definir*:  
    - `MLFLOW_TRACKING_URI` si se desea conexión automática a un servidor MLflow remoto.

## Documentación del despliegue

### Instrucciones de instalación

1. Crear un repositorio en GitHub que contenga:
   - `deploy.py`
   - `requirements.txt`
   - (opcionalmente) `modelo_severidad_cancer_svs.pkl` o un enlace público para su descarga.

2. En la plataforma Render:
   - Ir a “New Web Service”.
   - Vincular el repositorio de GitHub.
   - Seleccionar "Python" como entorno de ejecución.

3. Configurar comandos de construcción e inicio:
   ```bash
   pip install -r requirements.txt
   streamlit run deploy.py --server.port=$PORT --server.enableCORS=true --server.enableXsrfProtection=false
   ```

### Instrucciones de configuración

- Asegurar que el archivo `requirements.txt` incluya versiones compatibles con Colab:
  ```txt
  streamlit
  pandas
  pycaret==3.3.2
  scikit-learn==1.4.2
  joblib==1.3.2
  mlflow==2.16.0
  requests
  ```

- Verificar que el modelo (`.pkl`) esté accesible:
  - Desde un repositorio público en GitHub.
  - Subido manualmente por el usuario.
  - O conectado a un servidor MLflow mediante `ngrok`.

- Validar que los nombres y tipos de las columnas ingresadas coincidan exactamente con el conjunto de entrenamiento.

### Instrucciones de uso

1. Acceder a la URL pública de la app desplegada en Render.
2. Seleccionar el método de carga del modelo:
   - MLflow (requiere URI y selección de experimento/run)
   - GitHub (descarga directa del `.pkl`)
   - Subida manual (arrastrar archivo `.pkl`)

3. Completar el formulario con los datos del paciente:
   - Variables numéricas: Riesgo genético, Tabaquismo, etc.
   - Variables categóricas: Etapa del cáncer y tipo.
   - Se realiza codificación one-hot automáticamente para el tipo de cáncer.

4. Presionar el botón "Predecir severidad".

5. Visualizar la salida como texto: Baja, Media o Alta.

### Instrucciones de mantenimiento

- **Actualización del modelo:**
  - Entrenar un nuevo modelo en Colab y exportar `.pkl` con `save_model()`.
  - Subir el nuevo archivo al repositorio o reemplazar el existente.

- **Actualización de dependencias:**
  - Modificar el archivo `requirements.txt`.
  - Render reconstruye automáticamente el entorno tras cada commit.

- **Pruebas del sistema:**
  - Validar manualmente con distintos inputs desde la interfaz.
  - Verificar logs de Render para detectar errores en producción.

- ## Mejoras futuras recomendadas
  - **Mejorar la interfaz con componentes interactivos**  
  Incorpora componentes de Streamlit como sliders, selectboxes, tablas dinámicas o gráficos interactivos para facilitar la exploración de datos y resultados.
  - **Registrar predicciones y métricas**  
  Guarda las predicciones y datos de entrada en una base de datos o archivo para auditoría, análisis posterior o mejora continua del modelo.
  - **Agregar interpretabilidad de modelos**  
  Integra explicaciones visuales con SHAP o gráficos que ayuden a entender las predicciones, aumentando la confianza del usuario.
  - **Conectar con APIs externas**  
  Permite que tu app consuma o exponga APIs para integrar el modelo en flujos de trabajo más amplios o facilitar despliegues en producción.
  - **Diseñar una experiencia de usuario clara y amigable**  
  Organiza la app con instrucciones, etiquetas claras y diseño intuitivo para que cualquier usuario pueda usarla sin dificultad
