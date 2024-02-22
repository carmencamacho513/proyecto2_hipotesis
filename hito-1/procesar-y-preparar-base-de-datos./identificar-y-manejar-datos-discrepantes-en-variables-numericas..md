# Identificar y manejar datos discrepantes en variables numéricas.

## Meta

Identificar y manejar datos discrepantes en variables numéricas.

## Objetivo

Utilizar comandos como MAX, MIN y AVG para identificar valores discrepantes en variables numéricas.

## Objetivo individual

* [x] Cada una debe analizar las variables numéricas de al menos una tabla, por ejemplo, una consulta los de track_technical_info, la otra de track_in_competition y ambas de track_in_spotify.

<mark style="background-color:purple;">proyecto-2-hipotesis-405315.tablaSpotify.track\_in\_competition</mark>

```sql
SELECT
  (MAX(in_apple_playlists),
    MIN(in_apple_playlists),
    AVG(in_apple_playlists)) AS F1,
  (MAX(in_apple_charts),
    MIN(in_apple_charts),
    AVG(in_apple_charts)) AS F2,
  (MAX(in_deezer_playlists),
    MIN(in_deezer_playlists),
    AVG(in_deezer_playlists)) AS F3,
  (MAX(in_deezer_charts),
    MIN(in_deezer_charts),
    AVG(in_deezer_charts)) AS F4,
  (MAX(in_shazam_charts),
    MIN(in_shazam_charts),
    AVG(in_shazam_charts)) AS F5
FROM
  `proyecto-2-hipotesis-405315.tablaSpotify.track_in_competition`
```

<mark style="background-color:purple;">proyecto-2-hipotesis-405315.tablaSpotify.track\_in\_spotify</mark>

```sql
SELECT
  (MAX(artist_count),
    MIN(artist_count),
    AVG(artist_count)) AS F1,
  (MAX(released_year),
    MIN(released_year),
    AVG(released_year)) AS F2,
  (MAX(released_month),
    MIN(released_month),
    AVG(released_month)) AS F3,
  (MAX(released_day),
    MIN(released_day),
    AVG(released_day)) AS F4,
  (MAX(in_spotify_playlists),
    MIN(in_spotify_playlists),
    AVG(in_spotify_playlists)) AS F5,
  (MAX(in_spotify_charts),
    MIN(in_spotify_charts),
    AVG(in_spotify_charts)) AS F6
FROM
  `proyecto-2-hipotesis-405315.tablaSpotify.track_in_spotify`
```

<mark style="background-color:purple;">proyecto-2-hipotesis-405315.tablaSpotify.track\_technical\_info</mark>

```sql
SELECT
  (MAX(bpm),
    MIN(bpm),
    AVG(bpm)) AS F1,
  (MAX(danceability__),
    MIN(danceability__),
    AVG(danceability__)) AS F2,
  (MAX(valence__),
    MIN(valence__),
    AVG(valence__)) AS F3,
  (MAX(energy__),
    MIN(energy__),
    AVG(energy__)) AS F4,
  (MAX(acousticness__),
    MIN(acousticness__),
    AVG(acousticness__)) AS F5,
  (MAX(instrumentalness__),
    MIN(instrumentalness__),
    AVG(instrumentalness__)) AS F6,
  (MAX(liveness__),
    MIN(liveness__),
    AVG(liveness__)) AS F7,
  (MAX(speechiness__),
    MIN(speechiness__),
    AVG(speechiness__)) AS F8
FROM
  `proyecto-2-hipotesis-405315.tablaSpotify.track_technical_info`
```

## Conclusiones

<mark style="background-color:green;">En este objetivo se realizo en las tres tablas en las variables numéricas y se utilizo los comandos  MAX, MIN y AVG; para encontrar datos discrepantes; no se encuentra datos discrepantes en las variables numéricas.</mark>
