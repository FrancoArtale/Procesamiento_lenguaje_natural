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

A partir de un dataset (corpus) se crearon vectores de palabras (embeddings) usando Gensim. Se graficaron los vectores y se observaron las similitudes en el espacio de emebddings. Por ultimo se plantearon tests de analogías.

El dataset utilizado fue la biblia del projecto Gutenberg.
El dataset fue preprocesado antes de crear los vectores, el preprocesamiento se enumera de la siguiente forma:
1. Lematización.
2. Se quitaron los signos de puntuaciones.
3. Se filtraron las _stropwords_.
Para generar los vectores se uso un modelo Word2Vec.
Luego se entreno el modelo generador de vectores durante 100 epocas.

En la siguiente figura se pueden ver resultados similares usando la similitud coseno de la palabra _god_:

![image](https://github.com/user-attachments/assets/1dbfa956-efd8-409d-bd85-27ddeae0a70c)

En la siguiente figura se pueden ver resultados menos similares de la palabra _prayer_:

![image2](https://github.com/user-attachments/assets/09d24eab-a47d-448b-9269-7df7e7b2af5d)

En la siguiente imagen podemos ver una distribución de los vectores en el espacio de embeddings:

![image3](https://github.com/user-attachments/assets/d8153e05-3012-4bfa-8026-c942529704c7)

En el grafico podemos ver que las palabras David y altar estan muy cercas entre si, según la biblia David construyó un altar e hizo sacrificios allí. Puede ser por esto esa relación que se ve en el grafico.  

En el grafico también se puede ver una cercanía entre 'seven' y 'priest' (sacerdote), tal vés esto se deba a los siete sacramentos y que la mayoria solo puede ser administrado por un sacerdote.

'water' y 'sea' estan cercanos.

Uno de los tests de analogías que se realizó fue 'orador' es a 'dios' com 'sacrificio' es a 'altar', con el fin de obtener palabras relacionadas a 'altar' pero se obtuvieron resultados similares a 'sacrificio', en la siguiente imagen se puede ver lo obtenido:

![image](https://github.com/user-attachments/assets/f00edb48-5c59-4b07-b0bf-a5c62438300e)

## Muchas gracias!
Sientete libre de contactarte por mail a francoa23@gmail.com por cualquier duda.
Disfruta 😄!!
