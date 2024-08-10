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

### Desafío 3:

Se entrenaron modelos de lenguaje con tokenización por caracteres y por palabras. Estos modelos se utilizaron para la generación de secuencias. Para la generación, se emplearon tanto la predicción más probable como métodos como Beam Search y muestreo aleatorio para armar las secuencias.

El dataset (corpus) utilizado en este caso fue el libro Viaje al centro de la Tierra de Julio Verne, descargado del proyecto Gutenberg.

Preprocesamiento de datos:
1. Tokenización del libro.
2. Separamos las sentencias en un larog de 100 caracteres o palabras según el modelo.
3. Separación en entrenamiento y validación.

Para el entrenamiento se utilizó la metrica de perplejidad, las arquitecturas utilizadas fueron RNN, LSTM Y GRU, todos entrenados durante 20 epocas.

En la siguiente figura se puede ver el rendimiento de las distintas arquitecturas en el caso de tokenización por caracteres:

![image](https://github.com/user-attachments/assets/1a90ba5e-6eab-4418-95dc-ba02cc20ba57)

En la siguiente figura se puede ver el rendimiento de las distintas arquitecturas en el caso de tokenización por palabras:

![image](https://github.com/user-attachments/assets/c1c120da-4961-4b7e-9531-48f06f8a3236)

En la siguiente figura se puede ver las predicciones de las distintas arquitecturas en el caso de tokenización por caracteres:

![image](https://github.com/user-attachments/assets/dfc5c4dc-2485-4292-a3fa-113424b11e98)


En la siguiente figura se puede ver las predicciones de las distintas arquitecturas en el caso de tokenización por palabras:

![image](https://github.com/user-attachments/assets/43aefdf7-8628-427c-92ec-a88364aa1bae)

### Desafío 4:


## Muchas gracias!
Sientete libre de contactarte por mail a francoa23@gmail.com por cualquier duda.
Disfruta 😄!!
