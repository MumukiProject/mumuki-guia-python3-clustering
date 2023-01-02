Otra propiedad que nos puede interesar de una agrupación, es que todos los puntos de un grupo estén bien juntos y a la vez bien separados del resto de los puntos en otros grupos. Esta idea se puede encontrar en el COEFICIENTE DE SILHOUETTE, y nos dice para cada punto, si está cerca de su cluster y lejos del resto (coeficiente cercano a 1) o si está lejos de su cluster y cerca del resto (coeficiente cercano a -1):

```python
#Para el coeficiente de silhouette
from sklearn.metrics import silhouette_samples, silhouette_score 

#Calculamos el promedio del silhouette de todos
silhouette_avg = silhouette_score(iris_escaleado, kmeans.labels_)

#Calculamos el silhouette de cada punto
sample_silhouette_values = silhouette_samples(iris_escaleado, kmeans.labels_)
```

```
from yellowbrick.cluster import SilhouetteVisualizer

fig, ax = plt.subplots(2, 2, figsize=(15,8))
for i in [2, 3, 4, 5]:
  km = KMeans(n_clusters=i, init='k-means++', n_init=10, max_iter=100, random_state=42)
  q, mod = divmod(i, 2)
  visualizer = SilhouetteVisualizer(km, colors='yellowbrick', ax=ax[q-1][mod])
  visualizer.fit(iris_escalado)  
```
> Calculá la silhouette para distintos valores de `k`, desde 2 a 10, y almacenalos en un `DataFrame`. Luego realizá un gráfico de inercia vs k, usando el método `pairplot` de seaborn, ¿Cuál es el mejor valor de k según este criterio?
>

