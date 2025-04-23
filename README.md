# **Predicción de Costos Médicos empleando Regresión**

Este proyecto analiza un dataset de seguros médicos obtenido de [Kaggle](https://www.kaggle.com/datasets/mirichoi0218/insurance/data) para predecir costos médicos individuales facturados por seguros de salud. El dataset incluye variables como edad, sexo, IMC, número de hijos o dependientes, estado de fumador, región y costos médicos. El objetivo es construir modelos de regresión que predigan con precisión los costos médicos basados en estas características.

## Estructura del Proyecto
1. **Exploración de datos**:
   - Carga y revisión del dataset.
   - Conversión de variables categóricas a numéricas.
   - Visualización de distribuciones y correlaciones entre variables.
2. **Modelos de Regresión**:
   - **Regresión Lineal**: Modelo base para predecir costos médicos.
   - **Regresión Polinomial**: Modelo mejorado para capturar relaciones no lineales.
3. **Análisis Segmentado**:
   - Modelos separados para fumadores con IMC 15-30 y otros (no fumadores o IMC > 30).
4. **Evaluación**:
   - Comparación del rendimiento de los modelos usando puntuaciones R² y MSE.

## Hallazgos Clave
- **Estado de fumador**: Es el predictor más fuerte de los costos médicos. Los fumadores presentan costos significativamente más altos.
- **Impacto del IMC**: Un IMC alto (>30) combinado con el tabaquismo conduce a los costos médicos más elevados.
- **Modelos Segmentados**:
  - Para fumadores con IMC 15-30, la regresión polinomial de grado 5 proporcionó el mejor ajuste.
  - Para no fumadores o aquellos con IMC > 30, la regresión lineal fue suficiente.

## Resultados
- **Regresión Lineal (Modelo general)**:
  - R² (Entrenamiento): 0.74
  - R² (Prueba): 0.78
- **Modelos Segmentados**:
  - **Fumadores con IMC 15-30 (Regresión Polinomial)**:
    - R² (Entrenamiento): 1.0
    - R² (Prueba): 1.0
  - **No fumadores o IMC 30-55 (Regresión Lineal)**:
    - R² (Entrenamiento): 0.86
    - R² (Prueba): 0.85

## Conclusión
Segmentar los datos en subgrupos (fumadores con IMC 15-30 vs. no fumadores o IMC > 30) y aplicar modelos de regresión personalizados mejoró significativamente la precisión de las predicciones. La regresión polinomial fue especialmente efectiva para fumadores con IMC bajo, mientras que la regresión lineal fue adecuada para otros casos. Este enfoque aborda las limitaciones de un modelo general único.

## Archivos Disponibles
- `medical_cost_regression.ipynb`: Jupyter Notebook con el análisis completo (exploración, modelado y visualización).
- `insurance.csv`: Conjunto de datos en formato CSV.

## Autora
Yamile Montecinos: [@yamilemr](https://github.com/yamilemr)