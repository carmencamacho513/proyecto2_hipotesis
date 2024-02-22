# Comprobar y cambiar tipo de dato.

## Meta

Comprobar y cambiar tipo de dato.

## Objetivo

Utilizar CAST para modificar el tipo de dato.

## Objetivo individual

* [x] Una debe poder cambiar el tipo de dato de la variable streams y la otra debe brindar soporte. En el próximo objetivo, cuando creemos una nueva variable de fecha, tendrás la oportunidad de poner en práctica el comando CAST nuevamente.

<mark style="background-color:purple;">proyecto-2-hipotesis-405315.tablaSpotify.track\_in\_spotify</mark>

```sql
SELECT
streams
FROM
  `proyecto-2-hipotesis-405315.tablaSpotify.track_in_spotify`
  WHERE streams NOT LIKE '%BPM%'
```

```sql
SELECT
  streams,
  SAFE_CAST(streams AS INT64) AS streams_entero
FROM
  `proyecto-2-hipotesis-405315.tablaSpotify.track_in_spotify`
```

## Conclusiones

<mark style="background-color:green;">En este objetivo se realizo en la tabla Spotify en la variable streams la cual es String y se va a pasar a Integer,, pero antes en una fila aparece una dato discrepante se realiza la corrección de este dato con el comando NOT LIKE.</mark>

<mark style="background-color:green;">Luego ya se realiza la sentencia de pasar de string a Integer con el comando CAST.</mark>&#x20;
