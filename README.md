# Análisis de Costos en Seguros Médicos

## Introducción
Este proyecto analiza un conjunto de datos de seguros médicos con el objetivo de identificar los factores que influyen en el costo de los seguros de salud. Utilizamos un enfoque de Análisis Exploratorio de Datos (EDA), transformación de datos, detección de outliers y modelado estadístico para evaluar las relaciones entre diferentes características y los costos médicos.

## Dataset
El dataset fue descargado de [Kaggle](https://www.kaggle.com/) y contiene la siguiente información:
- **Age**: Edad del asegurado
- **Sex**: Sexo del asegurado
- **BMI**: Índice de masa corporal
- **Children**: Número de hijos del asegurado
- **Smoker**: Indica si el asegurado es fumador o no
- **Region**: Región donde reside el asegurado
- **Charges**: Costos médicos generados por el asegurado

## Objetivos del Análisis
1. Identificar los principales factores que contribuyen al aumento de los costos médicos
2. Detectar la existencia de outliers y evaluar su impacto
3. Construir modelos de regresión para predecir los costos médicos

## Análisis Exploratorio de Datos (EDA)
Se realizaron las siguientes acciones:
- Verificación de valores nulos y duplicados
- Exploración estadística de variables numéricas
- Visualización de distribuciones mediante histogramas
- Creación de boxplots para evaluar influencia de diferentes factores

### Insights clave del EDA
- Edad promedio: 39 años
- BMI promedio: 30.7 (mayoría en sobrepeso)
- Diferencia significativa entre media y mediana de costos (distribución sesgada)
- Variable `smoker` muestra fuerte correlación positiva con costos

## Detección de Outliers
- 296 outliers identificados en `charges`
- 96.7% de outliers corresponden a fumadores
- Outliers no fueron eliminados (reflejan situaciones reales)

## Transformación de Datos
- Variables categóricas (`sex`, `smoker`) convertidas a binarias
- One-hot encoding aplicado a `region`

## Análisis de Correlación
Se generó un heatmap para visualizar la correlación entre las variables:
- `smoker` vs `charges`: 0.79 (fuerte)
- `age` vs `charges`: 0.3 (moderada)
- `bmi` vs `charges`: 0.2 (moderada)

## Modelado: Regresión Lineal
- **R-cuadrado**: 0.841 (84.1% de variabilidad explicada)
- Principales predictores:
  - Fumador: +$20,480 en costos
  - Edad: +$261.68 por año
  - Interacción BMI-Fumador amplifica impacto

## Conclusiones
1. Tabaquismo es el factor más relevante en costos
2. Edad y BMI tienen impacto moderado
3. Combinación fumador + alto BMI = alto riesgo
4. Región Northeast tiene costos más altos

## Recomendaciones
- Estrategias de precios diferenciados para fumadores
- Programas de bienestar para reducir BMI
- Explorar modelos predictivos más avanzados

## Tecnologías Utilizadas
- Python (Pandas, NumPy, Seaborn, Matplotlib, Statsmodels)
- Jupyter Notebook
