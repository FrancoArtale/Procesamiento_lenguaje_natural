# Desafíos de procesamiento del lenguaje natural

Especialización en IA - UBA (Universidad Nacional de Buenos Aires) - Projectos finales

### Desafío 1:

En el primer desafío, se abordaron los fundamentos de la vectorización de texto, utilizando posteriormente un modelo de clasificación como Naïve Bayes para encontrar similitudes entre textos. Para ello, se empleó el conjunto de datos _20 Newsgroups_ de scikit-learn.

Para la vectorización se siguieron los siguientes pasos:
1. Se instanció un vectorizador.
2. Se entrenó el vectorizador.

Para valorar la similitud entre texto se uso la similitud del coseno.

Luego se optimizaron estos modelo para lograr el maximo valor de la metrica F1-score. El mejor valor obtenido fue de 0.77.

Por ultimo se invirtio la matriz documento-término para estudiar similitudes entre palabras. En la siguiente figura se puede ver un ejemplo de predicciones de palabras similares:

![Predicciones de palabras](desafio1_similitud_palabras.png)

Enlaces de utilidad:
- https://scikit-learn.org/0.19/datasets/twenty_newsgroups.html
- https://www.geeksforgeeks.org/cosine-similarity/
- https://en.wikipedia.org/wiki/Document-term_matrix

### Desafío 2:

A partir de un dataset (corpus), se crearon vectores de palabras (embeddings) utilizando la biblioteca Gensim. Los vectores fueron graficados para observar las similitudes en el espacio de embeddings. Finalmente, se plantearon pruebas de analogías.

El dataset utilizado fue la Biblia del proyecto Gutenberg, la cual fue preprocesada antes de crear los vectores. El preprocesamiento incluyó los siguientes pasos:
1. Lematización.
2. Eliminación de los signos de puntuación.
3. Filtrado las _stropwords_.
Para generar los vectores, se utilizó un modelo Word2Vec. Posteriormente, el modelo generador de vectores fue entrenado durante 100 épocas.

En la siguiente figura, se pueden ver resultados similares usando la similitud coseno de la palabra _god_:

