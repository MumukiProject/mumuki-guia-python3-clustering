Otra propiedad que nos puede interesar de una agrupación, es que todos los puntos de un grupo estén bien juntos y a la vez bien separados del resto de los puntos en otros grupos. Esta idea se puede encontrar en el COEFICIENTE DE SILHOUETTE, y nos dice para cada punto, si está cerca de su cluster y lejos del resto (coeficiente cercano a 1) o si está lejos de su cluster y cerca del resto (coeficiente cercano a -1):

```python
#Para el coeficiente de silhouette
from sklearn.metrics import silhouette_samples, silhouette_score 

#Calculamos el promedio del silhouette de todos
silhouette_avg = silhouette_score(iris_escaleado, kmeans.labels_)

#Calculamos el silhouette de cada punto
sample_silhouette_values = silhouette_samples(iris_escaleado, kmeans.labels_)
```

Para graficarlo, vamos a escribir la siguiente función:

```python
import matplotlib.pyplot as plt 
import matplotlib.cm as cm 
import numpy as np

def graficar_silhouette(k, labels, sample_silhouette_values, silhouette_avg):
  fig, ax1 = plt.subplots(1, 1)
  y_lower = 10
  for i in range(k):
      ith_cluster_silhouette_values = \
          sample_silhouette_values[labels == i]

      ith_cluster_silhouette_values.sort()

      size_cluster_i = ith_cluster_silhouette_values.shape[0]
      y_upper = y_lower + size_cluster_i

      color = cm.nipy_spectral(float(i) / k)
      ax1.fill_betweenx(np.arange(y_lower, y_upper),
                        0, ith_cluster_silhouette_values,
                        facecolor=color, edgecolor=color, alpha=0.7)
      ax1.text(-0.05, y_lower + 0.5 * size_cluster_i, str(i))
      y_lower = y_upper + 10

  ax1.set_title("Plot del silhouette de cada cluster")
  ax1.set_xlabel("Coeficiente de silhouette")
  ax1.set_ylabel("Etiqueta del cluster")
  ax1.axvline(x=silhouette_avg, color="red", linestyle="--")
  ax1.set_yticks([]) 
```

Ahora sí podemos visualizar el gráfico haciendo:

```python
graficar_silhouette(k, kmeans.labels_, sample_silhouette_values, silhouette_avg)
```

> Calculá la silhouette para distintos valores de `k`, desde 2 a 10, y almacenalos en un `DataFrame`. Luego realizá un gráfico de inercia vs k, usando el método `pairplot` de seaborn, ¿Cuál es el mejor valor de k según este criterio?
>

