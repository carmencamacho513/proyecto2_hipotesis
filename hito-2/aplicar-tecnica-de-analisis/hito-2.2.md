# Hito 2.2

## Meta

Prueba de significancia.

## Objetivo

Comprender y aplicar test t o test de Wilcoxon (Mann-Whitney U).

## Objetivo individual

* [x] Cada una debe aplicar al menos una vez el test para una de las variables

```python
!pip install scipy

import numpy as np
import pandas as pd
from scipy.stats import mannwhitneyu
from scipy import stats
```

```python
group_bpm_alto = df.loc[df['bpm_category'] == "Alto"]['streams_limpo'].tolist()
group_bpm_bajo = df.loc[df['bpm_category'] == "Bajo"]['streams_limpo'].tolist()
statistic, pvalue = mannwhitneyu(group_bpm_alto, group_bpm_bajo)
print("Mann-Whitney U test result")
print("For bpm_category:")
print(f"Statistic: {round(statistic, 2)}")  
print(f"Pvalue: {round(pvalue, 4)}")
if pvalue < alpha:
    print("La diferencia entre las categorias es estadísticamente significativa (Rechazar hipótesis).")
else:
    print("La diferencia entre las categorías no es estadísticamente significativa (No se rechaza la hipótesis).")
    
group_dance_alto = df.loc[df['danceability_category'] == "Alto"]['streams_limpo'].tolist()
group_dance_bajo = df.loc[df['danceability_category'] == "Bajo"]['streams_limpo'].tolist()
statistic, pvalue = mannwhitneyu(group_dance_alto, group_dance_bajo)
print("Mann-Whitney U test result")
print("For danceability_category:")
print(f"Statistic: {round(statistic, 2)}")  
print(f"Pvalue: {round(pvalue, 4)}")
alpha = 0.05
if pvalue < alpha:
    print("La diferencia entre las categorias es estadísticamente significativa (Rechazar hipótesis).")
else:
    print("La diferencia entre las categorías no es estadísticamente significativa (No se rechaza la hipótesis).")
    
group_valen_alto = df.loc[df['valence_category'] == "Alto"]['streams_limpo'].tolist()
group_valen_bajo = df.loc[df['valence_category'] == "Bajo"]['streams_limpo'].tolist()
statistic, pvalue = mannwhitneyu(group_valen_alto, group_valen_bajo)
print("Mann-Whitney U test result")
print("For valence_category:")
print(f"Statistic: {round(statistic, 2)}")  
print(f"Pvalue: {round(pvalue, 4)}")
alpha = 0.05
if pvalue < alpha:
    print("La diferencia entre las categorias es estadísticamente significativa (Rechazar hipótesis).")
else:
    print("La diferencia entre las categorías no es estadísticamente significativa (No se rechaza la hipótesis).")
    
group_energy_alto = df.loc[df['energy_category'] == "Alto"]['streams_limpo'].tolist()
group_energy_bajo = df.loc[df['energy_category'] == "Bajo"]['streams_limpo'].tolist()
statistic, pvalue = mannwhitneyu(group_energy_alto, group_energy_bajo)
print("Mann-Whitney U test result")
print("For energy_category:")
print(f"Statistic: {round(statistic, 2)}")  
print(f"Pvalue: {round(pvalue, 4)}")
alpha = 0.05
if pvalue < alpha:
    print("La diferencia entre las categorias es estadísticamente significativa (Rechazar hipótesis).")
else:
    print("La diferencia entre las categorías no es estadísticamente significativa (No se rechaza la hipótesis).")
       
group_acoust_alto = df.loc[df['acousticness_category'] == "Alto"]['streams_limpo'].tolist()
group_acoust_bajo = df.loc[df['acousticness_category'] == "Bajo"]['streams_limpo'].tolist()
statistic, pvalue = mannwhitneyu(group_acoust_alto, group_acoust_bajo)
print("Mann-Whitney U test result")
print("For acousticness_category:")
print(f"Statistic: {round(statistic, 2)}")  
print(f"Pvalue: {round(pvalue, 4)}")
alpha = 0.05
if pvalue < alpha:
    print("La diferencia entre las categorias es estadísticamente significativa (Rechazar hipótesis).")
else:
    print("La diferencia entre las categorías no es estadísticamente significativa (No se rechaza la hipótesis).")
    
group_instru_alto = df.loc[df['instrumentalness_category'] == "Alto"]['streams_limpo'].tolist()
group_instru_bajo = df.loc[df['instrumentalness_category'] == "Bajo"]['streams_limpo'].tolist()
statistic, pvalue = mannwhitneyu(group_instru_alto, group_instru_bajo)
print("Mann-Whitney U test result")
print("For instrumentalness_category:")
print(f"Statistic: {round(statistic, 2)}")  
print(f"Pvalue: {round(pvalue, 4)}")
alpha = 0.05
if pvalue < alpha:
    print("La diferencia entre las categorias es estadísticamente significativa (Rechazar hipótesis).")
else:
    print("La diferencia entre las categorías no es estadísticamente significativa (No se rechaza la hipótesis).")
    
group_liven_alto = df.loc[df['liveness_category'] == "Alto"]['streams_limpo'].tolist()
group_liven_bajo = df.loc[df['liveness_category'] == "Bajo"]['streams_limpo'].tolist()
statistic, pvalue = mannwhitneyu(group_liven_alto, group_liven_bajo)
print("Mann-Whitney U test result")
print("For liveness_category:")
print(f"Statistic: {round(statistic, 2)}")  
print(f"Pvalue: {round(pvalue, 4)}")
alpha = 0.05
if pvalue < alpha:
    print("La diferencia entre las categorias es estadísticamente significativa (Rechazar hipótesis).")
else:
    print("La diferencia entre las categorías no es estadísticamente significativa (No se rechaza la hipótesis).")
    
group_speech_alto = df.loc[df['speechiness_category'] == "Alto"]['streams_limpo'].tolist()
group_speech_bajo = df.loc[df['speechiness_category'] == "Bajo"]['streams_limpo'].tolist()
statistic, pvalue = mannwhitneyu(group_speech_alto, group_speech_bajo)
print("Mann-Whitney U test result")
print("For speechiness_category:")
print(f"Statistic: {round(statistic, 2)}")  
print(f"Pvalue: {round(pvalue, 4)}")
alpha = 0.05
if pvalue < alpha:
    print("La diferencia entre las categorias es estadísticamente significativa (Rechazar hipótesis).")
else:
    print("La diferencia entre las categorías no es estadísticamente significativa (No se rechaza la hipótesis).")
```

