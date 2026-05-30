# Predicción de Abandono de Clientes (Customer Churn)

Este repositorio contiene un proyecto de análisis de datos y machine learning enfocado en predecir la tasa de abandono (churn) de los clientes de una compañía de telecomunicaciones.

**Autores:** Jordi Rigau, Aniol de Ribot, Oscar Losada.

## 🎯 Objetivos del Proyecto

El objetivo principal es evitar la pérdida de clientes anticipándose a su decisión de abandonar la compañía. Para ello, se analizan los motivos del abandono y se entrenan modelos predictivos para identificar a aquellos clientes con mayor riesgo.

Se estudiaron en profundidad las siguientes dinámicas:
- Relación entre los meses de permanencia (tenure), los costes mensuales y la tendencia de abandono.
- Influencia del método de pago (automático vs. manual/cheque) en la retención.
- El impacto de las características demográficas (edad, tener pareja, dependientes a cargo) en los servicios contratados y la permanencia.

## 📂 Estructura del Repositorio

El proyecto se divide siguiendo buenas prácticas de Data Science:

```
/
├── data/
│   └── processed/                # Conjuntos de datos limpios y divididos en train y test.
├── docs/
│   └── Informe_Final.pdf         # Informe final completo con metodología y conclusiones.
├── notebooks/
│   ├── 01_EDA_and_Analysis/      # Notebooks de Análisis Exploratorio de Datos (EDA).
│   └── 02_Predictive_Models/     # Notebooks de los Modelos Predictivos.
├── README.md                     # Este archivo.
└── requirements.txt              # Dependencias del proyecto.
```

## 🛠 Modelos Utilizados

Para predecir el abandono de los clientes, se probaron y evaluaron tres modelos de clasificación:

1. **Regresión Logística:** Un modelo excelente para interpretar el peso de cada variable en la decisión del cliente. Nos permitió ver que los contratos de dos años y la larga permanencia reducen fuertemente la probabilidad de abandono, mientras que altas cuotas mensuales y fibra óptica suelen estar correlacionadas con un abandono más alto.
2. **K-Nearest Neighbors (KNN):** Tras un estudio detallado de la influencia del número de vecinos ($k$) y reduciendo el subconjunto de características utilizadas, se consiguió un rendimiento robusto para las clases positivas (f1-score ~62%).
3. **Árbol de Decisión:** Modelo muy interpretable. Mediante el ajuste de hiperparámetros como `max_depth`, `min_samples_split` y `max_features` y equilibrando los pesos de las clases, se mejoró significativamente el f1-score respecto al modelo base.

## 📈 Conclusiones Clave

- Los clientes que pagan de forma manual (ej. cheque electrónico) tienen una tasa de abandono significativamente mayor (~50%) frente a los métodos automáticos (~17%).
- La composición familiar (tener pareja e hijos/dependientes) está claramente asociada a una mayor retención.
- Paradójicamente, aunque los usuarios de mayor edad (seniors) tienen más servicios contratados e invierten más dinero, tienen también mayor tendencia al abandono.
- A nivel estratégico, aplicar descuentos o contactar con perfiles específicos clasificados por los modelos puede retener a un gran número de usuarios, incrementando la rentabilidad de la compañía.

## 💻 Instalación y Ejecución

1. Clona el repositorio:
   ```bash
   git clone <tu-url-de-github>
   cd <nombre-del-repo>
   ```
2. Instala las dependencias:
   ```bash
   pip install -r requirements.txt
   ```
3. Ejecuta los Jupyter Notebooks navegando a la carpeta `notebooks/`.
