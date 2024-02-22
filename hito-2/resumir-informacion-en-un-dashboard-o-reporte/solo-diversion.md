# Solo Diversión

¿Eres capaz de agregar el resumen de más de una variable continua a la vez (con el mismo grupo)? Por ejemplo, con la misma columna de grupo presentar en la misma tabla resumen el promedio de bpm y el promedio de stream a la vez.

```python
categories = ['bpm_category', 'danceability_category', 'valence_category',
              'energy_category', 'acousticness_category',
              'instrumentalness_category', 'liveness_category', 'speechiness_category']

result_category = []

for category in categories:
    df_group_alto = df[df[f'{category}'] == "Alto"]
    df_group_bajo = df[df[f'{category}'] == "Bajo"]

    summary_alto = df_group_alto['streams_limpo'].describe()
    summary_bajo = df_group_bajo['streams_limpo'].describe()

    scorecard = pd.DataFrame({
        'Categoría': [f'{category} (Alto)', f'{category} (Bajo)'],
        'Conteo': [summary_alto['count'], summary_bajo['count']],
        'Promedio': [summary_alto['mean'], summary_bajo['mean']],
        'Mediana': [summary_alto['50%'], summary_bajo['50%']],
        'Moda': [df_group_alto['streams_limpo'].mode().values[0], df_group_bajo['streams_limpo'].mode().values[0]],
        'Máximo': [summary_alto['max'], summary_bajo['max']],
        'Mínimo': [summary_alto['min'], summary_bajo['min']],
        'Desviación Estándar': [summary_alto['std'], summary_bajo['std']]
    })

    result_category.append(scorecard)

result_combined = pd.concat(result_category, keys=categories, names=['Categoría', 'Subcategoría'])

result_combined = result_combined.droplevel(0)

print(tabulate(result_combined, headers='keys', tablefmt='pretty'))
```

<mark style="background-color:purple;">Explicación línea por línea del código:</mark>

1. `categories`: Esta línea define una lista llamada `categories` que contiene los nombres de las categorías que se utilizarán en el análisis.
2. `result_category`: Se crea una lista vacía llamada `result_category` que se utilizará para almacenar los DataFrames resultantes de cada categoría.
3. Se inicia un bucle `for` que recorre cada categoría en la lista `categories`.
4. Se filtran dos DataFrames, `df_group_alto` y `df_group_bajo`, que contienen las filas correspondientes a "Alto" y "Bajo" para la categoría actual.
5. Se calculan estadísticas descriptivas (como el conteo, la media, la mediana, etc.) para la columna 'streams\_limpo' en los DataFrames filtrados.
6. Se crea un DataFrame llamado `scorecard` que contiene las estadísticas descriptivas para "Alto" y "Bajo" en la categoría actual.
7. El DataFrame `scorecard` se agrega a la lista `result_category`.
8. Todos los DataFrames de las diferentes categorías se combinan en un único DataFrame llamado `result_combined` utilizando la función `pd.concat`. Se utiliza el argumento `keys` para etiquetar cada sección con el nombre de la categoría y `names` para asignar nombres a los niveles de índice.
9. Se elimina el nivel superior del índice (que era 'Categoría') utilizando `droplevel(0)`.
10. Finalmente, se imprime la tabla formateada utilizando la función `tabulate`.

    Este código realiza un análisis de las estadísticas descriptivas para diferentes categorías y subcategorías, y presenta los resultados en una tabla fácil de leer.







