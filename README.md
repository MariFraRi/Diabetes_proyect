# 🩺 Estudio de Predictores de Diabetes en la Población Estadounidense 2022
### *Study of Diabetes Predictors in the U.S. Population 2022*

<p align="center">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white"/>
  <img src="https://img.shields.io/badge/Scikit--Learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white"/>
  <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white"/>
  <img src="https://img.shields.io/badge/Matplotlib-11557C?style=for-the-badge&logo=python&logoColor=white"/>
  <img src="https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white"/>
</p>

---

## 📋 Descripción | Description

**ES:**
La diabetes es una de las enfermedades crónicas más prevalentes en Estados Unidos. Este proyecto desarrolla un sistema predictivo capaz de identificar individuos con mayor riesgo de diabetes utilizando datos de salud poblacional de 2022. El reto principal fue construir un modelo robusto frente a un dataset altamente desbalanceado (~13.7% de casos positivos), maximizando la sensibilidad hacia la clase positiva.

*Diabetes is one of the most prevalent chronic diseases in the United States. This project develops a predictive system to identify individuals at higher risk of diabetes using 2022 population health data. The main challenge was building a robust model on a highly imbalanced dataset (~13.7% positive cases), maximizing sensitivity toward the positive class.*

---

## 🎯 Objetivo | Objective

**ES:** Desarrollar un modelo de Machine Learning capaz de predecir la presencia de diabetes en adultos estadounidenses (2022), maximizando la sensibilidad hacia la clase positiva mediante un proceso metodológico completo.

*Develop a Machine Learning model capable of predicting diabetes presence in U.S. adults (2022), maximizing sensitivity toward the positive class through a complete methodological pipeline.*

---

## 📊 Dataset

| Campo | Detalle |
|-------|---------|
| **Fuente** | [Kaggle — Personal Key Indicators of Heart Disease 2022](https://www.kaggle.com/datasets/kamilpytlak/personal-key-indicators-of-heart-disease?select=2022) |
| **Archivo** | heart_2022_no_nans.csv |
| **Registros** | 246.022 |
| **Variables** | 40 (6 numéricas, 34 categóricas) |
| **Variable objetivo** | HadDiabetes (0 = No, 1 = Sí) |
| **Desbalance** | Clase positiva: ~13.7% |

---

## 🔬 Metodología | Methodology

```
1. EDA (Análisis Exploratorio)
   ├── Descripción estadística de variables
   ├── Visualización de distribuciones
   ├── Identificación de correlaciones
   └── Detección de valores atípicos

2. Preprocesamiento
   ├── Codificación de variables categóricas
   ├── Estandarización de variables numéricas
   └── Manejo del desbalance (SMOTE / SMOTENC)

3. Benchmark — Modelos Baseline
   ├── Regresión Logística
   ├── Random Forest estándar
   ├── Gradient Boosting estándar
   └── Variantes con class_weight y SMOTENC

4. ⭐ Modelo Original — HCSE Model
   ├── Gradient Boosting Cost-Sensitive
   ├── Balanced Random Forest
   └── Fusión Probabilística (capa original)

5. Validación Final
   └── Comparación vs. líneas base
```

---

## ⭐ Modelo Original — HCSE Model

**ES:**
Ningún modelo estándar lograba maximizar el recall de la clase positiva de forma satisfactoria. Por ello, se diseñó un **Modelo Híbrido Cost-Sensitive (HCSE)**, inspirado en tres trabajos de investigación (CMBoost, Pes & Lai 2021, Kadkhodaei et al. 2021), pero con una arquitectura completamente original:

- **Módulo 1 — Gradient Boosting Cost-Sensitive:** penaliza más los errores en la clase positiva mediante `sample_weight`.
- **Módulo 2 — Balanced Random Forest:** re-muestrea internamente para balancear clases en cada árbol.
- **Capa de Fusión Probabilística *(contribución original)*:** combina las probabilidades de ambos módulos (`prob_final = (prob_GB + prob_RF) / 2`), mejorando estabilidad y sensibilidad.

> Este modelo **no existe en sklearn ni en imbalanced-learn**. Es una arquitectura diseñada específicamente para datos de salud desbalanceados a gran escala.

*No standard model was able to maximize recall for the positive class satisfactorily. A **Hybrid Cost-Sensitive Ensemble (HCSE) Model** was designed, inspired by three research papers but with a completely original architecture combining Cost-Sensitive Gradient Boosting, Balanced Random Forest, and a novel probabilistic fusion layer.*

---

## 📈 Métricas de Evaluación | Evaluation Metrics

- **Recall** *(métrica principal / main metric)*
- F1-Score
- Accuracy
- ROC–AUC
- Matriz de confusión

---

## 🛠️ Herramientas | Tools

| Herramienta | Uso |
|------------|-----|
| Python | Lenguaje principal |
| Scikit-learn | Modelos de ML y métricas |
| Imbalanced-learn | SMOTE / SMOTENC |
| Pandas / NumPy | Procesamiento de datos |
| Matplotlib / Seaborn | Visualización |
| Jupyter Book | Publicación del proyecto |

---

## ⚠️ Alcance | Scope

**ES:** Este proyecto es una herramienta analítica de apoyo. No reemplaza evaluaciones médicas profesionales.

*This project is an analytical support tool. It does not replace professional medical evaluations.*

---

## 📚 Ver Proyecto Completo | View Full Project

[![Jupyter Book](https://img.shields.io/badge/Jupyter%20Book-Ver%20Proyecto%20Completo-orange?style=for-the-badge&logo=jupyter)](https://marifrari.github.io/Diabetes_proyect)

---

## 👩‍💻 Autora | Author

**Mariana Franco Riatiga**
Estudiante de Ciencia de Datos — Universidad del Norte, Barranquilla, Colombia.

[![GitHub](https://img.shields.io/badge/GitHub-MariFraRi-100000?style=flat-square&logo=github)](https://github.com/MariFraRi)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Mariana%20Franco-0077B5?style=flat-square&logo=linkedin)](https://www.linkedin.com/in/mariana-franco-riatiga-634867314)
