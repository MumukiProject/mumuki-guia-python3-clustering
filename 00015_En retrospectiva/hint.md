Para hacer un `pointplot` son seaborn podés utilizar el siguiente código: 

```python
sns.pointplot(data = inercias, x = "k", y = "inercia")
```

O, usando pandas: 

```python
inercias.plot.line(x="k", y="inercia")
```

