# Challenge-Telecom-X Parte2
## Predicción de Evasión de Clientes - TelecomX 
Parte 2: Modelado Predictivo y Sistema de Alerta Temprana

Autor: Patricia Aros
Fecha: Marzo 2026

## 📌 Descripción del proyecto
Este proyecto está asociado la segunda fase del análisis de evasión de clientes de Telecom X, enfocándose en la construcción de modelos predictivos de Machine Learning capaces de anticipar qué clientes tienen mayor probabilidad de cancelar sus servicios.

Partiendo del dataset limpio generado en la Parte 1, se implementó un pipeline de ML que incluye:

Preprocesamiento especializado para algoritmos de clasificación
Entrenamiento y evaluación de múltiples modelos
Análisis de interpretabilidad con SHAP values
Generación de recomendaciones estratégicas accionables

## 🎯 Objetivo
Desarrollar un modelo de clasificación que permita identificar clientes con alta probabilidad de cancelación, con el propósito de implementar acciones que reduzcan la tasa de evasión del 26,5%.

## 🛠️ Tecnologías y Librerías
- **Preprocesamiento:** Pandas, NumPy, Scikit-learn
- **Visualización:** Matplotlib, Seaborn, Plotly
- **Modelado:** Random Forest, XGBoost, Logistic Regression
- **Interpretabilidad:** SHAP (SHapley Additive exPlanations)
- **Evaluación:** Scikit-learn Metrics, Confusion Matrix, ROC-AUC

## 🗂️ Estructura del Proyecto

- TelecomX_Parte2_Final.ipynb   # Notebook principal
- telecomx_limpio.csv           # Dataset procesado (generado en Parte 1)
- README.md                     # Este archivo


## 📊 Flujo de trabajo

## Etapa 1 — Preparación de Datos

| Proceso | Técnica aplicada | Objetivo |
|--------|------------------|---------|
| Codificación binaria | `Label Encoding: {'Sí': 1, 'No': 0}` | Convertir variables Sí/No a formato numérico |
| Codificación categórica | One-Hot Encoding (`drop_first=True`) | Transformar variables categóricas como `Tipo_Contrato`, `Metodo_Pago`, etc. |
| Normalización | `StandardScaler (μ=0, σ=1)` | Escalar variables numéricas (`Cargos_Mensuales`, `Cargos_Totales`, `Meses_Contrato`) |
| División de datos | Train (80%) / Test (20%) con `stratify` | Mantener la proporción de la variable objetivo `Evasion_Binaria` |

---

## Etapa 2 — Análisis de Correlación

- Construcción de **matriz de correlación completa** considerando la variable objetivo `Evasion_Binaria`.
- Detección de **multicolinealidad** utilizando un umbral de correlación `> 0.85`.
- Identificación de las **10 variables más correlacionadas con la evasión**.
- Visualización mediante **heatmaps y gráficos de barras** para facilitar la interpretación.

---

## Etapa 3 — Entrenamiento de Modelos

Se entrenaron **tres modelos de clasificación supervisada** para predecir la evasión de clientes.

| Modelo | Tipo |
|------|------|
| Regresión Logística | Lineal |
| Random Forest | Ensemble (Bagging) |
| XGBoost | Ensemble (Boosting) |
---

## Etapa 4 — Evaluación de Modelos

Para evaluar el desempeño de los modelos se calcularon diversas métricas de clasificación:

- ✅ **Accuracy** → Porcentaje total de predicciones correctas del modelo.  
- ✅ **Precision** → De los clientes predichos como evasión, cuántos realmente abandonan.  
- ✅ **Recall** → De todos los clientes que abandonan, cuántos logra detectar el modelo.  
- ✅ **F1-Score** → Media armónica entre *Precision* y *Recall*, útil cuando las clases están desbalanceadas.  
- ✅ **ROC-AUC** → Capacidad del modelo para discriminar entre clientes que evaden y los que permanecen.


## 📌Comparación de los modelos

Los tres modelos tienen capacidad real para distinguir entre clientes que abandonan el servicio y los que permanecen.

En términos generales:
AUC entre 0.80 y 0.90 → modelo muy bueno
AUC > 0.90 → modelo excelente

### 🏆 Comparación entre modelos
Modelo	ROC-AUC	Interpretación
Regresión Logística	0.8431	Mejor capacidad predictiva
XGBoost	0.8414	Muy similar al mejor
Random Forest	0.8277	Buen desempeño pero ligeramente inferior

Conclusión: 
i) Regresión Logística presenta el mayor ROC-AUC, por lo que es el modelo con mejor capacidad para diferenciar clientes que abandonan y los que permanecen.

ii) XGBoost obtiene un rendimiento prácticamente equivalente, lo que sugiere que ambos modelos son adecuados para el problema.

iii) Random Forest también muestra buen desempeño, aunque ligeramente menor que los otros dos modelos.

## 📌 Conclusiones
El análisis permitió identificar variables clave que influyen en la cancelación de clientes.

• Antigüedad del contrato: < 6 meses   
• Tipo Contrato: Mensual        
• Internet: Fibra óptica  
• Pago: Cheque electrónico
• Cargos mensuales: > $70 USD   
• Servicios adicionales: < 2  

El modelo de Regresión Logística mostró un desempeño superior para predecir la cancelación, tiene mejor capacidad para diferenciar clientes que abandonan y los que permanecen.

## 💡 Recomendaciones para Telecom X
A partir de los resultados obtenidos, se proponen las siguientes estrategias orientadas a reducir la cancelación de clientes y fortalecer la retención:

i) Fomentar la contratación de planes de mayor duración, con el fin de aumentar el compromiso y la permanencia de los clientes.

ii) Implementar programas de fidelización dirigidos a clientes nuevos, especialmente durante los primeros meses de servicio.

iii) Ofrecer beneficios o descuentos a clientes con cargos mensuales elevados, con el objetivo de mejorar la percepción de valor del servicio.


