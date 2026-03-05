# Challenge-Telecom-X--Parte-2

# Predicción de Cancelación de Clientes (Churn Prediction)

## Descripción del proyecto

Este proyecto tiene como objetivo analizar los factores que influyen en la cancelación de clientes (Churn) y desarrollar modelos de Machine Learning capaces de predecir qué clientes tienen mayor probabilidad de abandonar el servicio.

A partir del análisis exploratorio de datos y la aplicación de modelos de clasificación, se identificaron variables clave relacionadas con la cancelación de clientes y se propusieron estrategias de retención basadas en los resultados obtenidos.

El proyecto compara el rendimiento de dos modelos de Machine Learning:

* Random Forest
* Regresión Logística

El modelo final seleccionado fue **Regresión Logística**, debido a su mejor rendimiento general y mayor interpretabilidad.

---

# Objetivos

* Analizar los factores que influyen en la cancelación de clientes.
* Construir modelos predictivos de churn.
* Comparar el desempeño de diferentes algoritmos.
* Identificar variables clave que afectan la retención.
* Proponer estrategias de negocio basadas en los resultados.

---

# Dataset

El dataset contiene información de clientes de una empresa de telecomunicaciones, incluyendo características como:

* Tiempo de permanencia del cliente (tenure)
* Tipo de contrato
* Servicios contratados
* Cargos mensuales y totales
* Estado de cancelación del cliente (Churn)

La variable objetivo es:

**Churn**

* 1 → Cliente cancela el servicio
* 0 → Cliente permanece en el servicio

---

# Tecnologías utilizadas

Python fue utilizado como lenguaje principal para el análisis y modelado.

Principales librerías:

* pandas
* numpy
* matplotlib
* seaborn
* scikit-learn


Estas herramientas permitieron realizar:

* limpieza de datos
* análisis exploratorio
* transformación de variables
* entrenamiento de modelos
* evaluación de desempeño

---

# Metodología

El proyecto se desarrolló siguiendo las siguientes etapas:

### 1. Limpieza y preparación de datos

* Eliminación de columnas irrelevantes
* Conversión de variables categóricas
* Separación de variables predictoras y variable objetivo

### 2. Análisis Exploratorio de Datos (EDA)

Se analizaron relaciones entre variables y la cancelación mediante:

* distribución de variables
* análisis de correlación
* visualizaciones

### 3. Transformación de variables

Se aplicaron transformaciones para preparar los datos para los modelos:

* One Hot Encoding para variables categóricas
* Escalado de variables numéricas (en regresión logística)

### 4. División del dataset

El dataset se dividió en:

* 70% entrenamiento
* 30% prueba

Utilizando **Stratified Train-Test Split** para mantener la proporción de churn.

### 5. Entrenamiento de modelos

Se entrenaron dos modelos de clasificación:

* Random Forest
* Regresión Logística

La evaluación se realizó usando **validación cruzada estratificada (Stratified K-Fold)**.

### 6. Optimización del threshold

Se utilizó la curva **Precision-Recall** para encontrar el threshold óptimo que maximiza el **F1-score**.

---

# Resultados de los modelos

## Regresión Logística

Accuracy: **0.80**

| Clase    | Precision | Recall | F1-score |
| -------- | --------- | ------ | -------- |
| No Churn | 0.88      | 0.85   | 0.86     |
| Churn    | 0.62      | 0.69   | 0.65     |

ROC-AUC: **0.85**

---

## Random Forest

Accuracy: **0.75**

| Clase    | Precision | Recall | F1-score |
| -------- | --------- | ------ | -------- |
| No Churn | 0.90      | 0.73   | 0.81     |
| Churn    | 0.51      | 0.78   | 0.62     |

ROC-AUC: **0.83**

---

# Modelo seleccionado

El modelo seleccionado fue **Regresión Logística**, debido a:

* Mayor ROC-AUC
* Mejor equilibrio entre precision y recall
* Mayor interpretabilidad del modelo

La interpretabilidad es especialmente importante en problemas de negocio, ya que permite entender los factores que afectan la cancelación.

---

# Factores principales que influyen en el churn

El análisis permitió identificar varios factores asociados con la cancelación:

### 1. Tiempo de permanencia (Tenure)

Los clientes con menor tiempo en la empresa presentan mayor probabilidad de cancelar el servicio.

### 2. Tipo de contrato

Los contratos mensuales muestran mayor tasa de cancelación que los contratos de largo plazo.

### 3. Cargos totales

Clientes con ciertos patrones de gasto presentan mayor riesgo de churn.

---

# Estrategias de retención propuestas

A partir del análisis se proponen las siguientes estrategias:

### Retención temprana

Implementar programas de seguimiento y beneficios durante los primeros meses del cliente.

### Incentivar contratos de largo plazo

Ofrecer descuentos o beneficios para clientes que contraten planes anuales.

### Segmentación de clientes en riesgo

Utilizar el modelo predictivo para identificar clientes con alta probabilidad de churn y aplicar campañas de retención dirigidas.

### Incrementar percepción de valor

Ofrecer paquetes de servicios adicionales o promociones para aumentar el compromiso del cliente con la empresa.

---

# Estructura del proyecto

```
churn-prediction/
│
├── datos/
│   └── datos_tratados.csv
│
├── notebooks/
│   └── churn_analysis.ipynb
│
├── src/
│   └── modelos.py
│
├── README.md
└── requirements.txt
```

---

# Posibles mejoras futuras

* Optimización de hiperparámetros con GridSearchCV
* Pruebas con modelos adicionales (XGBoost, Gradient Boosting)
* Implementación de un dashboard interactivo
* Implementación del modelo en una API
* Desarrollo de un sistema de monitoreo del modelo

