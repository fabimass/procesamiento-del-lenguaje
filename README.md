# Especialización en IA - Procesamiento Natural del Lenguaje

<br>

# [Desafío 1](desafio_1/Desafio_1.ipynb)

Este proyecto aborda un desafío práctico en el ámbito del Procesamiento de Lenguaje Natural (NLP), utilizando el dataset clásico `20newsgroups`. A lo largo del ejercicio se implementan diversas técnicas de NLP para la clasificación de textos y el análisis de similaridad, explorando modelos de clasificación y evaluando su desempeño.

## Contenidos

### 1. Vectorización y Análisis de Similaridad de Documentos

Se implementa la vectorización de los documentos utilizando `TfidfVectorizer`. Luego, se seleccionan 5 documentos al azar y se mide la similaridad coseno con el resto de los documentos en el conjunto de datos. Los 5 documentos más similares a cada uno se analizan en función de su contenido y la etiqueta de clasificación, evaluando si la similaridad calculada refleja una relación semántica coherente.

### 2. Entrenamiento y Evaluación de Modelos de Clasificación Naïve Bayes

Se exploran y entrenan modelos de clasificación `MultinomialNB` y `ComplementNB`, ajustando diferentes parámetros de los vectorizadores y los modelos para maximizar el f1-score macro en el conjunto de datos de prueba. Se comparan distintas configuraciones de vectorización y modelos, evaluando su rendimiento y seleccionando la combinación óptima.

### 3. Análisis de Similaridad entre Palabras

La matriz documento-término es transpuesta para obtener una matriz término-documento, lo que permite estudiar la similaridad entre palabras. Se seleccionan manualmente 5 palabras relevantes y se mide la similaridad coseno con otras palabras en el vocabulario. Este análisis permite interpretar las relaciones semánticas entre términos según su contexto de uso en los documentos.

<br>

# [Desafío 2](desafio_2/Desafio_2.ipynb)

Este trabajo tiene como objetivo explorar y analizar las relaciones semánticas entre palabras utilizando modelos de word embeddings entrenados con Gensim.

## Contenidos

### 1. Entrenamiento de Embeddings

Utilización de `nltk` y `Gensim` para procesar el dataset de reseñas de películas de IMDb y generar vectores de embeddings que representan las palabras en un espacio semántico.

### 2. Relaciones Semánticas entre Palabras

Se realizaron pruebas para identificar las palabras más y menos relacionadas con términos clave como:

- "excellent"
- "boring"
- "plot"
- "director"
- "soundtrack"
- "actor"

Los resultados muestran que el modelo es capaz de capturar relaciones esperadas, como la cercanía entre **"excellent"** y **"phenomenal"** o entre **"boring"** y **"predictable"**.

### 3. Test de Analogías

Para validar la capacidad del modelo de identificar analogías, se realizaron las siguientes pruebas:

- **man** es a **woman** como **actor** es a **actress**
- **good** es a **bad** como **entertaining** es a **insipid**

Los resultados demuestran que el modelo capta correctamente tanto relaciones de género como opuestos, destacando su capacidad para reconocer patrones semánticos más profundos.

### 4. Visualización de Embeddings

Los embeddings fueron visualizados en espacios 2D y 3D, mostrando las relaciones geométricas entre los términos seleccionados.

<br>

# [Desafío 3](desafio_3/Desafio_3.ipynb)

Este proyecto implementa modelos de lenguaje entrenados con reseñas de películas de IMDb para la generación automática de secuencias de texto. Se exploran dos enfoques de tokenización: tokenización por palabras y tokenización por caracteres. Ambos enfoques utilizan el algoritmo de **Beam Search** para la generación de secuencias.

## Contenidos

### 1. Tokenización por palabras

El modelo predice secuencias basadas en la estructura de las palabras en las reseñas.

- **Input**: "two teen couples go to"
- **Result**: "two teen couples go to patrick's"

- **Input**: "watch the movie and"
- **Result**: "watch the movie and the performance"

### 2. Tokenización por caracteres

El modelo genera secuencias de texto prediciendo carácter por carácter.

- **Input**: "two teen couples go to"
- **Result**: "two teen couples go to the"

- **Input**: "watch the movie and"
- **Result**: "watch the movie and see"

<br>

# [Desafío 4](desafio_4/Desafio_4.ipynb)

En este proyecto, se ha construido un modelo de bot de Preguntas y Respuestas (Q&A) utilizando los datos del *Conversational Intelligence Challenge 2* (ConvAI2). El objetivo principal ha sido crear un sistema capaz de generar respuestas coherentes y contextuales a preguntas comunes basadas en los datos proporcionados.

## Contenidos

### 1. Preprocesamiento de Datos  

Se llevó a cabo la limpieza y tokenización de los datos del dataset ConvAI2 para preparar el conjunto de entrenamiento.

### 2. Generación de Embeddings 

Se utilizaron los embeddings de Glove para transformar los tokens de entrada en vectores, representando las palabras de manera semánticamente significativa.

### 3. Entrenamiento del Modelo 

Se entrenó un modelo basado en un esquema *encoder-decoder* utilizando los datos preprocesados y los embeddings generados.

### 4. Evaluación y Resultados  

Se realizaron experimentos para evaluar la calidad y coherencia de las respuestas generadas. El modelo es capaz de responder preguntas comunes con cierta coherencia. Ejemplos de entradas y respuestas generadas incluyen:

- **Input:** "what is your hobby?"  
  **Response:** "i like to play video games"

- **Input:** "wat do you do for a living?"  
  **Response:** "i m a student"

- **Input:** "do you have any pet?"  
  **Response:** "no"

<br>

# [Desafío 5](desafio_5/Desafio_5.ipynb)

Este proyecto implementa un análisis de sentimiento sobre reseñas de usuarios utilizando BERT (Bidirectional Encoder Representations from Transformers). El objetivo es clasificar reseñas en categorías de sentimiento como muy positivo, positivo, neutral, negativo y muy negativo.

## Contenidos

### 1. Preprocesamiento de Datos 

Los textos fueron limpiados y convertidos en tokens utilizando `tokenizers.BertTokenizer`. Además, las etiquetas de clasificación se transformaron en un formato adecuado para el entrenamiento.

### 2. Carga y Ajuste del Modelo BERT

Se utilizó un modelo preentrenado de BERT (`bert-base-uncased`) y se realizaron modificaciones para ajustarlo a las cinco categorías de salida. Se añadió una capa densa adicional para manejar la clasificación multicategorica.

### 3. Entrenamiento del Modelo

Se dividió el conjunto de datos en subconjuntos de entrenamiento y prueba, y el modelo fue entrenado utilizando el optimizador Adam. También se incorporaron técnicas de regularización, como dropout, para evitar el sobreajuste.

### 4. Evaluación y Resultados

El modelo fue evaluado en el conjunto de prueba, logrando una precisión aceptable en la clasificación de las reseñas. A continuación se muestran algunos ejemplos de clasificación de textos:

- **Reseña:** "I love this app!"
  **Clasificación:** very positive

- **Reseña:** "Fair enough"
  **Clasificación:** positive

- **Reseña:** "Useful but could improve"
  **Clasificación:** positive

- **Reseña:** "Not what I expected"
  **Clasificación:** very negative

- **Reseña:** "This is the worst app I have seen!"
  **Clasificación:** very negative