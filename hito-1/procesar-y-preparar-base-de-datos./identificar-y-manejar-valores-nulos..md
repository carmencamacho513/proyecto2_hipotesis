# Identificar y manejar valores nulos.

## Meta

Identificar y manejar valores nulos.

## Objetivo

Identificar nulos a través de comandos SQL COUNT, WHERE y IS NULL.

## Objetivo individual

* [x] Cada una debe consultar los nulos de al menos una tabla, por ejemplo, una consulta los nulos track_technical_info, la otra de track_in_competition y ambas de track_in_spotify.

<mark style="background-color:purple;">proyecto-2-hipotesis-405315.tablaSpotify.track\_in\_competition</mark>

```sql
SELECT
  COUNT(track_id),
  COUNT(in_apple_playlists),
  COUNT(in_apple_charts),
  COUNT(in_deezer_playlists),
  COUNT(in_deezer_charts),
  COUNT(in_shazam_charts)
FROM
  `proyecto-2-hipotesis-405315.tablaSpotify.track_in_competition`
WHERE
  track_id IS NOT NULL
  OR in_apple_playlists IS NOT NULL
  OR in_apple_charts IS NOT NULL
  OR in_deezer_playlists IS NOT NULL
  OR in_deezer_charts IS NOT NULL
  OR in_shazam_charts IS NOT NULL 
```

<mark style="background-color:purple;">proyecto-2-hipotesis-405315.tablaSpotify.track\_in\_spotify</mark>

```sql
SELECT
  COUNT(track_id),
  COUNT(track_name),
  COUNT(artist_s__name),
  COUNT(artist_count),
  COUNT(released_year),
  COUNT(released_month),
  COUNT(released_day),
  COUNT(in_spotify_playlists),
  COUNT(in_spotify_charts),
  COUNT(streams)
FROM
  `proyecto-2-hipotesis-405315.tablaSpotify.track_in_spotify`
WHERE
  track_id IS NOT NULL
  OR track_name IS NOT NULL
  OR artist_s__name IS NOT NULL
  OR artist_count IS NOT NULL
  OR released_year IS NOT NULL
  OR released_month IS NOT NULL 
  OR released_day IS NOT NULL
  OR in_spotify_playlists IS NOT NULL
  OR in_spotify_charts IS NOT NULL
  OR streams IS NOT NULL 
```

<mark style="background-color:purple;">proyecto-2-hipotesis-405315.tablaSpotify.track\_technical\_info</mark>

```sql
SELECT
  COUNT(track_id),
  COUNT(bpm),
  COUNT(key),
  COUNT(mode),
  COUNT(danceability__),
  COUNT(valence__),
  COUNT(energy__),
  COUNT(acousticness__),
  COUNT(instrumentalness__),
  COUNT(liveness__),
  COUNT(speechiness__)
FROM
  `proyecto-2-hipotesis-405315.tablaSpotify.track_technical_info`
WHERE
  track_id IS NOT NULL
  OR bpm IS NOT NULL
  OR key IS NOT NULL
  OR mode IS NOT NULL
  OR danceability__ IS NOT NULL
  OR valence__ IS NOT NULL 
  OR energy__ IS NOT NULL
  OR acousticness__ IS NOT NULL
  OR instrumentalness__ IS NOT NULL
  OR liveness__ IS NOT NULL
  OR speechiness__ IS NOT NULL 
```

## Conclusiones

<mark style="background-color:green;">En este objetivo se realizo en las tres tablas la búsqueda de valores nulos y seutilizo los comando COUNT, WHERE y IS NULL.</mark>

<mark style="background-color:green;">proyecto-2-hipotesis-405315.tablaSpotify.track\_in\_competition: Se encuentra en la variable "in\_shazam\_charts" 50 nulos</mark>

<mark style="background-color:green;">proyecto-2-hipotesis-405315.tablaSpotify.track\_in\_spotify: no se encuentra nulos.</mark>

<mark style="background-color:green;">proyecto-2-hipotesis-405315.tablaSpotify.track\_technical\_info: se encuentra en la variable "key" 95 nulos.</mark>
