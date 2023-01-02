Para hacer un gráfico de líneas podés usar el método `plot.line` de `pandas` :panda_face:. Por ejemplo, si tu tabla de inercias se llama `inercias` y tiene dos columnas `k` e `inercia`, podés hacerlo así:

```python
inercias.plot.line(x = "k", y = "inercia")
```

Alternativamente, podés hacer lo mismo (pero más bonito :star2:) con `seaborn` usando `pointplot`: 

```python
sns.pointplot(data = inercias, x = "k", y = "inercia")
```

