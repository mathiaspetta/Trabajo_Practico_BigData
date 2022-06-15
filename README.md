# Trabajo_Practico_BigData
Trabajo Practico de Big Data, Componentes 1 y 2. Por Axel Mathias Petta

COMPONENTE 1
Primeramente de accedieron a los tokens de twitter con las determiandas credenciales.
Posteriormente se autenticaron y se establecio el date time para recolectar los tweets.
Se pregunta al usuario para ingresar el nombre del hashtag y la cantidad de tweets. Se crearon dos variables, una para recoger el hashtag y otra para recolectar los tweets.
Se buscaron tweets en Twitter usando la función Cursor(). Paso el parámetro api.search al cursor, así como la cadena de consulta, que se especifica mediante el parámetro q del cursor. Recolectando asu tweets en un tweet_list los siguientes parametros: (tweet.text, tweet.user.screen_name, tweet.created_at, tweet.retweet_count, tweet.favorite_count)
Posteriormente se creo un Data Frame para visualizar los tweets con las siguientes columnas: [ "Tweet", "Autor", "Fecha", "Total Favs", "Total RTs"]
Finalmente se creo un csv con la lista de tweets y sus columnas con el nombre del hashtag que se busco los tweets.

COMPONENTE 2
Para el analisis de los sentimientos se utilizo el analisis con polaridad y subjetividad, con las librerias de SentimentIntensityAnalyzer con los polarity scores para definir los tweets positivos, neutrales y negativos.
Primeramente se lee el CSV creado anteriormente con la lista de tweets recolectada.
Pese a que los datos estan sucios, luego se procede a limpiar los tweets, eliminando los hashtags, menciones, Rts, liks y tags.
Se agrega la subjetividad y polaridad de los tweets al DataFrame. Se crean dos funciones, una para obtener los tweets llamada Subjetividad (qué tan subjetivo u obstinado es el texto: una puntuación de 0 es un hecho, y una puntuación de +1 es en gran medida una opinión) y la otro para obtener los tweets llamados Polaridad (qué tan positivo o negativo es el texto, -- una puntuación de -1 es la puntuación negativa más alta y una puntuación de +1 es la puntuación positiva más alta).
Luego se procede al mismo analisis pero creando listas de positivos, neutrales y negativos.
Este analisis nuevo se procede a guardar en el mismo csv: tweets_list.to_csv("Analisis_de_" + hashtag + ".csv")
Luego se eliminan conectores y palabras inutiles, para asi generar una nube de palabras de los tweets analizados.
Finalmente se crean dos graficos, un scatter plot con la subjetividad y polaridad de los sentimientos analizados para entender que tan variados son los tweets, y otro con la cantidad de los tweets positivos, negativos y neutrales.