![image](https://github.com/user-attachments/assets/1dbfa956-efd8-409d-bd85-27ddeae0a70c)

En la siguiente figura, se pueden observar los resultados menos similares de la palabra _prayer_:

![image2](https://github.com/user-attachments/assets/09d24eab-a47d-448b-9269-7df7e7b2af5d)

En la siguiente imagen, se muestra la distribución de los vectores en el espacio de embeddings:

![image3](https://github.com/user-attachments/assets/d8153e05-3012-4bfa-8026-c942529704c7)

En el gráfico, podemos ver que las palabras "David" y "altar" están muy cerca entre sí. Según la Biblia, David construyó un altar e hizo sacrificios allí, lo que podría explicar esta relación que se observa en el gráfico.

En el gráfico también se puede apreciar una cercanía entre "seven" y "priest" (sacerdote). Esto tal vez se deba a los siete sacramentos, de los cuales la mayoría solo puede ser administrada por un sacerdote.

Asimismo, "water" y "sea" están cercanos.

Uno de los tests de analogías que se realizó fue: "orador" es a "Dios" como "sacrificio" es a "altar", con el fin de obtener palabras relacionadas con "altar". Sin embargo, se obtuvieron resultados más cercanos a "sacrificio". En la siguiente imagen se puede ver lo obtenido:

![image](https://github.com/user-attachments/assets/f00edb48-5c59-4b07-b0bf-a5c62438300e)

Enlaces de utilidad:
- https://radimrehurek.com/gensim/
- https://www.baeldung.com/cs/latent-vs-embedding-space
- https://www.gutenberg.org/
- https://www.datacamp.com/es/tutorial/stemming-lemmatization-python
- https://blackbeast.pro/diccionario/stop-words/#:~:text=Las%20Stop%20Words%20o%20palabras,la%20palabra%20clave%20o%20keyword.

### Desafío 3:

Se entrenaron modelos de lenguaje con tokenización por caracteres y por palabras. Estos modelos se utilizaron para la generación de secuencias. Para la generación, se emplearon tanto la predicción más probable como métodos como Beam Search y muestreo aleatorio para armar las secuencias.

El dataset (corpus) utilizado en este caso fue el libro Viaje al centro de la Tierra de Julio Verne, descargado del proyecto Gutenberg.

Preprocesamiento de datos:
1. Tokenización del libro.
2. División de las sentencias en segmentos de 100 caracteres o palabras, según el modelo.
3. Separación en entrenamiento y validación.

Para el entrenamiento, se utilizó la métrica de perplejidad. Las arquitecturas utilizadas fueron RNN, LSTM y GRU, todas entrenadas durante 20 épocas.

En la siguiente figura, se muestra el rendimiento de las distintas arquitecturas en el caso de tokenización por caracteres:

![image](https://github.com/user-attachments/assets/1a90ba5e-6eab-4418-95dc-ba02cc20ba57)

En la siguiente figura, se muestra el rendimiento de las distintas arquitecturas en el caso de tokenización por palabras:

![image](https://github.com/user-attachments/assets/c1c120da-4961-4b7e-9531-48f06f8a3236)

En la siguiente figura se puede ver las predicciones de las distintas arquitecturas en el caso de tokenización por caracteres usando Beam Search estocástico:

![image](https://github.com/user-attachments/assets/dfc5c4dc-2485-4292-a3fa-113424b11e98)


En la siguiente figura, se muestran las predicciones de las distintas arquitecturas en el caso de tokenización por palabras utilizando Beam Search estocástico.

![image](https://github.com/user-attachments/assets/43aefdf7-8628-427c-92ec-a88364aa1bae)

Enlaces de utilidad:
- https://www.gutenberg.org/
- https://charanhu.medium.com/unveiling-the-power-of-character-level-tokenization-in-natural-language-processing-b2adadbbc72c#:~:text=Character%2Dlevel%20tokenization%20operates%20by,text%20into%20its%20atomic%20components.
- https://towardsdatascience.com/word-subword-and-character-based-tokenization-know-the-difference-ea0976b64e17
- https://njoroge.tomorrow.co.ke/blog/ai/word_vs_character_level_tokenization
- https://blog.dinobrain.ai/beam-search/#:~:text=El%20'beam%20search'%20es%20un,secuencias%20m%C3%A1s%20coherentes%20y%20precisas.
- https://klu.ai/glossary/perplexity
- https://keras.io/api/layers/recurrent_layers/
- https://keras.io/api/layers/recurrent_layers/lstm/
- https://keras.io/api/layers/recurrent_layers/gru/

### Desafío 4:

En este desafío, se lleva a cabo la implementación de un bot de preguntas y respuestas (QA). Se utiliza datos disponibles del challenge ConvAI2 (Conversational Intelligence Challenge 2) de conversaciones en inglés. Los datos se pueden descargar desde [challenge ConvAI2 ](http://convai.io/data/).

Prepocesamiento de datos:
1. Se eliminaron los apóstrofes mediante una función personalizada.
2. Las sentencias se limitaron a un máximo de 10 palabras.
3. Se tokenizaron las sentencias.
4. Se aplicó padding para uniformar la longitud de las sentencias.

Se utilizaron los embeddings de FastText para transformar los tokens de entrada en vectores, específicamente los embeddings _crawl-300d-2M.vec_.

El primer modelo entrenado se basó en una arquitectura encoder-decoder, cada uno con una capa de embedding y una LSTM.

Los resultados del entrenamiento de este modelo se pueden observar en la siguiente figura:

![image](https://github.com/user-attachments/assets/c62995ab-2b26-4212-b32d-fb5efb8bc599)

En las siguientes imágenes, se pueden observar ejemplos de preguntas y respuestas generadas usando este modelo:

![image](https://github.com/user-attachments/assets/b617ac31-65f0-4647-961a-b93007d48814)
![image](https://github.com/user-attachments/assets/e0b5962d-ba99-482b-9c5b-39aaa94e231a)

El segundo modelo utilizado fue similar al anterior, pero con un stack de LSTMs: 3 capas para el encoder y 3 capas para el decoder, cada uno con sus respectivas capas de embeddings. Los resultados del entrenamiento se pueden ver en la siguiente figura:

![image](https://github.com/user-attachments/assets/4f65b331-52ea-40e5-aaaf-15c046f4bf15)

En las siguientes imágenes, se pueden observar ejemplos de preguntas y respuestas generadas usando este modelo:

![image](https://github.com/user-attachments/assets/afed733e-fa0a-40e6-84fa-965bc1d20d15)
![image](https://github.com/user-attachments/assets/e0b5962d-ba99-482b-9c5b-39aaa94e231a)

En el último modelo, se utilizó una capa LSTM para el encoder y otra para el decoder, con sus correspondientes capas de embeddings y una capa de attention. Los resultados del entrenamiento se pueden ver en la siguiente figura:

![image](https://github.com/user-attachments/assets/28726f9c-234f-4426-9bb2-ffd493009dce)

En las siguientes imágenes, se pueden observar ejemplos de preguntas y respuestas generadas usando este modelo:

![image](https://github.com/user-attachments/assets/953e1b17-d191-4c70-83ed-3e0ecbd53429)
![image](https://github.com/user-attachments/assets/9e90da13-4f91-4b41-b5a5-98df27837f7d)

Enlaces de utilidad:
- https://medium.com/@prashantmalge181/building-q-a-chat-bot-gemma-llm-with-hugging-face-233ddcc76fe8
- https://www.linkedin.com/advice/0/what-best-nlp-models-question-answering-skills-machine-learning-rzbgf
- https://medium.com/@mrmohit254/end-to-end-implementation-of-a-qa-bot-using-deep-learning-a3225e62bf22
- https://convai.io/data/
- https://fasttext.cc/docs/en/crawl-vectors.html
- https://keras.io/api/layers/recurrent_layers/lstm/
- https://medium.com/analytics-vidhya/https-medium-com-understanding-attention-mechanism-natural-language-processing-9744ab6aed6a
- https://slds-lmu.github.io/seminar_nlp_ss20/attention-and-self-attention-for-nlp.html

## Muchas gracias!
Sientete libre de contactarte por mail a francoa23@gmail.com por cualquier duda.
Disfruta 😄!!
