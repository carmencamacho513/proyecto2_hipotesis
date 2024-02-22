# Construir tablas auxiliares.

## Meta

Construir tablas auxiliares.

## Objetivo

Utilizar el comando WITH para crear una tabla temporal para calcular el total de canciones por artista solista.

## Objetivo individual

* [x] Una debe crear la tabla temporal con WITH y la otra auxiliar. En la próxima oportunidad que se necesite  crear la tabla temporal con WITH dentro de este hito, la que aún no haya implementado esta técnica deberá hacerlo.



<mark style="background-color:purple;">proyecto-2-hipotesis-405315.tablaSpotify.track\_in\_spotify</mark>

view\_limpo\_spotify

```sql
WITH
  song_artist AS (
  SELECT
    artist_s__name_limpos, 
    COUNT(*) AS total_song_artist,
    COUNT(streams_limpo) AS total_streams
  FROM
    `proyecto-2-hipotesis-405315.tablaSpotify.view_limpo_spotify`
  GROUP BY
    artist_s__name_limpos)
SELECT
*,
FROM
  `proyecto-2-hipotesis-405315.tablaSpotify.view_limpo_spotify` 
LEFT JOIN
  song_artist
USING(artist_s__name_limpos)
```

## Conclusiones

<mark style="background-color:green;">En este objetivo se realizo el comando WITH para crear tablas temporales.</mark>
