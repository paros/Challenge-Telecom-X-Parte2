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

TelecomX-ML-Prediction/
│

├── TelecomX_Parte2_DPuebla.ipynb # Notebook principal (ML Pipeline)
├── telecomx_limpio.csv          # Dataset procesado (generado en Parte 1)
├── README.md       # Este archivo
└── papeline_machine_leraning.png   # Diagrama del pipeline ML

## 📊 Preparación de los datos



## 📌 Conclusiones
El análisis permitió identificar variables clave que influyen en la cancelación de clientes.

• Antigüedad del contrato: < 6 meses   
• Tipo Contrato: Mensual        
• Internet: Fibra óptica  
• Pago: Cheque electrónico
• Cargos mensuales: > $70 USD   
• Servicios adicionales: < 2  

El modelo Random Forest mostró un desempeño superior para predecir la cancelación, al capturar relaciones más complejas entre las variables.

## 💡 Recomendaciones para Telecom X
A partir de los resultados obtenidos, se proponen las siguientes estrategias orientadas a reducir la cancelación de clientes y fortalecer la retención:

i) Fomentar la contratación de planes de mayor duración, con el fin de aumentar el compromiso y la permanencia de los clientes.

ii) Implementar programas de fidelización dirigidos a clientes nuevos, especialmente durante los primeros meses de servicio.

iii) Ofrecer beneficios o descuentos a clientes con cargos mensuales elevados, con el objetivo de mejorar la percepción de valor del servicio.


