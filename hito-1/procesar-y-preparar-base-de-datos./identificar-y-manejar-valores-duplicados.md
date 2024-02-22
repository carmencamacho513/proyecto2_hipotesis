# Identificar y manejar valores duplicados

## Meta

Identificar y manejar valores duplicados

## Objetivo

Identificar duplicados a través de comandos SQL COUNT, GROUP BY, HAVING

## Objetivo individual

* [x] Cada una debe consultar los duplicados de al menos una tabla, por ejemplo, una consulta los duplicados de track_technical_info, la otra de track_in_competition y ambas de track_in_spotify.

<mark style="background-color:purple;">proyecto-2-hipotesis-405315.tablaSpotify.track\_in\_competition</mark>

```sql
SELECT
  in_apple_playlists,
  in_apple_charts,
  in_deezer_playlists,
  in_deezer_charts,
  in_shazam_charts, COUNT (*) AS cantidad_double
FROM
  `proyecto-2-hipotesis-405315.tablaSpotify.track_in_competition`
GROUP BY
  in_apple_playlists,
  in_apple_charts,
  in_deezer_playlists,
  in_deezer_charts,
  in_shazam_charts
HAVING
  COUNT(*) > 1
```

<mark style="background-color:purple;">proyecto-2-hipotesis-405315.tablaSpotify.track\_in\_spotify</mark>

```sql
SELECT
  track_name,
  artist_s__name, COUNT (*) AS cantidad_double
FROM
  `proyecto-2-hipotesis-405315.tablaSpotify.track_in_spotify`
GROUP BY
  track_name,
  artist_s__name
HAVING
  COUNT(*) > 1
```

<mark style="background-color:purple;">proyecto-2-hipotesis-405315.tablaSpotify.track\_technical\_info</mark>

```sql
SELECT
 `key`,
  mode, COUNT (*) AS cantidad_double
FROM
  `proyecto-2-hipotesis-405315.tablaSpotify.track_technical_info`
GROUP BY
  `key`,
  mode
HAVING
  COUNT(*) > 1

```

## Conclusiones

<mark style="background-color:green;">En este objetivo se realizo en las tres tablas la búsqueda de valores duplicados y se utilizo los comandos COUNT, GROUP BY, HAVING.</mark>

<mark style="background-color:green;">proyecto-2-hipotesis-405315.tablaSpotify.track\_in\_competition: Se encuentra varios valores duplicados por ejecutar el código, pero no se puede en ninguna variable tomarse en cuenta estos resultados; ya que los valores de estas variables no son únicos y por lo tanto van a tener varios valores iguales.</mark>

<mark style="background-color:green;">proyecto-2-hipotesis-405315.tablaSpotify.track\_in\_spotify: Se encuentra varios valores duplicados por ejecutar el código, pero solo los valores de las variables track\_name, artist\_s\_\_name se puede determinar valores duplicados de resto de columnas no son valores únicos por lo tanto van a tener varios valores iguales.</mark>

<mark style="background-color:green;">proyecto-2-hipotesis-405315.tablaSpotify.track\_technical\_info:  Se encuentra varios valores duplicados por ejecutar el código, pero no se puede en ninguna variable tomarse en cuenta estos resultados; ya que los valores de estas variables no son únicos y por lo tanto van a tener varios valores iguales.</mark>
