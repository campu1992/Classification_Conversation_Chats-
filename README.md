# Classification_Conversation_Chats-

## Informe sobre Clasificación de Conversaciones 

### 1. Introducción:
El presente informe documenta el proceso de construcción y evaluación de un modelo de clasificación de texto utilizando SVM y TfidfVectorizer para establecer si una negociación de venta se lleva a cabo o no y otro modelo de clasificación de texto haciendo fine-tuning de un modelo pre-entrenado de Bert en español para clasificar el tipo de negocio que se está llevando a cabo en la conversacion

### 2. Descripción del Problema:
El problema consiste en clasificar conversaciones de ventas en función de su contenido para identificar patrones que puedan predecir la probabilidad de que la negociación halla terminado en una venta exitosa o no y así mismo establecer según la conversación qué tipo de negociación se esta llevando a cabo.

### 3. Descripción del Conjunto de Datos:
El conjunto de datos contiene conversaciones de ventas de productos fisicos etiquetadas con la variable objetivo "Venta" -- True o --False y tambien con la variable objetivo "Categoria" -- venta_de_producto_fisico  .

### 4. Preprocesamiento de Datos:
Se realizó un preprocesamiento que incluyó limpieza de texto, tokenización y vectorización utilizando TfidfVectorizer. Además, se balancearon las clases para evitar sesgos en el modelo.

### 5. Construcción del Modelo:
Se construyó un pipeline que incluye TfidfVectorizer para la extracción de características y un clasificador SVM para la clasificación.

### 6. Hiperparámetros y Validación:
Se utilizó GridSearchCV para la búsqueda de hiperparámetros y validación cruzada de 5 pliegues para evaluar el rendimiento del modelo.

### 7. Evaluación del Modelo:
El modelo entrenado alcanzó una precisión del 95% en el conjunto de prueba. Se presenta la matriz de confusión y otras métricas de evaluación.

### 8. Conclusiones y Recomendaciones:
El modelo demostró un buen rendimiento en la clasificación de conversaciones de ventas. Sin embargo, se sugiere investigar técnicas adicionales para mejorar la generalización y la robustez del modelo.

