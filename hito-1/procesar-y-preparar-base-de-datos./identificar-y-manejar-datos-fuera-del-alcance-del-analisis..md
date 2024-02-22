# Identificar y manejar datos fuera del alcance del análisis.

## Meta

Identificar y manejar datos fuera del alcance del análisis.

## Objetivo

Manejar variables que no son útiles para el análisis a través de comandos SQL SELECT EXCEPT

## Objetivo individual

* [x] Cada una debe analizar las variables fuera de alcance de al menos una tabla, por ejemplo, una consulta los de track_technical_info, la otra de track_in_competition y ambas de track_in_spotify.

<mark style="background-color:purple;">proyecto-2-hipotesis-405315.tablaSpotify.track\_in\_competition</mark>

```sql
SELECT
*EXCEPT(in_shazam_charts)
FROM
  `proyecto-2-hipotesis-405315.tablaSpotify.track_in_competition`

```

<mark style="background-color:purple;">proyecto-2-hipotesis-405315.tablaSpotify.track\_in\_spotify</mark>

```sql
SELECT
*EXCEPT(in_spotify_charts)
FROM
  `proyecto-2-hipotesis-405315.tablaSpotify.track_in_spotify
```

<mark style="background-color:purple;">proyecto-2-hipotesis-405315.tablaSpotify.track\_technical\_info</mark>

```sql
SELECT
*EXCEPT(key, mode)
FROM
  `proyecto-2-hipotesis-405315.tablaSpotify.track_technical_info`
```

## Conclusiones

<mark style="background-color:green;">En este objetivo se realizo en las tres tablas la sentencia y se utilizo el comando SELECT EXCEPT</mark>

<mark style="background-color:green;">proyecto-2-hipotesis-405315.tablaSpotify.track\_in\_competition: En esta tabla en la variable "in\_shazam\_charts" se realiza el código ya que esta columna presenta varios valores nulos y no determinan alguna significancia en el proceso de investigación.</mark>

<mark style="background-color:green;">proyecto-2-hipotesis-405315.tablaSpotify.track\_in\_spotify:  En esta tabla en la variable "in\_spotify\_charts" se realiza el código para hacer el ejercicio peo en esta tabla no se hace efectivo la sentencia; ya que las variables de esta tabla son determinantes en la investigación.</mark>

<mark style="background-color:green;">proyecto-2-hipotesis-405315.tablaSpotify.track\_technical\_info:  En esta tabla en las variables "key, mode" se realiza el código ya que estas columnas es información poco relevante para el proceso de investigación.</mark>
