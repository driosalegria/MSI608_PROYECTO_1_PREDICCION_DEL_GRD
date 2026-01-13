# Early Prediction of Diagnosis-Related Groups (DRG) 🏥

Este repositorio contiene la implementación de un marco de aprendizaje supervisado para la predicción temprana de **Grupos Relacionados por el Diagnóstico (DRG)**, utilizando datos administrativos del Hospital El Pino (Chile). El proyecto busca optimizar la gestión hospitalaria prediciendo la complejidad de los casos desde el momento de la admisión.

👥 Autores
Diego Ríos - d.rosalegra@uandresbello.edu
Marcela Quezada - m.quezadaaraya@uandresbello.edu
Universidad Andrés Bello - Facultad de Ingeniería

## 📂 Estructura del Repositorio

- **`Datasets/`**: 
  - `dataset_elpino.csv`: Dataset original con 14,561 registros.
- **`Imagenes Graficos/`**: 
  - Visualizaciones de Análisis Exploratorio de Datos (EDA).
  - Gráficos de desempeño (Recall macro vs weighted) para cada escenario.
- **Notebooks**:
  - `Escenarios_Consolidado.ipynb`: Flujo completo integrado (Recomendado para revisión).
  - `Escenario_A.ipynb`, `Escenario_B.ipynb`, `Escenario_C.ipynb`: Notebooks experimentales por fase de información.

## 📋 Metodología y Escenarios

El estudio simula la disponibilidad incremental de datos clínicos durante la hospitalización:

* **Escenario A (Admisión):** Predicción basada en edad, sexo y diagnóstico principal.
* **Escenario B (24-48 horas):** Incorpora los primeros 5 diagnósticos secundarios y 3 procedimientos. **(Punto óptimo de decisión identificado).**
* **Escenario C (Alta):** Información completa (20 diagnósticos / 30 procedimientos) para validación técnica.



## 🛠️ Tecnologías Utilizadas

- **Lenguaje:** Python 3.8+
- **Librerías:** - `Pandas` & `Numpy` (Procesamiento)
  - `Scikit-Learn` (Modelamiento: Logistic Regression, Random Forest, MLP)
  - `Matplotlib` & `Seaborn` (Visualización científica)

## 📊 Hallazgos Clave del EDA

Durante el Análisis Exploratorio se identificaron características críticas que influyeron en el modelo:
- **Correctitud:** Limpieza de registros sin diagnósticos primarios.
- **Outliers:** Presencia de casos geriátricos de hasta 121 años (mantenidos por relevancia clínica).
- **Desbalance:** Se detectó una distribución de "cola larga" en los DRG, lo que justifica el uso de métricas pesadas (Weighted F1/Recall).



## 🚀 Instalación y Uso

1. Clonar el repositorio:
```bash
git clone [https://github.com/tu-usuario/nombre-del-repo.git](https://github.com/tu-usuario/nombre-del-repo.git)

2. Instalar dependencias:
```bash
pip install pandas numpy scikit-learn matplotlib seaborn

3. Ejecutar el análisis: Abrir Escenarios_Consolidado.ipynb en Jupyter Notebook o VS Code para reproducir los resultados y gráficas.
