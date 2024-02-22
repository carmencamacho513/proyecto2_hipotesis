# 🎧 Herramientas, lenguajes e insumos

#### 1.1 Herramientas y/o plataformas <a href="#id-11herramientasyoplataformas" id="id-11herramientasyoplataformas"></a>

En este proyecto vas a utilizar una herramienta de Google llamada BigQuery, para el manejo de los datos, una herramienta de Microsoft llamada Power BI para la visualización de los datos y Google Colab para realizar análisis en Python (hitos 2 y 3):

* BigQuery
* Power BI
* Google Colab

#### 1.2 Lenguajes <a href="#id-12lenguajes" id="id-12lenguajes"></a>

Utilizarás el lenguaje SQL en BigQuery y Python en Google Colab. Nota la diferencia entre “lenguaje” (SQL o Python) y “herramienta” (BigQuery o Colab), en la sección de recursos de cada meta encontrarás cursos de SQL y tutoriales de Python que pueden ayudarte a comprender estos lenguajes y cómo usarlos en estas herramientas.

#### 1.3 Insumos <a href="#id-13insumos" id="id-13insumos"></a>

Este conjunto de datos contiene datos sobre las canciones más reproducidas en Spotify en 2023. Los datos se dividen en 3 tablas, la primera sobre el rendimiento de cada canción en Spotify, la segunda con el rendimiento en otras plataformas como Deezer o Apple Music, y la tercera con las características de estas canciones.

El conjunto de datos está disponible para download en este enlace [dataset](https://drive.google.com/file/d/11W1wfljCoRKy1Uk5R65LHWmh2mtCtMGV/view?usp=share\_link), ten en cuenta que es un archivo comprimido, tendrás que descomprimirlo para acceder a los archivos con los datos.

A continuación, puedes consultar la descripción de las variables que componen las tablas de este conjunto de datos:

**Track\_ in\_ spotify**

* **track\_id**: Identificador único de la canción. Es un número entero de 7 dígitos que no se repite
* **track\_name**: Nombre de la canción
* **artist(s)\_name**: Nombre del artista(s) de la canción
* **artist\_count**: Número de artistas que contribuyen a la canción.
* **released\_year**: Año en que se lanzó la canción.
* **released\_month**: Mes en el que se lanzó la canción.
* **released\_day**: Día del mes en que se lanzó la canción.
* **in\_ spotify\_ playlists**: Número de listas de reproducción de Spotify en las que está incluida la canción
* **in\_ spotify\_ charts**: Presencia y ranking de la canción en las listas de Spotify
* **streams**: Número total de transmisiones en Spotify. Representa la cantidad de veces que la canción fue escuchada.

**Track\_ in\_ competition**

* **track\_id**: Identificador único de la canción. Es un número entero de 7 dígitos que no se repite
* **in\_ apple\_ playlists**: número de listas de reproducción de Apple Music en las que está incluida la canción
* **in\_ apple\_ charts**: Presencia y rango de la canción en las listas de Apple Music
* **in\_ deezer\_ playlists**: Número de listas de reproducción de Deezer en las que está incluida la canción
* **in\_ deezer\_ charts**: Presencia y rango de la canción en las listas de Deezer
* **in\_ shazam\_ charts**: Presencia y rango de la canción en las listas de Shazam

**Track\_ technical\_ info**

* **track\_id**: Identificador único de la canción. Es un número entero de 7 dígitos que no se repite
* **bpm**: Pulsaciones por minuto, una medida del tiempo de la canción.
* **key**: Clave musical de la canción
* **mode**: Modo de la canción (mayor o menor)
* **danceability\_%**: Porcentaje que indica qué tan adecuada es la canción para bailar
* **valence\_%**: Positividad del contenido musical de la canción.
* **energy%**: Nivel de energía percibido de la canción.
* **acusticness\_%**: Cantidad de sonido acústico en la canción.
* **instrumentality\_%**: Cantidad de contenido instrumental en la canción.
* **liveness\_%**: Presencia de elementos de actuación en vivo.
* **Speechiness\_%**: Cantidad de palabras habladas en la canción.

\


\
