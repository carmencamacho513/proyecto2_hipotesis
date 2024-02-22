# Calcular correlación entre variables.

## Meta

Calcular correlación entre variables.

## Objetivo

Calcular correlación en BigQuery a través de CORR.

## Objetivo individual

* [x] Cada una debe calcular la correlación entre dos variables continuas. Una puede calcular para streams y playlists y otra para streams y danceability\_\_.

```sql
SELECT
CORR(streams_limpo, in_spotify_playlists) AS correlation_playspo,
CORR(streams_limpo, in_apple_playlists) AS correlation_playapp,
CORR(streams_limpo, in_deezer_playlists) AS correlation_playdee,
CORR(streams_limpo, bpm) AS correlation_bpm,
CORR(streams_limpo, danceability__) AS correlation_dance,
CORR(streams_limpo, valence__) AS correlation_valen,
CORR(streams_limpo, energy__) AS correlation_energy,
CORR(streams_limpo, acousticness__) AS correlation_acoust,
CORR(streams_limpo, instrumentalness__) AS correlation_instrum,
CORR(streams_limpo, liveness__) AS correlation_liven,
CORR(streams_limpo, speechiness__) AS correlation_speech,
FROM
  `proyecto-2-hipotesis-405315.tablaSpotify.view_master_left`
```

<figure><img src="../../.gitbook/assets/image (20).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (21).png" alt=""><figcaption></figcaption></figure>

## Conclusiones

* <mark style="background-color:green;">Se realiza la sentencia para crear las correlaciones entre dos variables continuas las cuales fueron los streams con las diferentes características:</mark>&#x20;

1. `correlation_playspo = 0.78982215995506377`:  Es positivo y significa que entre más aumente los Streams más aumentan los Spotify\_Playlists.
2. `correlation_playapp = 0.72999552663790834`: Es positivo y significa que entre más aumente los Streams más aumentan los Apple\_Playlists.
3. `correlation_playdee = 0.608748221233361`: Es positivo pero moderado y significa que entre más aumente los Streams más aumentan moderadamente los Deezer\_Playlists.
4. `correlation_bpm = -0.0024379081382716896`: La correlación esta muy cercana al cero lo que significa que como es tan débil la relación no esta clara entre estas dos variables Streams y bpm.
5. `correlation_dance = -0.10545688369141912`: Es una correlación negativa, pero también esta muy débil, lo que significa que entre más aumente la variable Streams , la variable dance tiende a disminuir ligeramente.
6. `correlation_valen = -0.040831367495`: Es una correlación negativa, pero también esta muy débil, lo que significa que entre más aumente la variable Streams , la variable valen tiende a disminuir ligeramente.
7. `correlation_energy = -0.026051488364`: Es una correlación negativa, pero también esta muy débil, lo que significa que entre más aumente la variable Streams , la variable energy tiende a disminuir ligeramente.
8. `correlation_acoust = -0.0044846527006`: La correlación esta muy cercana al cero lo que significa que como es tan débil la relación no esta clara entre estas dos variables Streams y acoust.
9. `correlation_instrum = -0.04490247317`: Es una correlación negativa, pero también esta muy débil, lo que significa que entre más aumente la variable Streams , la variable instrum tiende a disminuir ligeramente.
10. `correlation_liven = -0.04833729577983`: Es una correlación negativa, pero también esta muy débil, lo que significa que entre más aumente la variable Streams , la variable liven tiende a disminuir ligeramente.
11. `correlation_speech = -0.1123329964033`: Es una correlación negativa, pero también moderada, lo que significa que entre más aumente la variable Streams , la variable speech tiende a disminuir moderadamente.

<figure><img src="../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (15).png" alt=""><figcaption></figcaption></figure>

