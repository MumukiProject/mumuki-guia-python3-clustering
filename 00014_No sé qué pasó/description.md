Para entender mejor los resultados obtenidos grafiquemos la distribución de puntos, pintando cada punto según el color correspondiente al etiquetado:


```python
import seaborn as sns
colores = ["red", "green", "blue"]
g = sns.scatterplot(x = iris_escaleado[:,2], y = iris_escaleado[:, 3], hue = kmeans.labels_, palette = colores, alpha = 0.5)
g = sns.scatterplot(x = kmeans.cluster_centers_[:,2], y = kmeans.cluster_centers_[:,3], zorder = 10, palette = colores, hue = [0, 1, 2], legend = False, marker=6, s=200)
```

> Para pensar 🤔: ¿Es bueno o malo este resultado? ¿Cómo podríamos evaluar el resultado?
>
