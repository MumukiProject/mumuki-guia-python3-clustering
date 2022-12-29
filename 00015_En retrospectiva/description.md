Una forma de evaluar cuán bien funcionó nuestro agrupamiento podría ser calcular cuán compactos son los grupos obtenidos. Entendiendo que funcionó mejor si todos los elementos del grupo están lo más cerca posible de su centro. Podemos, entonces, sumar las distancias de cada punto a su respectivo centro y usar eso como medida. A este valor se lo denomina inercia y puede obtenerse haciendo:


```python
print(kmeans.inertia_ )
```

>
> Calculá la inercia para distintos valores de k, desde 0 a 10, y almacenalos en un `DataFrame`. Luego realizá un gráfico de inercia vs k, usando el método pointplot de seaborn
>
> ¿Cuál es el mejor valor de k según este criterio?
>
