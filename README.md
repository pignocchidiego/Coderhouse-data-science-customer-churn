# Predicción de Customer Churn | Machine Learning con Python

**Proyecto Final – Data Science | Coderhouse**

## 1. Descripción del proyecto

Este proyecto desarrolla un modelo de Machine Learning para predecir el abandono de clientes (*Customer Churn*) en una empresa de telecomunicaciones.

El objetivo es identificar clientes con mayor probabilidad de cancelar sus servicios y proporcionar información que permita diseñar estrategias de retención.

Se implementó un flujo de Ciencia de Datos que incluye análisis exploratorio, limpieza de datos, preprocesamiento, entrenamiento, optimización y evaluación de modelos predictivos.

## 2. Objetivos

- Analizar los factores asociados al abandono de clientes.
- Identificar patrones en las características demográficas, contractuales y de facturación.
- Preparar los datos para algoritmos de clasificación supervisada.
- Entrenar y comparar modelos de Regresión Logística y Random Forest.
- Optimizar hiperparámetros mediante GridSearchCV.
- Seleccionar el modelo más adecuado según las métricas y el objetivo de negocio.

## 3. Dataset

**Fuente:** IBM Telco Customer Churn, disponible públicamente en Kaggle.

El conjunto de datos original contiene:

- **7.043 clientes**
- **21 variables**
- **Variable objetivo:** `Churn` (`Yes` / `No`)

Las variables incluyen antigüedad del cliente, tipo de contrato, servicios contratados, métodos de pago, cargos mensuales y gastos acumulados.

Durante la limpieza se eliminaron 11 registros con valores faltantes en `TotalCharges`, obteniendo **7.032 registros válidos**.

## 4. Tecnologías utilizadas

- **Python:** lenguaje de programación.
- **Pandas y NumPy:** manipulación y análisis de datos.
- **Matplotlib y Seaborn:** visualización de información.
- **Scikit-learn:** preprocesamiento, entrenamiento y evaluación de modelos.
- **Google Colab:** entorno de desarrollo.
- **GitHub:** documentación y publicación del proyecto.

## 5. Metodología

### Análisis exploratorio (EDA)

Se analizaron las distribuciones de la variable objetivo y su relación con el tipo de contrato, servicio de Internet, método de pago, antigüedad y cargos mensuales.

También se realizaron histogramas, boxplots y una matriz de correlación.

### Limpieza y preprocesamiento

- Conversión de `TotalCharges` a formato numérico.
- Tratamiento de valores faltantes.
- Eliminación de `customerID` de las variables predictoras.
- Separación de variables predictoras y variable objetivo.
- División de datos en entrenamiento (80 %) y prueba (20 %), con estratificación.
- Estandarización de variables numéricas mediante `StandardScaler`.
- Codificación de variables categóricas mediante `OneHotEncoder`.
- Integración del preprocesamiento y los modelos mediante `Pipeline` y `ColumnTransformer`.

### Modelado predictivo

Se evaluaron tres configuraciones:

1. **Regresión Logística:** modelo de referencia (*baseline*).
2. **Random Forest:** modelo basado en árboles de decisión.
3. **Random Forest optimizado:** búsqueda de hiperparámetros mediante `GridSearchCV`.

## 6. Resultados

| Métrica | Regresión Logística | Random Forest inicial |
|---|---:|---:|
| Accuracy | 80,38 % | 78,75 % |
| Precision | 64,85 % | 63,07 % |
| Recall | 57,22 % | 48,40 % |
| F1-score | 0,6080 | 0,5477 |
| ROC-AUC | 0,8359 | 0,8137 |

La optimización mediante GridSearchCV mejoró el desempeño de Random Forest respecto de su configuración inicial, pero no logró superar a la Regresión Logística.

**Modelo seleccionado: Regresión Logística.**

Este modelo presentó el mejor rendimiento general entre las configuraciones evaluadas, además de ofrecer ventajas de simplicidad e interpretabilidad.

## 7. Principales hallazgos

El análisis identificó factores asociados al abandono de clientes:

- **Antigüedad:** los clientes con menor permanencia presentan mayor riesgo de abandono.
- **Tipo de contrato:** los contratos mensuales se asocian con mayores cancelaciones.
- **Facturación:** los cargos mensuales y los gastos acumulados aportan información relevante.
- **Servicio de Internet:** la fibra óptica aparece asociada a mayores niveles de abandono en el conjunto analizado.
- **Método de pago:** el pago mediante `Electronic check` presenta una asociación relevante con el abandono.
- **Servicios adicionales:** la ausencia de soporte técnico y seguridad en línea también aparece entre las variables relevantes.

Estas relaciones son asociaciones observadas en el dataset y no demuestran causalidad.

## 8. Conclusiones

El proyecto permitió desarrollar y evaluar modelos de clasificación binaria aplicados a un problema de negocio.

La Regresión Logística obtuvo un **ROC-AUC de 0,8359**, mostrando una buena capacidad de discriminación entre clientes que permanecen y clientes que abandonan la empresa.

Sin embargo, su Recall del **57,22 %** indica que todavía existe margen para mejorar la detección de clientes que efectivamente cancelan el servicio.

Los resultados muestran cómo Machine Learning puede contribuir a la identificación de clientes en riesgo y apoyar decisiones comerciales orientadas a la retención.

## 9. Posibles mejoras

- Evaluar algoritmos adicionales como XGBoost, LightGBM y CatBoost.
- Explorar técnicas de balanceo como SMOTE.
- Ajustar el umbral de clasificación según el costo de los falsos negativos.
- Incorporar nuevas variables de comportamiento.
- Utilizar técnicas de interpretabilidad como SHAP.
- Validar el desempeño con datos más recientes y representativos.

## 10. Estructura del repositorio

```text
Coderhouse-data-science-customer-churn/
├── data/
│   └── raw/
│       ├── README.md
│       └── WA_Fn-UseC_-Telco-Customer-Churn.csv
├── notebooks/
│   ├── README.md
│   └── Proyecto_Final_Customer_Churn_GitHub.ipynb
├── docs/
│   ├── README.md
│   └── Proyecto Final_Coderhouse_DiegoPignocchi.pdf
├── README.md
└── LICENSE
```

## 11. Archivos principales

- [Dataset original](data/raw/)
- [Notebook de Machine Learning](notebooks/Proyecto_Final_Customer_Churn_GitHub.ipynb)

## 12. Autor

**Diego Pignocchi**

Proyecto académico desarrollado como trabajo final de Data Science en Coderhouse.
