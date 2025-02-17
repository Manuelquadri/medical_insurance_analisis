Análisis de Costos en Seguros Médicos 
Introducción 
Este proyecto analiza un conjunto de datos de seguros médicos con el objetivo de 
identificar los factores que influyen en el costo de los seguros de salud. Utilizamos 
un enfoque de Análisis Exploratorio de Datos (EDA), transformación de datos, 
detección de outliers y modelado estadístico para evaluar las relaciones entre 
diferentes características y los costos médicos. 
Dataset 
El dataset fue descargado de Kaggle y contiene la siguiente información: 
• Age: Edad del asegurado. 
• Sex: Sexo del asegurado. 
• BMI: Índice de masa corporal. 
• Children: Número de hijos del asegurado. 
• Smoker: Indica si el asegurado es fumador o no. 
• Region: Región donde reside el asegurado. 
• Charges: Costos médicos generados por el asegurado. 
Objetivos del Análisis 
1. Identificar los principales factores que contribuyen al aumento de los 
costos médicos. 
2. Detectar la existencia de outliers y evaluar su impacto. 
3. Construir modelos de regresión para predecir los costos médicos en 
función de las características del asegurado. 
Análisis Exploratorio de Datos (EDA) 
Se realizaron las siguientes acciones para conocer el dataset: 
• Verificación de valores nulos y duplicados. 
• Exploración estadística de las variables numéricas. 
• Visualización de distribuciones mediante histogramas. 
• Creación de boxplots para evaluar la influencia de diferentes factores en 
los costos. 
Insights clave del EDA 
• La edad promedio de los asegurados es 39 años. 
• El BMI promedio es de 30.7, indicando que la mayoría de los asegurados 
están en sobrepeso. 
• Hay una diferencia significativa entre la media y la mediana de los costos, 
indicando una distribución sesgada y la posible presencia de outliers. 
• La variable fumador tiene una fuerte correlación positiva con los costos 
médicos. 
Detección de Outliers 
Se calcularon los outliers en base al rango intercuartílico (IQR): 
• Se identificaron 296 outliers en la variable charges. 
• El 96.7% de los outliers corresponden a personas fumadoras. 
• Los outliers no fueron eliminados, ya que reflejan combinaciones de 
factores de riesgo reales y su eliminación podría sesgar el análisis. 
Transformación de Datos 
Para facilitar el análisis y la modelización: 
• Se convirtieron las variables categóricas sex y smoker a valores binarios. 
• Se aplicó one-hot encoding a la variable region. 
Análisis de Correlación 
Se generó un heatmap para visualizar la correlación entre las variables: 
• Smoker vs Charges: Correlación fuerte de 0.79. 
• Age vs Charges: Correlación positiva moderada de 0.3. 
• BMI vs Charges: Correlación positiva moderada de 0.2. 
• Se observa una correlación fuerte entre fumadores con altos valores de 
BMI y mayores costos médicos. 
Modelado: Regresión Lineal 
Se construyó un modelo de regresión lineal para predecir los costos médicos: 
• R-cuadrado: 0.841, indicando que el modelo explica el 84.1% de la 
variabilidad de los costos. 
• Principales predictores: 
o Ser fumador incrementa los costos en $20,480. 
o Cada año adicional de edad aumenta los costos en $261.68. 
o La interacción entre BMI y fumar amplifica el impacto del BMI en los 
costos. 
Conclusiones 
1. El factor más relevante es el tabaquismo, con un impacto significativo en 
los costos de salud. 
2. La edad y el BMI también tienen un impacto relevante, aunque menor 
que el tabaquismo. 
3. Los costos son considerablemente más altos en personas fumadoras 
con alto BMI, lo que sugiere que estos dos factores combinados 
representan un alto riesgo para el seguro. 
4. Las diferencias entre regiones son significativas, con el Northeast 
presentando los costos más altos. 
Recomendaciones 
• Diseñar estrategias de precios diferenciados para fumadores y no 
fumadores. 
• Evaluar programas de bienestar para reducir el IMC entre los asegurados. 
• Seguir explorando métodos de modelado avanzados para mejorar la 
precisión de las predicciones. 
Tecnologías Utilizadas 
• Python (Pandas, NumPy, Seaborn, Matplotlib, Statsmodels, Lifelines) 
• Jupyter Notebook para documentar y ejecutar el análisis.