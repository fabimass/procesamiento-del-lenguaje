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
