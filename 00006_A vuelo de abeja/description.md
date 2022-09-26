Para tener una idea más intuitiva del comportamiento de los datos podemos graficar la distribución de frecuencias de las distintas variables que nos permitirá, por ejemplo,  saber si las observaciones son únicas o se repiten. Para ello utilizaremos la biblioteca `seaborn` 🐚, que al igual que `pandas`, nos permite hacer gráficos….

```python
import seaborn as sns

g = sns.histplot(data = iris, x = "sepal.length", binwidth=0.25, kde = True)
plt.show()
```

... sólo que un poco más bonitos ✨.

> Realizá este gráfico en tu cuaderno y respondé: ¿qué información nos provee? 
