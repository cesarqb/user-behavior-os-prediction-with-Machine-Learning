# PREDICCIÓN DEL SISTEMA OPERATIVO DE USUARIOS MEDIANTE MACHINE LEARNING

Proyecto completo de Ciencia de Datos para la predicción del sistema operativo (Windows, Macintosh o Linux) de los usuarios de una plataforma digital a partir de su comportamiento de navegación, utilizando técnicas avanzadas de imputación multivariada, ingeniería de características (Feature Engineering, WoE, Box-Cox) y análisis de asociación.

---

## Objetivos del proyecto

* Identificar el sistema operativo utilizado por el usuario para apoyar la personalización de la experiencia de usuario (UX) y la optimización de recursos en la plataforma.
* Analizar el comportamiento digital de los usuarios según sus métricas de interacción, navegación y conversión.
* Identificar los factores de comportamiento y perfil asociados al uso de cada sistema operativo.
* Serializar el modelo entrenado para su posterior despliegue en producción.

---

## Técnicas utilizadas

Durante el desarrollo del proyecto se aplicaron diversas técnicas de Ciencia de Datos y Machine Learning:

### Preparación de datos
* Análisis univariado, bivariado y multivariado.
* Análisis de multicolinealidad mediante matriz de correlación de Pearson.
* Evaluación de asociación no lineal/multiclase
* **Limpieza de datos:** Tratamiento de outliers en variables de interacción.
* **Tratamiento de valores faltantes:** Imputación univariada y multivariada bayesiana basados en predictores correlacionados.
* **Ingeniería de características:** Creación de ratios de comportamiento. Transformaciones especiales (Box-Cox, WoE)
* **Codificación y Escalado:** 
* Balanceo de clases
* Modelos utilizados
  - Logistic Regression
  - Decision Tree Classifier
  - Random Forest Classifier
  - XGBoost Classifier
* Optimización de modelos
* Serialización del modelo (pickle)

---

## Tecnologías utilizadas

Python, Pandas, NumPy, Matplotlib, Seaborn, Scikit-Learn, Imbalanced-Learn (SMOTE), SciPy, Missingno, Pickle, Joblib.

---

## Estructura del proyecto

```text
user-behavior-os-prediction-with-Machine-Learning
│
├── README.md
├── requirements.txt
├── user_behavior_os_prediction.ipynb
│
├── data
│   ├── raw
│   │   └── usuarios_win_mac_lin_exp_cmp.csv
│   │
│   └── processed
│       └── usuarios_processed.csv
│
├── notebooks
│   └── os_prediction_modeling.ipynb
│
├── src
│   ├── eda_evaluation.py
│   ├── preprocessing.py
│   ├── feature_engineering.py
│   ├── balancing.py
│   ├── train_model.py
│   └── evaluation.py
│
├── images
│
├── models
│   └── os_predict_model.pkl
│
├── results
│   ├── metrics.csv
│   └── predictions.csv
│
├── app.py                   # API con FastAPI (Backend)
│
└── streamlit_app.py         # Interfaz de usuario (Frontend)

```
---
## Descripción de carpetas

* data/ → contiene datos originales (vivienda, vivienda_new) y procesados.
* notebooks/ → análisis exploratorio y desarrollo del modelo.
* src/ → funciones reutilizables (preprocesamiento, modelado, evaluación).
* images/ → visualizaciones generadas durante el análisis.
* models/ → modelo entrenado guardado con pickle.
* results/ → predicciones y métricas finales.

---

## Flujo del análisis

El análisis sigue las siguientes etapas:
1. Carga y exploración inicial de datos.
2. Análisis de calidad de datos e identificación de valores nulos y outliers.
3. Tratamiento de valores faltantes (Moda e IterativeImputer).
4. Tratamiento de outliers en acciones con la mediana.
5. Análisis exploratorio de datos (EDA).
6. Ingeniería de características (Creación de ratios de interacción y valor).
7. Transformación Box-Cox para corregir sesgos y cálculo de Weight of Evidence (WoE).
8. Transformación de variables categóricas y codificación mediante One-Hot Encoding.
9. Escalado de variables.
10. Análisis del desbalance de clases y aplicación de técnicas de remuestreo (SMOTE).
11. División del dataset en conjuntos de Entrenamiento y Prueba (Train/Test Split).
12. Entrenamiento de modelos de clasificación multiclase.
13. Optimización de hiperparámetros mediante GridSearchCV.
14. Evaluación comparativa de modelos y análisis de métricas de desempeño.
15. Guardado del modelo entrenado (Serialización).
16. Generación de predicciones para nuevos clientes.

---

## Ejemplo de resultado

Cliente:

- Duración de sesión: 180 segundos
- Páginas visitadas: 12
- Acciones realizadas: 45
- Nivel de usuario: Avanzado
- Navegador: Safari

Resultado del modelo: Probabilidad de uso de Macintosh: 87%
Predicción: CLASE = 1 (Macintosh)

--- 

## Posibles mejoras futuras

- Implementar modelos más avanzados como LightGBM y CatBoost.
- Automatizar el flujo de trabajo con Scikit-learn Pipeline.
- Aplicar técnicas más robustas de selección de variables.
- Desplegar el modelo mediante FastAPI o Streamlit.

---

## 👨‍🏫 Autor

César Quezada
Científico de Datos | Docente Universitario | Mentor



