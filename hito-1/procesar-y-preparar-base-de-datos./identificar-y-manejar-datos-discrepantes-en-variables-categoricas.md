# Identificar y manejar datos discrepantes en variables categóricas

## Meta

Identificar y manejar datos discrepantes en variables categóricas

## Objetivo

Utilizar comandos de manejo de string, como LIKE o REGEXP

## Objetivo individual

* [x] Cada persona debe usar el comando para ajustar las variables de tipo string al menos una vez, en este objetivo pueden trabajar en la misma tabla.

<mark style="background-color:purple;">proyecto-2-hipotesis-405315.tablaSpotify.track\_in\_spotify</mark>

```sql
SELECT
  *,
  REGEXP_REPLACE(track_name, r'[^a-zA-Z0-9 ]', '') AS track_name_limpos,
  REGEXP_REPLACE(artist_s__name, r'[^a-zA-Z0-9 ]', '') AS artist_s__name_limpos
FROM
  `proyecto-2-hipotesis-405315.tablaSpotify.track_in_spotify`
```

## Conclusiones

<mark style="background-color:green;">En este objetivo se realizo en la tabla de spotify en las columnas track\_name y artist\_s\_name que son variables categóricas y se encontró datos discrepantes; se utilizo los comandos REGEXP en un próximo objetivo se realiza el comando LIKE.</mark>
