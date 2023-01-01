¿Qué cosa? 🤌 ¡No, no, estamos hablando de _K-means_!  :sweat_smile: 

K-means (o _k-medias_, en español) se trata de un método que agrupa las observaciones en los _mejores_ K grupos distintos, es decir, los K _clusters_ con la menor varianza interna (_intra-cluster variation_) posible. En otras palabras, se reparten las observaciones en K clusters de forma que la suma de las varianzas internas de todos ellos sea lo menor posible. 

👣 Este método repite una serie de pasos...

 1. Definir el número K de clusters que se quieren crear;
 2. Seleccionar de forma aleatoria k observaciones del lote de datos como _centroides_ iniciales, esto es los, datos a los cuáles se calcula la distancia para delimitar el grupo de menor varianza interna;
 3. Calcular las distancia de todos los datos al centroide, para definir a cuál se encuentra más próximo;
 4. Para cada uno de los K clusters recalcular su centroide, la posición del centroide se actualiza tomando como nuevo centroide la posición del promedio de las observaciones pertenecientes a dicho grupo;
 5. Repetir los pasos 3 y 4 hasta que los centroides no se mueven, o se mueven por debajo de una distancia umbral en cada paso, o se alcancen el número de iteraciones definidas de antemano.

...hasta que encuentra los mejores k grupos:

<a href="https://commons.wikimedia.org/wiki/File:K-means_convergence.gif" target="_blank"><img src="https://upload.wikimedia.org/wikipedia/commons/e/ea/K-means_convergence.gif" alt="Convergencia de KMeans, cortesía de Wikipedia" width="250px" height="auto"></a>

Si definimos, arbitrariamente, que vamos a buscar 3 grupos ...

```python
k = 3
```
... con `scikit-learn` podemos implementar este método usando `KMeans`: 

```python
kmeans = KMeans(
  n_clusters = k, 
  init="random", 
  n_init=10, 
  max_iter=300, 
  random_state=42
) 
kmeans.fit(iris_escalado)
```

Luego, podremos consultar cuáles son los clusters encontrados...

```python
kmeans.labels_
```
... y los centroides:

```python
kmeans.cluster_centers_
```

> Ejecutá el código anterior. ¿Cuántos miembros encuentra de cada grupo?
