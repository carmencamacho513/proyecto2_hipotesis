# Gráfico de dispersión (Scatter Plot)

## Meta

representar datos a través de gráficos o visuales avanzados.

## Objetivo

Crear un gráfico de dispersión (scatter plot) con la reta obtenida de la regresión linear simple..

## Objetivo individual

* [x] Cada una debe hacer al menos una vez este gráfico, por ejemplo una hace para streams por bpm y la otra streams por total\_playlists.
* [x] Lo importante también es discutir los resultados y explorar las otras variables.

```python
!pip install scipy
!pip install matplotlib seaborn plotly
!pip install scikit-learn
!pip install pydataset
!pip install tabulate
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
import plotly.express as px
import numpy as np

from sklearn.model_selection import train_test_split
from sklearn.linear_model import LinearRegression
from sklearn import metrics
from pydataset import data
from tabulate import tabulate
from sklearn.ensemble import RandomForestRegressor
```

**Hipótesis Las canciones con un mayor BPM (Beats Por Minuto) tienen más éxito en términos de streams en Spotify**

```python
plt.scatter(X_test, y_test, color='Salmon')
plt.plot(X_test, predicciones, color='MediumVioletRed', linewidth=3)
plt.xlabel('Streams Limpo')
plt.ylabel('BPM')
plt.title('Regresión Lineal Simple')
plt.show()
```

**Hipótesis Las canciones más populares en el ranking de Spotify también tienen un comportamiento similar en otras plataformas como Deezer**

```python
plt.scatter(X_test, y_test, color='MediumAquamarine')
plt.plot(X_test, predicciones, color='Indigo', linewidth=3)
plt.xlabel('in_deezer_charts')
plt.ylabel('in_spotify_charts')
plt.title('Regresión Lineal Simple')
plt.show()
```

**Hipótesis La presencia de una canción en un mayor número de playlists se relaciona con un mayor número de streams**

```python
plt.scatter(X_test, y_test, color='DarkKhaki')
plt.plot(X_test, predicciones, color='PaleVioletRed', linewidth=3)
plt.xlabel('streams_limpo')
plt.ylabel('total_playlists')
plt.title('Regresión Lineal Simple')
plt.show()
```

**Hipótesis Los artistas con un mayor número de canciones en Spotify tienen más streams totales.**

```python
plt.scatter(X_test, y_test, color='Magenta')
plt.plot(X_test, predicciones, color='DodgerBlue', linewidth=3)
plt.xlabel('streams_total')
plt.ylabel('artist_total')
plt.title('Regresión Lineal Simple')
plt.show()
```

##



####





\




