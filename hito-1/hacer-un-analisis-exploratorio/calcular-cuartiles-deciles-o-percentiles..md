# Calcular cuartiles, deciles o percentiles.

## Meta

Calcular cuartiles, deciles o percentiles.

## Objetivo

Crear categorías por cuartiles para las variables de características en BigQuery.

## Objetivo individual

* [x] Cada una debe calcular los cuartiles al menos para una variable y crear las categorías con IF.

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

## Conclusiones

* <mark style="background-color:green;">Se realiza la sentencia para crear las categorías de cada característica.</mark>
