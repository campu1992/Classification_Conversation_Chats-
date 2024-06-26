# Classification_Conversation_Chats-

## Informe sobre Clasificación de Conversaciones 

### 1. Introducción:
El presente informe documenta el proceso de construcción y evaluación de un modelo de clasificación de texto utilizando SVM y TfidfVectorizer para establecer si una negociación de venta se lleva a cabo o no y otro modelo de clasificación de texto haciendo fine-tuning de un modelo pre-entrenado de Bert en español para clasificar el tipo de negocio que se está llevando a cabo en la conversacion

### 2. Descripción del Problema:
El problema consiste en clasificar conversaciones de ventas en función de su contenido para identificar patrones que puedan predecir la probabilidad de que la negociación halla terminado en una venta exitosa o no y así mismo establecer según la conversación qué tipo de negociación se esta llevando a cabo.

### 3. Descripción del Conjunto de Datos:
El conjunto de datos contiene conversaciones de ventas de productos fisicos electrónicos las cuales fueron generadas con ChatGpt para productos diferentes entre un agente y un cliente , etiquetadas con la variable objetivo "Venta" -- True o --False y tambien con la variable objetivo "Categoria" -- venta_de_producto_fisico  .

### 4. Preprocesamiento de Datos:
Se realizó un preprocesamiento que incluyó limpieza de texto, tokenización, lemmatización y vectorización utilizando TfidfVectorizer. Además, se balancearon las clases haciendo un submuestreo para evitar sesgos en el modelo.

### 5. Construcción del Modelo:
Se construyó un pipeline que incluye TfidfVectorizer para la extracción de características y un clasificador SVM para la clasificación para la clasificación de negocio exitoso o no exitoso, Para clasificar el tipo de negocio, debido a la falta de datos de cada categoria para entrenar un modelo desde cero se recurrió a usar un modelo pre-entrenado basado en transformers como lo es Bert en español, se hizo un fine-tuning entrenandolo con los datos de la categoria venta_de_producto_fisico entrenando las capas mas superficiales para poder mantener los datos originales del modelo pre-entrenado y que no hubiese un sobreajuste con una sola de las categorias.

### 6. Hiperparámetros y Validación:
Se utilizó GridSearchCV para la búsqueda de hiperparámetros y validación cruzada de 5 pliegues para evaluar el rendimiento del modelo , ya que, se observó un recall de 1 pero al momento de hacer la validación cruzada se obtuvo un promedio de 0.95, lo cual podemos inferir que funciona ante diferentes escenarios pero necesita una mayor cantidad de datos para entrenamiento y evitar sobreajustes.

### 7. Evaluación del Modelo:
El modelo entrenado alcanzó una precisión del 95% en el conjunto de prueba. Se presenta la matriz de confusión y otras métricas de evaluación como accuracy, F1 Score , Recall.

### 8. Conclusiones y Recomendaciones:
El modelo demostró un buen rendimiento en la clasificación de conversaciones de ventas. Sin embargo, se debe aumentar la cantidad de datos de entrenamiento para ambos modelos y así mejorar la generalización y la robustez de los modelos.

### 9. Librerias 
-pandas
-matplotlib
-seaborn
-numpy
-nltk
-sklearn
-tensorflow
-transformers
-torch
-re
-string
-joblib

### 10. Caso de uso
Se entrega un archivo ejecutable el cual da la opcion de introducir el texto a clasificar o se presenta la opcion de subir un csv con las columnas Producto y Conversación.

