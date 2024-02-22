# Dashboard

## Meta

Representar datos a través de tabla resumen o scorecards.

Representar datos a través de gráficos simples.

Representar datos a través de gráficos o visuales avanzados.

Aplicar opciones de filtros para manejo e interacción.

## Objetivo

Crear scorecards para los números generales de la base de datos.

Representar los datos a través de gráficos de barras y líneas.

Representar datos a través de scatter plot.

Incluir filtros para visualizar los resultados por categorías y por fecha.

## Objetivo individual

* [x] Cada una debe crear al menos una tarjeta de resultados (scorecards).
* [x] Cada una ya ha hecho este ejercicio anteriormente en la habilidad de Análisis Exploratorio, ahora como dupla deben elegir qué gráficos utilizar en su dashboard y organízalo.
* [x] Cada una ya ha hecho este ejercicio anteriormente en la habilidad de Análisis Exploratorio, ahora como dupla deben elegir qué gráficos utilizar en su dashboard y organízalo para que explique los resultados obtenidos.
* [x] Incluir una página donde se pueda visualizar los datos generales por filtros. Cada una debe incluir un filtro, pueden ser filtro de fecha, filtro de categoría, etc.

## Conclusiones

<figure><img src="../../.gitbook/assets/image (32).png" alt=""><figcaption></figcaption></figure>

**Dashboard 1**

* En la categoría de "Altos" Hay un total de 2101 Streams, un total track\_id de 228,  el mayor año de Streams fue en el 2020 con 99.

En esta categoría se encuentra la artista Taylor Swift, lo cual puede ser por el tipo de música que interpreta que tiene características en sus canciones que son enérgicas, tiende a tener una dinámica sonora potente e intensa; con un total de Streams de 34, un total de Playlists de 21 mil, tiende a tener más presencia y rango de sus canciones en las listas de Apple con el 75% y en Spotify con 22%, el año que tuvo más Streams 16 fue en el 2020.

* En la categoría de "Bajos" Hay un total de 2178 Streams, un total track\_id de 674,  el mayor año de Streams fue en el 2020 con 298.

En esta categoría se encuentra la artista Bad Bunny, lo cual puede ser por el tipo de música que interpreta que tiene características en sus canciones que son con frecuencias menos enérgicas, tiende a tener una dinámica sonora menos potente e intensa o que la presencia de bajos es menos intensa; con un total de Streams de 19, un total de Playlists de 53 mil, tiende a tener más presencia y rango de sus canciones en las listas de Apple con el 73% y en Spotify con 23%, el año que tuvo más Streams 15 fue en el 2022.

<figure><img src="../../.gitbook/assets/image (33).png" alt=""><figcaption></figcaption></figure>

**Dashboard 2**&#x20;

#### 1. Hipótesis: Canciones con mayor BPM tienen más éxito en Spotify.

* **Resultado:**
  * Error Cuadrático Medio (ECM): 704.12
  * Coeficiente de Determinación (R²): -0.0164

**Conclusión:**

* **ECM:** Cuanto menor sea el ECM, mejor. En este caso, el valor no es extremadamente bajo, lo que indica que la hipótesis no es muy precisa.
* **R²:** Un valor negativo sugiere que la relación entre el BPM y el éxito en Spotify no es clara ni fuerte.

#### 2. Hipótesis: Canciones populares en Spotify tienen comportamiento similar en Deezer.

* **Resultado:**
  * ECM: 188.44
  * R²: 0.2423

**Conclusión:**

* **ECM:** Este valor es relativamente moderado. Menor ECM sugiere una relación más fuerte.
* **R²:** Un valor positivo indica que hay alguna relación entre la popularidad en Spotify y en Deezer, pero no es extremadamente fuerte.

#### 3. Hipótesis: Más playlists se relacionan con más streams.

* **Resultado:**
  * ECM: 23,374,000
  * R²: 0.575

**Conclusión:**

* **ECM:** Este valor es bastante alto, indicando que la hipótesis no es muy precisa.
* **R²:** Un valor alto sugiere que hay una relación significativa entre el número de playlists y los streams.

#### 4. Hipótesis: Más canciones de un artista en Spotify resultan en más streams totales.

