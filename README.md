
# 📊 Predicción de Riesgo Crediticio con Machine Learning

Este proyecto tiene como objetivo construir un modelo predictivo para clasificar si una persona incumplirá o no el pago de un préstamo, a partir de características demográficas, financieras y crediticias. Se realizó una limpieza completa de los datos, análisis exploratorio (EDA), ingeniería de variables y comparación de modelos supervisados.

---

## 📁 Dataset

- **Fuente:** [Kaggle – Credit Risk Dataset](https://www.kaggle.com/datasets/laotse/credit-risk-dataset)
- **Descripción:** Conjunto de datos que contiene información de personas que han solicitado un préstamo, incluyendo edad, ingresos, historial crediticio, propósito del préstamo, tasa de interés, entre otras variables.

---

## 🎯 Objetivo

Predecir la probabilidad de que un solicitante de préstamo **incumpla con sus pagos**, a partir de sus características, y ayudar así a las instituciones financieras a reducir el riesgo de impago.

---

## ⚙️ Herramientas y Librerías

- Python
- Pandas, NumPy
- Matplotlib, Seaborn
- Scikit-learn
- Plotly (opcional para visualizaciones interactivas)

---

## 🧪 Proceso

### 1. Exploración y limpieza de datos
- Tratamiento de valores nulos (`loan_int_rate`, `person_emp_length`)
- Eliminación de edades no realistas (> 90 años)
- Conversión de variables categóricas a formato adecuado
- Detección y tratamiento de valores atípicos extremos (`person_income`)

### 2. Análisis exploratorio (EDA)
- Visualización de distribuciones, boxplots y relaciones entre variables
- Detección de sesgos, outliers y correlaciones
- Análisis cruzado entre tasas, calificaciones crediticias, ingresos y default

### 3. Ingeniería de variables
- Escalado con `MinMaxScaler` para ingresos y montos con gran variabilidad
- Codificación de variables categóricas con `LabelEncoder` y `OneHotEncoder`
- Selección de variables relevantes según Cramér’s V y correlaciones

### 4. Modelado
- **Modelo 1: Regresión Logística**
  - Ajuste de `class_weight='balanced'`
  - Ajuste de umbral de clasificación (threshold)
- **Modelo 2: Random Forest Classifier**
  - Modelo sin ajuste, usado como baseline no lineal

### 5. Evaluación de modelos
- Métricas: Accuracy, Precision, Recall, F1-score
- Comparación de desempeño
- Conclusiones sobre impacto de cada variable en la predicción

---

## 🧠 Resultados
S
| Modelo                                | Accuracy | Precision | Recall | F1-score |
|--------------------------------------|----------|-----------|--------|----------|
| Regresión Logística (umbral 0.59)    | 0.8089   | 0.6874    | 0.6778 | 0.6091   |
| Random Forest (sin ajuste de umbral) | 0.8828   | 0.8168    | 0.6016 | 0.6929   |

> 🔍 El modelo de **Random Forest** obtuvo mejor F1-score general, pero la **Regresión Logística** ajustada tuvo mejor Recall (más útil si se quiere priorizar detección de incumplimientos).

---

## 📌 Conclusiones

- Las variables más influyentes en el riesgo de impago son: tasa de interés, calificación crediticia, porcentaje del ingreso destinado al préstamo e historial de impagos.
- Los incumplimientos se relacionan fuertemente con ingresos bajos y tasas más altas.
- El desbalance de clases afecta el rendimiento de los modelos, por lo que se aplicó ajuste de pesos y umbral para mejorar la detección de casos positivos.

---

## 🚀 Próximos pasos (posibles mejoras)

- Implementar técnicas de balanceo como SMOTE
- Probar modelos avanzados como XGBoost o LightGBM
- Usar GridSearchCV para ajuste de hiperparámetros
- Desplegar el modelo con una interfaz en Streamlit

---

## 👩‍💻 Autor

**Ximena Castro Vidrio**  
📍 CDMX, México  
🔗 [LinkedIn](https://linkedin.com/in/ximena-castro-vidrio)

---
