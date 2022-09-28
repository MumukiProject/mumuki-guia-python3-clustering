¿Qué cosa? 🤌 ¡No, no, estamos hablando de _K-means_!  K-means (o _k-medias_, en español) se trata de un método que agrupa las observaciones en los _mejores_ K grupos distintos, es decir, los K _clusters_ con la menor varianza interna (_intra-cluster variation_) posible. En otras palabras, se reparten las observaciones en K clusters de forma que la suma de las varianzas internas de todos ellos sea lo menor posible. 

Podríamos decir que este método repite una serie de pasos hasta que encuentra los mejores k grupos:

![](./k_means.png)

 1. Especifica el número K de clusters que se quieren crear
 2. Selecciona de forma aleatoria k observaciones del set de datos como centroides iniciales, esto es los datos a los cuáles se calcula la distancia para delimitar el grupo de menor varianza interna
 3. Calcula las distancia de todos los datos al centroide, para definir a cuál se encuentra más próximo
4. Para cada uno de los K clusters recalcular su centroide, la posición del centroide se actualiza tomando como nuevo centroide la posición del promedio de las observaciones pertenecientes a dicho grupo
5. Repetir los pasos 3 y 4 hasta que los centroides no se mueven, o se mueven por debajo de una distancia umbral en cada paso, o se alcancen el número de iteraciones definidas de antemano.

Apliquemos ahora este método a nuestros datos:

```python
from sklearn.cluster import KMeans, DBSCAN #Para usar kmeans

k = 3  #definimos la cantidad de clusters
kmeans = KMeans(n_clusters = k, init="random", n_init=10, max_iter=300, random_state=123457) #tomamos los centroides de forma aleatoria y definimos un máximo de 300 iteraciones
kmeans.fit(iris_escaleado)  #aplicamos el método a nuestros datos
```

> Ejecutá el código anterior. ¿Qué grupos encuentra?
