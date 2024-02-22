# Conectar/importar datos a otras herramientas

## Meta

Conectar/importar datos a otras herramientas.

## Objetivo

Crear un nuevo Google Colab e importar tablas.

## Objetivo individual

* [x] Cada una debe crear su entorno de trabajo en Google Colab e importar las tablas.

<pre class="language-python"><code class="lang-python"><strong>!pip install google-cloud-bigquery
</strong>!pip install pandas

from google.cloud import bigquery
from google.colab import auth
from IPython.display import display
import pandas as pd

auth.authenticate_user()

project_id = 'proyecto-2-hipotesis-405315'

client = bigquery.Client(project=project_id)

query = 'SELECT * FROM proyecto-2-hipotesis-405315.tablaSpotify.view_master_left'

df = client.query(query).to_dataframe()

display(df)
</code></pre>

## Conclusiones

<mark style="background-color:green;">Se creo un espacio de trabajo en Google Colab y por medio del código se importa la tabla view\_master\_left</mark>

