# ProyectoFinal-DataScience

# Predicción de Retrasos en Vuelos Domésticos en EE. UU.

## Problema a Resolver

El proyecto busca mejorar la experiencia del cliente en una plataforma de reservación de vuelos, anticipando si un vuelo será retrasado debido al clima. La solución consiste en desarrollar un modelo de machine learning que, con base en los datos disponibles antes del vuelo, prediga si el mismo sufrirá un retraso al salir o llegar a los aeropuertos más transitados de EE. UU.

---

## Dataset Utilizado

El dataset proviene del curso de AWS Academy’s Machine Learning Foundations. Contiene información sobre vuelos operados por aerolíneas comerciales de EE. UU. entre 2013 y 2018, reportados al Bureau of Transportation Statistics (BTS). Incluye:

- Fecha y hora del vuelo
- Origen y destino
- Aerolínea
- Distancia
- Estado de retraso

---

## Modelo Final y Proceso

### Proceso de Modelado

1. Se construyó un modelo **baseline** con todas las variables disponibles tras preprocesamiento, sin selección previa ni regularización. Este modelo obtuvo las mejores métricas de las primeras 3 iteraciones.
2. Se desarrollaron 3 **iteraciones** adicionales aplicando técnicas de *feature selection* (IV, coeficientes, WoE), reduciendo el conjunto de variables.
3. Finalmente, se implementó una **cuarta iteración extra** usando un modelo de **RandomForestClassifier**, el cual logró superar al baseline en desempeño.

---

### Modelo Final: Random Forest

- **Modelo:** `RandomForestClassifier` de `sklearn`
- **Target:** `is_delay` (0: no retrasado, 1: retrasado)
- **Clases:** Binaria
- **Tratamiento de features:**
  - Variables categóricas codificadas con `pd.get_dummies()`
  - Oversampling aplicado para balancear clases
- **Variables utilizadas:** Todas las variables relevantes tras codificación (fecha, tiempo, distancia, origen, destino, aerolínea)
  
---

### Métricas del modelo final (Random Forest)

| Métrica    | Valor aproximado |
|------------|------------------|
| Accuracy   | 🟩 Mayor al Modelo Baseline |
| Precision  | 🟩 Mayor al Modelo Baseline |
| Recall     | 🟩 Mayor al Modelo Baseline |
| KS         | 🟩 Mayor al Modelo Baseline |