* **Resultado:**
  * ECM: \~0 (muy bajo)
  * R²: 1.0 (muy alto)

**Conclusión:**

* **ECM:** Casi cero, lo que significa que la hipótesis es muy precisa.
* **R²:** Un valor de 1.0 indica una relación perfecta. Cuanto más alto, más fuerte es la relación.

<figure><img src="../../.gitbook/assets/image (34).png" alt=""><figcaption></figcaption></figure>

&#x20;**Dashboard 3**

**5. Hipótesis: Características de la música influyen en el éxito en Spotify.**

* **Resultados por Cada Característica:**
  * **bpm:** ECM: 0.00279, R²: 0.99995
  * **danceability:** ECM: 0.00180, R²: 0.99997
  * **valence:** ECM: 0.00292, R²: 0.99995
  * **energy:** ECM: 0.00336, R²: 0.99994
  * **acousticness:** ECM: 0.00149, R²: 0.99997
  * **instrumentalness:** ECM: 0.00180, R²: 0.99997
  * **liveness:** ECM: 0.00180, R²: 0.99997
  * **speechiness:** ECM: 0.00203, R²: 0.99997

**Conclusión:**

* Todos los ECM son muy bajos, lo que indica que estas características son fuertes predictores del éxito en Spotify.

Graficas de Dispersiòn:

1. correlation\_bpm (correlación con el tempo): -0.0024

Existe una correlación negativa muy débil entre el tempo (beats por minuto) de la música y el éxito en términos de streams en Spotify. En otras palabras, el tempo no parece tener una influencia significativa en la popularidad de la canción.

2. correlation\_dance (correlación con la capacidad de baile): -0.1055

Hay una correlación negativa moderada entre la capacidad de baile de la música y el éxito en streams. Esto podría sugerir que canciones menos bailables tienden a tener más streams en Spotify.

3. correlation\_valen (correlación con la valencia): -0.0408

Existe una correlación negativa débil entre la valencia (la positividad de la música) y el éxito en streams. Esto podría indicar que canciones con tonos más negativos pueden tener ligeramente más streams.

4. correlation\_energy (correlación con la energía): -0.0261

Hay una correlación negativa débil entre la energía de la música y el éxito en streams. Esto sugiere que canciones menos enérgicas podrían tener una tendencia ligeramente positiva hacia más streams.

5. correlation\_acoust (correlación con la acústica): -0.0045

Existe una correlación negativa muy débil entre las características acústicas de la música y el éxito en streams. Esto sugiere que el componente acústico no parece tener una influencia significativa en la popularidad en Spotify.

6. correlation\_instrum (correlación con la instrumentalidad): -0.0449

Hay una correlación negativa débil entre la instrumentalidad de la música y el éxito en streams. Esto podría indicar que canciones menos instrumentales podrían tener ligeramente más streams.

7. correlation\_liven (correlación con la vivacidad): -0.0483

Existe una correlación negativa débil entre la vivacidad de la música y el éxito en streams. Esto sugiere que canciones menos vivaces podrían tener ligeramente más streams.

8. correlation\_speech (correlación con la presencia de voz humana): -0.1123

Hay una correlación negativa moderada entre la presencia de voz humana en la música y el éxito en streams. Esto podría sugerir que canciones con menos presencia de voz humana podrían tener más streams en Spotify.

En general las correlaciones de las características son negativas lo que nos indica que aunque los streams en Spotify aumenten las características tienen a disminuir débilmente o no tienen un lineal entre las variables.

**Conclusión:** Es una hipótesis no es verdadera; ya que las correlaciones de las características son negativas débiles a moderada y no hay correlaciones fuertes por lo que  indica que no hay una relación entre las variables

<figure><img src="../../.gitbook/assets/image (35).png" alt=""><figcaption></figcaption></figure>

**Dashboard 3.1.**&#x20;

**Conclusión:** estas estadísticas proporcionan una descripción completa de la distribución de datos en las dos categorías. El promedio, la mediana y la moda ofrecen diferentes perspectivas sobre la tendencia central, mientras que la desviación estándar proporciona una medida de la dispersión de los datos. El máximo y el mínimo indican el rango de los valores observados.

\




\


