# Análisis de la Lógica del Código

A continuación se detalla la lógica interna de los componentes más importantes.

## 1. Transformación de Datos (`Data_transformation.py`)
La lógica aquí es fundamental para el éxito del modelo. No se puede alimentar un modelo de ML con texto como "Apartment" o "Private Room".
- **Variables Numéricas:** Se rellenan los valores faltantes con la *mediana* y luego se estandarizan (`StandardScaler`).
- **Variables Categóricas:** Se rellenan con la *moda* (lo más frecuente) y se convierten a números usando `OneHotEncoder`.
- **Resultado:** Estos pasos se encapsulan en un objeto llamado **Preprocessor**, que se guarda como un archivo `.pkl` para ser usado exactamente igual durante las predicciones.

## 2. Entrenamiento del Modelo (`Model_trainer.py`)
El código no elige un modelo al azar.
- Evalúa una lista de algoritmos: `Random Forest`, `Decision Tree`, `Gradient Boosting`, `Linear Regression`, `XGBoost`, `CatBoost`, y `AdaBoost`.
- Realiza una búsqueda de hiperparámetros (Tuning) para cada uno.
- Compara el rendimiento (R2 Score) en los datos de prueba.
- **Lógica de Decisión:** Si ningún modelo supera un umbral mínimo (ej. 0.6), el sistema lanza una excepción. Si lo superan, guarda el modelo con el mejor puntaje.

## 3. Pipeline de Predicción (`Prediction_Pipeline.py`)
Cuando un usuario interactúa con la web:
1. La clase `CustomData` captura los inputs (ej. 2 habitaciones, 1 baño, Nueva York).
2. Convierte esos datos en un `DataFrame` de Pandas.
3. El pipeline carga el `model.pkl` y el `proprocessor.pkl` que fueron guardados anteriormente.
4. El preprocesador transforma los datos del usuario.
5. El modelo realiza la predicción sobre esos datos transformados.
6. El resultado se redondea y se envía de vuelta al navegador.

## 4. Manejo de Errores (`exception.py`)
Se utiliza un sistema de excepciones personalizado que captura no solo el mensaje de error, sino también el nombre del archivo y el número de línea exacto donde ocurrió la falla, facilitando enormemente el **debugeo**.

## 5. Logging (`logger.py`)
Cada paso (ingesta, transformación, error) genera una entrada en un archivo `.log`. Esto permite auditar qué pasó durante el entrenamiento o por qué falló una predicción sin tener que estar mirando la consola en tiempo real.
