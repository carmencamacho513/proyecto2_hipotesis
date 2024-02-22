# Dashboard

## Meta

Representar datos a través de tabla resumen o scorecards.

## Objetivo

Crear una tabla resumen agrupada por la variable categórica (característica de la canción) sumarizando la variable continua streams (AVG, MEDIAN, SD).

## Objetivo individual

* [x] Cada una debe hacer una tabla resumen para cada una de las características estudiadas.

```python
!pip install matplotlib seaborn plotly
!pip install tabulate
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
import plotly.express as px
from tabulate import tabulate
```

```python
categories= ['bpm_category', 'danceability_category', 'valence_category',
                   'energy_category', 'acousticness_category',
                   'instrumentalness_category', 'liveness_category', 'speechiness_category']

result_category = {}

for category in categories:

    df_group_alto = df[df[f'{category}'] == "Alto"]
    df_group_bajo = df[df[f'{category}'] == "Bajo"]

    summary_alto = df_group_alto['streams_limpo'].describe()
    summary_bajo = df_group_bajo['streams_limpo'].describe()

    scorecard = pd.DataFrame({
        'Categoría': ['Alto', 'Bajo'],
        'Conteo': [summary_alto['count'], summary_bajo['count']],
        'Promedio': [summary_alto['mean'], summary_bajo['mean']],
        'Mediana': [summary_alto['50%'], summary_bajo['50%']],
        'Moda': [df_group_alto['streams_limpo'].mode().values[0], df_group_bajo['streams_limpo'].mode().values[0]],
        'Máximo': [summary_alto['max'], summary_bajo['max']],
        'Mínimo': [summary_alto['min'], summary_bajo['min']],
        'Desviación Estándar': [summary_alto['std'], summary_bajo['std']]
    })

    result_category[category] = scorecard

for category, scorecard in result_category.items():
    print(f"\nScorecard para {category}:\n")
    print(tabulate(scorecard, headers='keys', tablefmt='pretty', showindex=False))    
```

## Conclusiones

Estos resultados muestran estadísticas descriptivas para diferentes categorías de música, donde cada categoría está definida por ciertos atributos o características de las canciones. Aquí hay una interpretación general de cada tabla:

#### Scorecard para bpm\_category:

* Se divide en dos categorías: "Alto" y "Bajo" basado en el tempo (beats por minuto).
* El promedio, la mediana y la moda muestran características centrales.
* El máximo y mínimo indican la variabilidad en los datos.
* La desviación estándar mide la dispersión de los datos alrededor del promedio.

#### Scorecard para danceability\_category:

* Similar al anterior, pero basado en la "bailable" de las canciones.
* "Alto" indica canciones más bailables, mientras que "Bajo" indica menos bailables.

#### Scorecard para valence\_category:

* Se refiere a la positividad o negatividad de la canción.
* "Alto" implica canciones más positivas, y "Bajo" implica menos positivas.

#### Scorecard para energy\_category:

* Mide la energía de la canción.
* "Alto" indica canciones más energéticas, mientras que "Bajo" indica menos energéticas.

#### Scorecard para acousticness\_category:

* Refleja cuánto de la canción es acústica.
* "Alto" implica canciones más acústicas, y "Bajo" implica menos acústicas.

#### Scorecard para instrumentalness\_category:

* Se relaciona con la probabilidad de que la canción sea instrumental.
* "Alto" sugiere canciones más instrumentales, y "Bajo" sugiere menos instrumentales.

#### Scorecard para liveness\_category:

* Indica si la canción fue grabada en vivo o no.
* "Alto" implica mayor probabilidad de ser en vivo, "Bajo" indica menor probabilidad.

#### Scorecard para speechiness\_category:

* Relacionado con la presencia de palabras habladas en la canción.
* "Alto" sugiere canciones con más contenido hablado, "Bajo" sugiere menos.

Estas tablas proporcionan información valiosa sobre la distribución y variabilidad de características específicas en cada categoría de música, lo que puede ser útil para entender y clasificar canciones según sus atributos.







\




