# Visualizar Distribución

## Meta

Visualizar distribución.

## Objetivo

Visualizar la distribución a través de un histograma.

## Objetivo individual

* [x] Cada una debe crear un histograma para la variable que estaba trabajando en la meta anterior.

<figure><img src="../../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

```python
import matplotlib.pyplot as plt
import pandas as pd

# Obtén los datos de Power BI 
data = dataset[['in_spotify_playlists']]

# Establece límites personalizados para el eje x
plt.xlim(min(data['in_spotify_playlists']), max(data['in_spotify_playlists']))

# Crea el histograma con bordes
plt.hist(data, bins=50, color='pink', alpha=0.7, edgecolor='blue')

# Calcula el promedio y la mediana
mean_value = data['in_spotify_playlists'].mean()
median_value = data['in_spotify_playlists'].median()

# Añade líneas verticales para el promedio y la mediana
plt.axvline(mean_value, color='red', linestyle='dashed', linewidth=2, label='Promedio')
plt.axvline(median_value, color='green', linestyle='dashed', linewidth=2, label='Mediana')

# Añade etiquetas a los ejes
plt.xlabel('Valor')
plt.ylabel('Frecuencia')

# Añade un título al histograma
plt.title('Histograma')

# Muestra el histograma
plt.legend()  # Muestra la leyenda con los nombres de las líneas verticales
plt.show()
```

<figure><img src="../../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

```python
import matplotlib.pyplot as plt
import pandas as pd

# Obtén los datos de Power BI 
data = dataset[['streams_limpo']]

# Establece límites personalizados para el eje x
plt.xlim(min(data['streams_limpo']), max(data['streams_limpo']))

# Crea el histograma con bordes
plt.hist(data, bins=50, color='blue', alpha=0.7, edgecolor='pink')

# Calcula el promedio y la mediana
mean_value = data['streams_limpo'].mean()
median_value = data['streams_limpo'].median()

# Añade líneas verticales para el promedio y la mediana
plt.axvline(mean_value, color='red', linestyle='dashed', linewidth=2, label='Promedio')
plt.axvline(median_value, color='green', linestyle='dashed', linewidth=2, label='Mediana')

# Añade etiquetas a los ejes
plt.xlabel('Valor')
plt.ylabel('Frecuencia')

# Añade un título al histograma
plt.title('Histograma')

# Muestra el histograma
plt.legend()  # Muestra la leyenda con los nombres de las líneas verticales
plt.show()
```

## Conclusiones

<mark style="background-color:green;">Se realiza los dos histogramas de Streams y Playlists en los cuales el sesgo es positivo y la distribución de los datos esta hacia la derecha; lo que nos lleva a que hay un conjunto de datos muy altos y hace que el promedio sea mucho mayor que la mediana.</mark>
