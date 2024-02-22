# Regresión lineal.

## Meta

Regresión lineal.

## Objetivo

Entendimiento más profundizado de la relación lineal entre dos variables continuas.

## Objetivo individual

* [x] Cada una debe hacer al menos una vez este análisis, por ejemplo una hace para streams por bpm y la otra streams por total\_playlists.
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
X = df['streams_limpo'].values.reshape(-1, 1)
y = df['bpm'].values

X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

modelo = LinearRegression()
modelo.fit(X_train, y_train)
```

```python
predicciones = modelo.predict(X_test)

print('Error cuadrático medio:', metrics.mean_squared_error(y_test, predicciones))
print('Coeficiente de determinación (R²):', metrics.r2_score(y_test, predicciones))
```

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
X = df['in_deezer_charts'].values.reshape(-1, 1)
y = df['in_spotify_charts'].values

X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

modelo = LinearRegression()
modelo.fit(X_train, y_train)
```

```python
predicciones = modelo.predict(X_test)

print('Error cuadrático medio:', metrics.mean_squared_error(y_test, predicciones))
print('Coeficiente de determinación (R²):', metrics.r2_score(y_test, predicciones))
```

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
X = df['streams_limpo'].values.reshape(-1, 1)
y = df['total_playlists'].values

X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

modelo = LinearRegression()
modelo.fit(X_train, y_train)
```

```python
predicciones = modelo.predict(X_test)

print('Error cuadrático medio:', metrics.mean_squared_error(y_test, predicciones))
print('Coeficiente de determinación (R²):', metrics.r2_score(y_test, predicciones))
```

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
X = df['streams_total'].values.reshape(-1, 1)
y = df['artist_total'].values

X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

modelo = LinearRegression()
modelo.fit(X_train, y_train)
```

```python
predicciones = modelo.predict(X_test)

print('Error cuadrático medio:', metrics.mean_squared_error(y_test, predicciones))
print('Coeficiente de determinación (R²):', metrics.r2_score(y_test, predicciones))
```

```python
plt.scatter(X_test, y_test, color='Magenta')
plt.plot(X_test, predicciones, color='DodgerBlue', linewidth=3)
plt.xlabel('streams_total')
plt.ylabel('artist_total')
plt.title('Regresión Lineal Simple')
plt.show()
```

**Hipótesis Las características de la música influyen en el éxito en términos de streams en Spotify**

```python
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

categories = ['bpm', 'danceability__', 'valence__', 'energy__', 'acousticness__', 'instrumentalness__', 'liveness__', 'speechiness__']
result_category = []

for category in categories:

    df_group_ECM = df[df[category] == "ECM"]
    df_group_R2 = df[df[category] == "R2"]

    summary_ECM = df_group_ECM['streams_limpo'].describe()
    summary_R2 = df_group_R2['streams_limpo'].describe()

    # Assuming you have a trained model (replace 'RandomForestRegressor()' with your actual model)
    modelo = RandomForestRegressor()
    modelo.fit(X_train, y_train)

    # Make predictions
    predicciones = modelo.predict(X_test)

    # Calculate metrics
    mse_ECM = metrics.mean_squared_error(y_test, predicciones)
    r2_ECM = metrics.r2_score(y_test, predicciones)

    # Combine results in a list
    result_category.append({
        'Categoría': category,
        'Error Cuadrático Medio (ECM)': mse_ECM,
        'Coeficiente de determinación (R²) ECM': r2_ECM,
    })

# Create a DataFrame for the combined scorecard
scorecard = pd.DataFrame(result_category)

# Print the combined scorecard
print(f"\nScorecard combinado:\n")
print(tabulate(scorecard, headers='keys', tablefmt='pretty', showindex=False))
```

## Conclusiones

¡Claro! Voy a explicar cada hipótesis y sus resultados de una manera más fácil de entender:

#### 1. Hipótesis: Canciones con mayor BPM tienen más éxito en Spotify.

* **Resultado:**
  * Error Cuadrático Medio (ECM): 704.12
  * Coeficiente de Determinación (R²): -0.0164

**Explicación:**

* **ECM:** Cuanto menor sea el ECM, mejor. En este caso, el valor no es extremadamente bajo, lo que indica que la hipótesis no es muy precisa.
* **R²:** Un valor negativo sugiere que la relación entre el BPM y el éxito en Spotify no es clara ni fuerte.

#### 2. Hipótesis: Canciones populares en Spotify tienen comportamiento similar en Deezer.

* **Resultado:**
  * ECM: 188.44
  * R²: 0.2423

**Explicación:**

* **ECM:** Este valor es relativamente moderado. Menor ECM sugiere una relación más fuerte.
* **R²:** Un valor positivo indica que hay alguna relación entre la popularidad en Spotify y en Deezer, pero no es extremadamente fuerte.

#### 3. Hipótesis: Más playlists se relacionan con más streams.

* **Resultado:**
  * ECM: 23,374,000
  * R²: 0.575

**Explicación:**

* **ECM:** Este valor es bastante alto, indicando que la hipótesis no es muy precisa.
* **R²:** Un valor alto sugiere que hay una relación significativa entre el número de playlists y los streams.

#### 4. Hipótesis: Más canciones de un artista en Spotify resultan en más streams totales.

* **Resultado:**
  * ECM: \~0 (muy bajo)
  * R²: 1.0 (muy alto)

**Explicación:**

* **ECM:** Casi cero, lo que significa que la hipótesis es muy precisa.
* **R²:** Un valor de 1.0 indica una relación perfecta. Cuanto más alto, más fuerte es la relación.

#### 5. Hipótesis: Características de la música influyen en el éxito en Spotify.

* **Resultados por Cada Característica:**
  * **bpm:** ECM: 0.00279, R²: 0.99995
  * **danceability:** ECM: 0.00180, R²: 0.99997
  * **valence:** ECM: 0.00292, R²: 0.99995
  * **energy:** ECM: 0.00336, R²: 0.99994
  * **acousticness:** ECM: 0.00149, R²: 0.99997
  * **instrumentalness:** ECM: 0.00180, R²: 0.99997
  * **liveness:** ECM: 0.00180, R²: 0.99997
  * **speechiness:** ECM: 0.00203, R²: 0.99997

**Explicación:**

* Todos los ECM son muy bajos, lo que indica que estas características son fuertes predictores del éxito en Spotify.

En resumen, las hipótesis 3 y 4 tienen relaciones más fuertes según los valores de R², mientras que las hipótesis 1 y 2 muestran relaciones más débiles. La hipótesis 5 sugiere que las características específicas de la música son fuertes predictores del éxito en términos de streams en Spotify.

\
