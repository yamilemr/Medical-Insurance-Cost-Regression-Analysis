# **Predicción de Costos Médicos empleando Regresión**

Este proyecto analiza un dataset de seguros médicos obtenido de [Kaggle](https://www.kaggle.com/datasets/mirichoi0218/insurance/data) para predecir costos médicos individuales facturados por seguros de salud. El dataset incluye variables como edad, sexo, IMC, número de hijos o dependientes, estado de fumador, región y costos médicos. El objetivo es construir modelos de regresión que predigan con precisión los costos médicos basados en estas características.

## Estructura del Proyecto
1. **Exploración de datos:**
   - Carga y revisión del dataset.
   - Conversión de variables categóricas a numéricas.
   - Visualización de distribuciones y correlaciones entre variables.
2. **Modelos de Regresión:**
   - **Regresión Lineal:** Modelo base para predecir costos médicos.
   - **Regresión Polinomial:** Modelo mejorado para capturar relaciones no lineales.
3. **Análisis Segmentado:**
   - Dos modelos separados, uno para fumadores con IMC entre 15-30 y otro para el resto de los casos (no fumadores o personas con IMC > 30).
   - Incorporar una variable categórica al dataset original que clasifique los datos en la segmentación mencionada en el punto anterior.
4. **Evaluación:**
   - Comparación del rendimiento de los modelos usando puntuaciones R² y MSE.

## Hallazgos Clave
- **Estado de fumador:** Es el predictor más fuerte de los costos médicos. Los fumadores presentan costos significativamente más altos.
- **Impacto del IMC:** Un IMC alto (>30) combinado con el tabaquismo conduce a los costos médicos más elevados.
- **Modelos Segmentados:**
  - Al haber muy pocos datos para el subgrupo de fumadores con IMC 15-30, se presentó un subajuste tanto con la regresión lineal como con la polinomial.
  - Para no fumadores o aquellos con IMC > 30, la regresión lineal fue suficiente.
- **Agregar la variable *category*:** Mejoró el desempeño del modelo, indicando que es importante la relación entre las variables *smoker* y *bmi*.

## Resultados
- **Usando todos los datos:**
  - **Regresión Lineal:**
    - R² (Entrenamiento): 0.74
    - R² (Prueba): 0.78
  - **Regresión Polinomial:**
    - R² (Entrenamiento): 0.85
    - R² (Prueba): 0.85
- **Agregando la variable *category*:**
  - **Regresión Lineal:**
    - R² (Entrenamiento): 0.85
    - R² (Prueba): 0.88
  - **Regresión Polinomial:**
    - R² (Entrenamiento): 0.87
    - R² (Prueba): 0.87

## Conclusión
Agregar una variable categórica que segmenta los datos en subgrupos (fumadores con IMC 15-30 vs. no fumadores o IMC > 30), fue la mejor estrategia para obtener el mejor modelo. La regresión polinomial fue la que obtuvo los mejores resultados, indicando que hay patrones no lineales en los datos.

## Archivos Disponibles
- `medical_cost_regression.ipynb`: Jupyter Notebook con el análisis completo (exploración, modelado y visualización).
- `insurance.csv`: Conjunto de datos en formato CSV.

## Autora
Yamile Montecinos: [@yamilemr](https://github.com/yamilemr)