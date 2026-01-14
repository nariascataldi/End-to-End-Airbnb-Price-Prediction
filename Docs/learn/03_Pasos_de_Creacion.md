# Pasos para Crear el Proyecto

Si quisieras replicar este proyecto desde cero, estos son los pasos lógicos que se siguieron:

## 1. Configuración del Entorno
- Crear un entorno virtual para aislar las dependencias.
- Crear el archivo `requirements.txt` con las librerías necesarias.
- Configurar el archivo `setup.py` para manejar el proyecto como un paquete.

## 2. Definición de la Estructura (Template)
- Se utiliza un script (`template.py`) para crear todas las carpetas y archivos `__init__.py` necesarios. Esto asegura que Python reconozca los directorios como módulos.

## 3. Análisis Exploratorio de Datos (EDA)
- Utilizar notebooks en la carpeta `Notebook_Experiments` para entender los datos.
- Identificar valores nulos, outliers y la correlación entre variables (como `bedrooms` y `price`).

## 4. Desarrollo de Componentes (Módulos)
- **Ingesta:** Escribir el código para leer los datos y dividirlos.
- **Transformación:** Crear un "Pipeline" de preprocesamiento usando `ColumnTransformer` para manejar variables numéricas (escalado) y categóricas (codificación).
- **Entrenamiento:** Implementar una clase que evalúe múltiples modelos y guarde el mejor rendimiento.

## 5. Creación de Pipelines de Usuario
- Crear un pipeline de entrenamiento que ejecute todos los componentes anteriores en orden.
- Crear un pipeline de predicción que pueda recibir un solo dato nuevo y devolver un precio estimado.

## 6. Interfaz Web (Frontend)
- Diseñar un formulario HTML (`templates/index.html`) para capturar las características de la propiedad.
- Configurar las rutas en `app.py` para recibir los datos del formulario, llamar al pipeline de predicción y mostrar el resultado.

## 7. Contenerización (Docker)
- Crear un `Dockerfile` para asegurar que el proyecto funcione en cualquier sistema sin importar las configuraciones locales de Python.
