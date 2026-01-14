# Guía del Proyecto de Predicción de Precios de Airbnb

Este documento proporciona una guía detallada del proyecto **Airbnb Price Prediction**, explicando su estructura, componentes principales y cómo fluyen los datos desde la entrada inicial hasta la predicción del precio.

## 1. Descripción General del Proyecto
El objetivo de este proyecto es predecir el precio de los anuncios de Airbnb basándose en diversas características como la ubicación, el tipo de propiedad, el tipo de habitación y las comodidades. Utiliza un modelo de aprendizaje automático (CatBoost) entrenado con datos históricos de Airbnb.

## 2. Estructura de Directorios
El proyecto está organizado en componentes modulares para asegurar la escalabilidad y el mantenimiento:

- **`src/Airbnb/`**: Contiene la lógica central de la aplicación.
  - **`components/`**: Scripts modulares para las diferentes etapas del pipeline de ML.
    - `Data_ingestion.py`: Maneja la carga y división de datos (entrenamiento/prueba).
    - `Data_transformation.py`: Realiza la limpieza de datos, ingeniería de características y preprocesamiento.
    - `Model_trainer.py`: Entrena el modelo de aprendizaje automático y lo guarda.
  - **`pipelines/`**: Orquestan la ejecución de los componentes.
    - `Training_Pipeline.py`: Ejecuta el proceso completo de entrenamiento.
    - `Prediction_Pipeline.py`: Maneja las predicciones en tiempo real para la aplicación web.
  - **`utils/`**: Funciones auxiliares para tareas comunes como guardar/cargar objetos.
  - **`logger.py` y `exception.py`**: Registro de logs y manejo de errores personalizados.
- **`Artifacts/`**: Almacena los datos crudos, los conjuntos de datos procesados y los archivos de modelos serializados (`Model.pkl`, `Preprocessor.pkl`).
- **`templates/` y `static/`**: Contienen las plantillas HTML y los archivos CSS/JS para la aplicación web Flask.
- **`app.py`**: El punto de entrada para el servidor web Flask.
- **`setup.py`**: Configuración para instalar el proyecto como un paquete.

## 3. Flujo de Trabajo Principal

### A. Ingesta de Datos (Data Ingestion)
El proceso comienza en `Data_ingestion.py`, donde se carga el conjunto de datos original desde una fuente (ej. archivo CSV) y se divide en conjuntos de entrenamiento y prueba. Estos se guardan en la carpeta `Artifacts/`.

### B. Transformación de Datos (Data Transformation)
En `Data_transformation.py`, los datos pasan por varios pasos de preprocesamiento:
- Manejo de valores faltantes.
- Conversión de características categóricas en formatos numéricos.
- Escalamiento de características numéricas.
- Creación de un objeto `Preprocessor.pkl` que encapsula estos pasos.

### C. Entrenamiento del Modelo (Model Training)
El script `Model_trainer.py` toma los datos transformados y entrena un **CatBoost Regressor** (u otros modelos según la configuración). El modelo con mejor rendimiento se guarda como `Model.pkl` en la carpeta `Artifacts/`.

### D. Predicción (Aplicación Web)
Cuando un usuario envía el formulario en la interfaz web:
1. `app.py` recibe los datos del formulario.
2. `Prediction_Pipeline.py` convierte la entrada en un dataframe.
3. Se carga el archivo `Preprocessor.pkl` para transformar los datos de entrada.
4. Se carga el archivo `Model.pkl` para predecir el precio.
5. El resultado se muestra al usuario en el navegador.

## 4. Cómo Ejecutar
Para ejecutar la aplicación localmente:
1. Instalar dependencias: `pip install -r requirements.txt`
2. Ejecutar la app Flask: `./venv/bin/python app.py`
3. Acceder a la app en `http://localhost:8080` en su navegador.

## 5. Stack Tecnológico
- **Lenguaje**: Python
- **Framework**: Flask
- **Librerías de ML**: Scikit-Learn, CatBoost, XGBoost, Pandas, Numpy
- **Versionamiento de Datos**: DVC (Data Version Control)
- **Contenedores**: Docker
