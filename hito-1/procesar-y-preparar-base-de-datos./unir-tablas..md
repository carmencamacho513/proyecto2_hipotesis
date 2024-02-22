# Unir tablas.

## Meta

Unir tablas.

## Objetivo

Unir tablas utilizando LEFT JOIN.

## Objetivo individual

* [x] Antes de unir las tablas, cada una debe crear la vista (view) con los datos limpios de cada tabla.Y al unir tablas usando LEFT JOIN, cada una debe hacer el JOIN de una tabla.

<mark style="background-color:purple;">proyecto-2-hipotesis-405315.tablaSpotify.track\_in\_competition</mark>

```sql
SELECT
  * 
FROM
  `proyecto-2-hipotesis-405315.tablaSpotify.track_in_competition`
WHERE
  track_id IS NOT NULL
  AND in_apple_playlists IS NOT NULL
  AND in_apple_charts IS NOT NULL
  AND in_deezer_playlists IS NOT NULL
  AND in_deezer_charts IS NOT NULL
  AND in_shazam_charts IS NOT NULL
```

<mark style="background-color:purple;">proyecto-2-hipotesis-405315.tablaSpotify.track\_in\_spotify</mark>

view\_spotify

```sql
SELECT
  * EXCEPT(track_name, artist_s__name, streams),
  REGEXP_REPLACE(track_name, r'[^a-zA-Z0-9 ]', '') AS track_name_limpos,
  REGEXP_REPLACE(artist_s__name, r'[^a-zA-Z0-9 ]', '') AS artist_s__name_limpos,
  CAST(streams AS INT64) streams_limpo,
  DATE(CONCAT(CAST(released_year AS STRING), '-', CAST(released_month AS STRING), '-', CAST(released_day AS STRING)) ) AS lanzamiento_cancion
FROM
  `proyecto-2-hipotesis-405315.tablaSpotify.track_in_spotify`
WHERE
  streams NOT LIKE '%BPM%'
```

view\_limpo\_spotify

```sql
SELECT
  *,
   CASE
    WHEN NTILE(4) OVER (ORDER BY streams_limpo) = 4 THEN 'Alto'
  ELSE
  'Bajo'
  END AS streams_category,
  COUNT(artist_s__name_limpos) OVER (PARTITION BY artist_s__name_limpos) AS artist_total,
  COUNT(streams_limpo) OVER (PARTITION BY artist_s__name_limpos) AS streams_total
FROM
  `proyecto-2-hipotesis-405315.tablaSpotify.view_spotify`;
```

<mark style="background-color:purple;">proyecto-2-hipotesis-405315.tablaSpotify.track\_technical\_info</mark>

```sql
WITH
  one AS (
  SELECT
    *
  FROM
    `proyecto-2-hipotesis-405315.tablaSpotify.track_technical_info`
  WHERE
    track_id IS NOT NULL
    AND bpm IS NOT NULL
    AND danceability__ IS NOT NULL
    AND valence__ IS NOT NULL
    AND energy__ IS NOT NULL
    AND acousticness__ IS NOT NULL
    AND instrumentalness__ IS NOT NULL
    AND liveness__ IS NOT NULL
    AND speechiness__ IS NOT NULL )
SELECT
  two.*EXCEPT(key, mode),
  CASE
    WHEN NTILE(4) OVER (ORDER BY two.bpm) = 4 THEN 'Alto'
  ELSE
  'Bajo'
END
  AS bpm_category,
  CASE
    WHEN NTILE(4) OVER (ORDER BY two.danceability__) = 4 THEN 'Alto'
  ELSE
  'Bajo'
END
  AS danceability_category,
  CASE
    WHEN NTILE(4) OVER (ORDER BY two.valence__) = 4 THEN 'Alto'
  ELSE
  'Bajo'
END
  AS valence_category,
  CASE
    WHEN NTILE(4) OVER (ORDER BY two.energy__) = 4 THEN 'Alto'
  ELSE
  'Bajo'
END
  AS energy_category,
  CASE
    WHEN NTILE(4) OVER (ORDER BY two.acousticness__) = 4 THEN 'Alto'
  ELSE
  'Bajo'
END
  AS acousticness_category,
  CASE
    WHEN NTILE(4) OVER (ORDER BY two.instrumentalness__) = 4 THEN 'Alto'
  ELSE
  'Bajo'
END
  AS instrumentalness_category,
  CASE
    WHEN NTILE(4) OVER (ORDER BY two.liveness__) = 4 THEN 'Alto'
  ELSE
  'Bajo'
END
  AS liveness_category,
  CASE
    WHEN NTILE(4) OVER (ORDER BY two.speechiness__) = 4 THEN 'Alto'
  ELSE
  'Bajo'
END
  AS speechiness_category
FROM
  `proyecto-2-hipotesis-405315.tablaSpotify.track_technical_info` AS two
LEFT JOIN
  one
USING
  (track_id)
```

## view\_master

<pre class="language-sql"><code class="lang-sql"><strong>SELECT
</strong>  *
FROM
  `proyecto-2-hipotesis-405315.tablaSpotify.view_limpo_spotify` 
LEFT JOIN
  `proyecto-2-hipotesis-405315.tablaSpotify.view_limpo_competition` 
USING
  (track_id)
LEFT JOIN
  `proyecto-2-hipotesis-405315.tablaSpotify.view_limpo_technical` 
USING
  (track_id)
</code></pre>

## Conclusiones

<mark style="background-color:green;">En este objetivo se realizo los view de cada tabla y en estas están las sentencia de objetivos anteriores y próximos a este objetivo.</mark>

<mark style="background-color:green;">La tabla view\_master es donde se realiza el LEFT JOIN.</mark>
