> **⚠️ Aviso sobre la autoría y origen del repositorio**
>
> Este repositorio actúa como una **copia pública** (mirror/snapshot) de un repositorio originalmente privado, desarrollado con fines académicos. Este proyecto es el resultado de un esfuerzo conjunto y **no es un trabajo de autoría exclusivamente individual**. Todos los créditos de desarrollo corresponden a los miembros del **Grupo 18** listados a continuación.

---

# 📉 Predicción de Rotación de Empleados (Attrition) - Grupo 18

Este proyecto de Machine Learning tiene como objetivo predecir la fuga o rotación de empleados (**Attrition**) dentro de una organización. A través del análisis de datos históricos de empleados, se entrenaron y evaluaron diversos modelos de clasificación para identificar patrones clave y generar predicciones sobre nuevos datos.

## 👥 Autores (Grupo 18)
* **Hugo Cuevas Romera** [100495962]
* **Pablo Lorenzo Martín** [100495954]

## 📂 Estructura del Repositorio

El proyecto se divide en dos fases principales (Análisis/Entrenamiento y Predicción) y contiene los siguientes archivos:

* **`01_EDA_Modelado_Grupo18.ipynb`**: Notebook principal que contiene:
    * **EDA (Exploratory Data Analysis):** Análisis exploratorio de las variables (distribuciones, correlaciones, valores nulos).
    * **Preprocesamiento:** Limpieza de datos, imputación de valores faltantes, codificación de variables categóricas y escalado.
    * **Modelado:** Entrenamiento y validación cruzada de múltiples algoritmos (KNN, Regresión Logística, SVM, Árboles de Decisión, Random Forest).
    * **Selección:** Comparación de métricas y exportación del modelo final.
* **`02_Prediccion_Grupo18.ipynb`**: Notebook encargado de la fase de producción:
    * Carga el modelo entrenado (`modelo_final.pkl`).
    * Procesa los nuevos datos de competición (`attrition_competition_08.csv.gz`).
    * Genera y exporta las predicciones finales.
* **`modelo_final_Grupo18.pkl`**: Archivo binario que contiene el pipeline del modelo final entrenado y serializado para su uso posterior.
* **`predicciones_Grupo18.csv`**: Archivo CSV con los resultados de las predicciones (etiquetas `Yes`/`No`) generadas por el modelo sobre el conjunto de test.

## ⚙️ Metodología

### 1. Preprocesamiento de Datos
Se implementó un `Pipeline` de Scikit-Learn para automatizar la transformación de datos:
* **Imputación:** Manejo de valores nulos utilizando estrategias como la mediana (`SimpleImputer`).
* **Escalado:** Uso de `RobustScaler` para normalizar las variables numéricas y mitigar el efecto de los valores atípicos (outliers).
* **Codificación:** Transformación de variables categóricas (como `Department`, `BusinessTravel`) para su uso en los modelos.

### 2. Modelos Evaluados
Se probaron y ajustaron diversos algoritmos de clasificación supervisada, incluyendo:
* K-Nearest Neighbors (KNN)
* Regresión Logística
* Support Vector Machines (SVM)
* Árboles de Decisión (Decision Tree)
* Random Forest

### 3. Selección del Modelo
Tras comparar las métricas de rendimiento (precisión, recall, score balanceado) y el coste computacional, se seleccionó el modelo que ofrecía el mejor equilibrio entre capacidad predictiva y eficiencia.

## 🚀 Instrucciones de Uso

### Requisitos Previos
Asegúrate de tener instaladas las siguientes librerías de Python:
```bash
pip install pandas numpy scikit-learn matplotlib seaborn joblib
´´´ 
## Ejecución

- **Entrenamiento**: Ejecuta el notebook `01_EDA_Modelado_Grupo18.ipynb` para procesar los datos de entrenamiento, visualizar el análisis y generar el archivo `modelo_final.pkl`.

- **Predicción**: Ejecuta el notebook `02_Prediccion_Grupo18.ipynb`. Este script cargará automáticamente el modelo `.pkl` y generará el archivo `predicciones_Grupo18.csv` con los resultados.

## 📊 Datos Utilizados

El dataset incluye variables de recursos humanos como:

- **Demográficas**: Age, Over18, DistanceFromHome.
- **Laborales**: Department, JobRole, JobLevel, YearsAtCompany.
- **Satisfacción**: JobSatisfaction, EnvironmentSatisfaction, WorkLifeBalance.
- **Métricas de Desempeño**: PerformanceRating, PercentSalaryHike.
