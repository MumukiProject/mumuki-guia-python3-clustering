Otra propiedad que nos puede interesar de una agrupación es que todos los puntos de un grupo estén bien _juntitos_ :hugging:  pero a la vez bien separados del resto de los puntos en otros grupos :dash:. 

:bust_in_silhouette: :busts_in_silhouette: Esta idea se puede encontrar en el coeficiente de _silhouette_ (silueta, en inglés), que para miembro del cluster nos dice, si está cerca de su cluster y lejos del resto (coeficiente cercano a `1`) o si está lejos de su cluster y cerca del resto (coeficiente cercano a `-1`). :person_gesturing_no: Esto nos da dos reglas taxativas para _rechazar_ (pero no así elegir) valores concretos de `k`: 

  1. Si hay clusters donde todos los coeficientes de silhouette de sus miembros están por debajo del valor promedio general, o bien
  2. si hay clusters donde alguno de sus miembros tiene un valor inferior a cero (que indica un miembro mal clasificado).

Tanto el valor promedio  
  

```python


silhouette_avg = silhouette_score(iris_escalado, kmeans.labels_)
print(silhouette_avg)

sample_silhouette_values = silhouette_samples(iris_escalado, kmeans.labels_)
sample_silhouette_values
```

```
from yellowbrick.cluster import SilhouetteVisualizer

from yellowbrick.cluster import SilhouetteVisualizer

for k in range(2, 6):
  print("k =", k)
  kmeans = KMeans(n_clusters=k, init='random', n_init=10, max_iter=300, random_state=42)

  visualizer = SilhouetteVisualizer(kmeans, colors='yellowbrick')
  visualizer.fit(iris_escalado)  
  plt.show()
```
> Calculá la silhouette para distintos valores de `k`, desde 2 a 10, y almacenalos en un `DataFrame`. Luego realizá un gráfico de inercia vs k, usando el método `pairplot` de seaborn, ¿Cuál es el mejor valor de k según este criterio?
>

