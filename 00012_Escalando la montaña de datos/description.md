Estas operaciones pueden hacerse muy fácilmente con la clase `StandardScaler`, del módulo `scikitlearn`:

```python
from sklearn.preprocessing import StandardScaler

scaler = StandardScaler()
iris_escaleado = scaler.fit_transform(iris)
```

> Ejecutá este código en tu cuaderno. 
