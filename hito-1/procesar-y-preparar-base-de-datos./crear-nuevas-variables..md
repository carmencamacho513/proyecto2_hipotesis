# Crear nuevas variables.

## Meta

Crear nuevas variables.

## Objetivo

Crear una variable de fecha released y una de participación total en playlists.

## Objetivo individual

* [x] Ambas deben poder crear una nueva variable, para que la que no tuvo la oportunidad de usar el comando CAST pueda poner en práctica este comando, debe crear la variable de fecha de lanzamiento completa usando concat y cast para que la fecha quede en el formato aaaa-mm-dd.

<mark style="background-color:purple;">proyecto-2-hipotesis-405315.tablaSpotify.track\_in\_spotify</mark>

```sql
SELECT
  *,
  DATE(CONCAT(CAST(released_year AS STRING), '-', CAST(released_month AS STRING), '-', CAST(released_day AS STRING)) ) AS lanzamiento_cancion
FROM
  `proyecto-2-hipotesis-405315.tablaSpotify.track_in_spotify`
```

```sql
SELECT
  *,
  in_spotify_playlists + in_apple_playlists + in_deezer_playlists AS total_playlists
FROM
  `proyecto-2-hipotesis-405315.tablaSpotify.view_master`
```

## Conclusiones

<mark style="background-color:green;">En este objetivo se realizo en la tabla Spotify con los comandos CONCAT y CAST en las variables realeased\_year, realeased\_month y realeased\_day.</mark>

<mark style="background-color:green;">Luego se realiza la suma de las tres variables playlists pero esto se realiza después de unir las tablas.</mark>
