Una forma de evaluar cuán bien funcionó nuestro agrupamiento podría ser calcular cuán compactos son los grupos obtenidos. 

Partiendo de la base que un agrupamiento es mejor si todos los elementos del grupo están lo más cerca posible de su centro, podemos sumar las distancias de cada punto a su respectivo centro y usar eso como medida. A este valor se lo denomina _inercia_ y puede obtenerse haciendo:

```python
ム kmeans.inertia_
139.82049635974974
```

>
> Calculá la inercia para distintos valores de k, desde 0 a 10, y almacenalos en un `DataFrame`. Luego realizá un gráfico de líneas de `k` vs `inercia`.
>
> ¿Cuál es el mejor valor de k según este criterio?
>
