La asignación de cada punto a un cluster se obtiene el atributo `labels_` del objeto `clusters`, esta propiedad me dice que etiqueta le puso a cada uno de mis datos. 


```python
kmeans.labels_
```

Los centroides pueden ser obtenidos con `cluster_centers_`:

```python
kmeans.cluster_centers_
```
