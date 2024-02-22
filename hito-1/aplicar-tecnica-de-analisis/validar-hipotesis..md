# Validar hipótesis.

## Meta

Validar hipótesis.

## Objetivo

Validar las hipótesis levantadas a través de la correlación y scatter plot.

## Objetivo individual

* [x] Cada una debe calcular la correlación de las variables de una hipótesis y visualizar estos datos a través de un scatter plot y discutir los resultados si existe o no una correlación y si la hipótesis es verdadera.

```googlesql
SELECT
CORR(streams_limpo, bpm) AS correlation_bpm,
CORR(in_deezer_charts, in_spotify_charts) AS correlation_chartSpot,
CORR(streams_limpo, total_playlists) AS correlation_playStreams,
CORR(streams_total, artist_total) AS correlation_artistStreams,
FROM
  `proyecto-2-hipotesis-405315.tablaSpotify.view_master_left`
```

<figure><img src="../../.gitbook/assets/image (27).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (22).png" alt=""><figcaption></figcaption></figure>

## Hipótesis

* [x] Las canciones con un mayor BPM (Beats[^1] Por Minuto) tienen más éxito en términos de cantidad de streams[^2] en Spotify.

`correlation_bpm = -0.0024379081382716896`:

&#x20;La correlación esta muy cercana al cero lo que significa que como es tan débil la relación no esta clara entre estas dos variables Streams y bpm.

<figure><img src="../../.gitbook/assets/image (23).png" alt=""><figcaption></figcaption></figure>

<mark style="background-color:green;">Conclusión: Es una hipótesis no es verdadera; ya que su correlación es negativa débil esto nos da que no tienen una consistencia entre las dos variables Streams y bpm.</mark>

* [x] Las canciones más populares en el ranking de Spotify también tienen un comportamiento similar en otras plataformas como Deezer.

`correlation_chartSpot = 0.588402454531`:

Esta correlación es positiva. Indica una relación lineal moderadamente fuerte, donde una variable aumenta, la otra también tiende a aumentar.

<figure><img src="../../.gitbook/assets/image (24).png" alt=""><figcaption></figcaption></figure>

<mark style="background-color:green;">Conclusión: Es una hipótesis es verdadera; ya que su correlación es positiva fuerte esto nos da que tienen una consistencia entre las dos variables, si una aumenta la otra variable también aumenta.</mark>

* [x] La presencia de una canción en un mayor número de playlists se relaciona con un mayor número de streams.

`correlation_playStreams = 0778480103465`:

Esta correlación es positiva. Indica una relación lineal moderadamente fuerte, donde una variable aumenta, la otra también tiende a aumentar. Cuando la variable total\_playlists aumente la variable total\_streams aumenta.

<figure><img src="../../.gitbook/assets/image (28).png" alt=""><figcaption></figcaption></figure>

<mark style="background-color:green;">Conclusión: Es una hipótesis es verdadera; ya que su correlación es positiva fuerte esto nos da que tienen una consistencia entre las dos variables, si una aumenta la otra variable también aumenta.</mark>

* [x] Los artistas con un mayor número de canciones en Spotify tienen más streams totales.

`correlation_artistStre = 1.0`:

Esta correlación es positiva fuerte y nos indica que las dos variables están directamente relacionadas de manera lineal y que cuando una variable aumenta como artist\_total, la otra streams\_total también aumenta en una proporción constante. Una correlación de 1.0 implica una relación lineal positiva perfecta.

<figure><img src="../../.gitbook/assets/image (26).png" alt=""><figcaption></figcaption></figure>

<mark style="background-color:green;">Conclusión: Es una hipótesis es verdadera; ya que su correlación es positiva perfecta esto nos da que tienen una consistencia entre las dos variables, si una aumenta la otra variable también aumenta.</mark>&#x20;

* [x] Las características de la música influyen en el éxito en términos de cantidad de streams en Spotify.

<figure><img src="../../.gitbook/assets/image (20).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (21).png" alt=""><figcaption></figcaption></figure>

En general las correlaciones de las características son negativas lo que nos indica que aunque los streams en Spotify aumenten las características tienen a disminuir débilmente o no tienen un lineal entre las variables.

<mark style="background-color:green;">Conclusión: Es una hipótesis no es verdadera; ya que las correlaciones de las características son negativas débiles o están cercanas al cero lo que nos indica que no hay una relación entre las variables.</mark>

[^1]: ''Beats Per Minute'' (literalmente, pulsos por minuto). Es una unidad precisa que indica el tempo en música: se toma una figura de referencia (negra, corchea, etc.) como valor de pulso y se indica el número de pulsos que han de interpretarse por minuto.

[^2]: se refiere a cualquier contenido de medios, ya sea en vivo o grabado, que se puede disfrutar en computadoras y aparatos móviles a través de internet y en tiempo real. Los podcasts, webcasts, las películas, los programas de TV y los videos musicales son tipos comunes de contenido de streaming
