# Estructura del Proyecto

Para comprender el código, es fundamental conocer cómo están organizados los archivos. Este proyecto sigue un diseño modular y profesional.

## Directorios Principales

- **`src/`**: Es el corazón del proyecto. Contiene todo el código fuente organizado en módulos.
    - `Airbnb/components/`: Contiene los pasos individuales del pipeline de datos:
        - `Data_ingestion.py`: Maneja la descarga y división de datos (Train/Test).
        - `Data_transformation.py`: Realiza la limpieza, manejo de valores nulos y codificación de variables.
        - `Model_trainer.py`: Entrena diversos modelos y selecciona el mejor basándose en la precisión.
    - `Airbnb/pipelines/`: Orquestadores que conectan los componentes.
        - `Training_pipeline.py`: Ejecuta todo el proceso desde la ingesta hasta el modelo final.
        - `Prediction_Pipeline.py`: Se encarga de convertir los datos del usuario en una predicción.
    - `Airbnb/utils/`: Funciones auxiliares (como guardar y cargar objetos `.pkl`).
    - `exception.py` y `logger.py`: Manejo robusto de errores y registro de eventos.

- **`Artifacts/`**: Aquí se guardan los archivos generados durante la ejecución:
    - El dataset crudo (`data.csv`).
    - Los conjuntos de entrenamiento y prueba (`train.csv`, `test.csv`).
    - El modelo entrenado (`model.pkl`).
    - El objeto de preprocesamiento (`proprocessor.pkl`).

- **`Notebook_Experiments/`**: Contiene archivos Jupyter Notebook (`.ipynb`) donde se realizaron las pruebas iniciales, el Análisis Exploratorio de Datos (EDA) y la validación de modelos antes de pasarlos a código Python limpio.

- **`templates/` y `static/`**: Archivos HTML y CSS para la interfaz web de Flask.

## Archivos Clave en la Raíz

- **`app.py`**: El punto de entrada de la aplicación Flask. Ejecuta el servidor web.
- **`setup.py`**: Configuración para instalar el proyecto como un paquete local.
- **`requirements.txt`**: Lista de todas las librerías necesarias (Pandas, Scikit-learn, Flask, etc.).
- **`Dockerfile`**: Instrucciones para empaquetar la aplicación en un contenedor.
- **`template.py`**: Un script de utilidad inicial para crear automáticamente la estructura de carpetas necesaria.

---
Esta estructura permite que el proyecto sea **escalable**, **mantenible** y fácil de entender para otros desarrolladores.