## Conclusiones

Normalmente, un nivel de significación (denotado como α o alfa) de 0,05 funciona bien. Un nivel de significación de 0,05 indica un riesgo del 5 % de concluir que existe una diferencia cuando en realidad no la hay.

* Valor p ≤ α: La diferencia entre las medianas es estadísticamente significativa (Rechazar hipótesis).\
  \
  Si el valor p es menor o igual que el nivel de significación, la decisión es rechazar la hipótesis nula.
* Valor p > α: La diferencia entre las medianas no es estadísticamente significativa (No se rechaza la hipótesis).\
  \
  Si el valor p es mayor que el nivel de significación, la decisión es no rechazar la hipótesis nula.

Los resultados indican los hallazgos de las pruebas de Mann-Whitney U para diferentes categorías de variables:

1.  En español, la interpretación de los resultados sería la siguiente:

    1. **Para bpm\_category:**
       * Estadístico: 88039.0
       * Valor p: 0.4029
       * Interpretación: La diferencia entre las categorías no es estadísticamente significativa (No se rechaza la hipótesis nula). El valor p de 0.4029 es mayor que el nivel de significancia (usualmente 0.05), lo que sugiere que no hay suficiente evidencia para rechazar la hipótesis nula de que no hay diferencia significativa entre los grupos.
    2. **Para danceability\_category:**
       * Estadístico: 78271.0
       * Valor p: 0.0684
       * Interpretación: La diferencia entre las categorías no es estadísticamente significativa (No se rechaza la hipótesis nula). Aunque el valor p de 0.0684 está cerca del umbral de significancia, no es lo suficientemente bajo como para rechazar la hipótesis nula.
    3. **Para valence\_category:**
       * Estadístico: 80959.5
       * Valor p: 0.3044
       * Interpretación: La diferencia entre las categorías no es estadísticamente significativa (No se rechaza la hipótesis nula). El valor p de 0.3044 es mayor que el nivel de significancia, indicando que no hay suficiente evidencia para rechazar la hipótesis nula.
    4. **Para energy\_category:**
       * Estadístico: 81433.0
       * Valor p: 0.3363
       * Interpretación: La diferencia entre las categorías no es estadísticamente significativa (No se rechaza la hipótesis nula). El valor p de 0.3363 es mayor que el nivel de significancia, lo que sugiere que no hay suficiente evidencia para afirmar una diferencia significativa.
    5. **Para acousticness\_category:**
       * Estadístico: 83074.0
       * Valor p: 0.6066
       * Interpretación: La diferencia entre las categorías no es estadísticamente significativa (No se rechaza la hipótesis nula). El valor p de 0.6066 es alto y no alcanza el umbral de significancia, indicando falta de evidencia para rechazar la hipótesis nula.
    6. **Para instrumentalness\_category:**
       * Estadístico: 89163.5
       * Valor p: 0.2533
       * Interpretación: La diferencia entre las categorías no es estadísticamente significativa (No se rechaza la hipótesis nula). El valor p de 0.2533 es mayor que el nivel de significancia, indicando que no hay suficiente evidencia para afirmar una diferencia significativa.
    7. **Para liveness\_category:**
       * Estadístico: 81086.0
       * Valor p: 0.2909
       * Interpretación: La diferencia entre las categorías no es estadísticamente significativa (No se rechaza la hipótesis nula). El valor p de 0.2909 es mayor que el umbral de significancia, lo que sugiere que no hay suficiente evidencia para rechazar la hipótesis nula.
    8. **Para speechiness\_category:**
       * Estadístico: 75630.0
       * Valor p: 0.011
       * Interpretación: La diferencia entre las categorías es estadísticamente significativa (Se rechaza la hipótesis nula). El valor p de 0.011 es menor que el nivel de significancia, indicando que hay evidencia suficiente para rechazar la hipótesis nula y afirmar que hay una diferencia significativa entre los grupos en esta categoría.



