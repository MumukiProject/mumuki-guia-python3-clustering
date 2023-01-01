Ya identificamos algunos problemas a la hora de clasificar los datos, pero para que las comparaciones que hagamos sean completamente válidas, resulta de suma importancia hacerles un tratamiento extra 💆. 

Uno de estos tratamientos es el _escalado de los datos_. Este procedimiento nos permite asegurarnos de que aún cuando algunas variables toman valores más grandes no se usarán como predictor principal a la hora de clasificar.

¿Por qué es importante hacer esto?

Imaginemos que tenemos que analizar la trayectoria profesional de dos personas, para hacer una selección laboral. A priori, sería lógico pensar en basar esta selección en el curriculum de dichas personas. Sin embargo, resulta evidente que el curriculum no nos da un panaroma completo de las habilidades de una persona. Por ejemplo, no nos permite conocer su capacidad de trabajo en equipo o sus habilidades para realizar más de una tarea a la vez, etc. ¿Qué peso le estamos dando entonces a estas otras características? ¿Estamos subvalorando o sobrevalorando las hablidades de las personas? ¿Que pasa con las personas no tienen las mismas posibilidades para completar su curriculum? ¿Las hace menos capaces para el trabajo?

Es por ello que resulta necesario escalar los datos. La escala es importante para poder especificar que una modificación en una cantidad no es igual a otra modificación en otra. En pocas palabras, escalar los datos le da a todas las características la misma importancia para que ninguna esté dominada por otra. 

Además, resulta necesario antes de comenzar a clasificar nuestros datos es la normalización. Esta implica transformar o convertir el conjunto de datos en una distribución normal, de forma que todos datos tenga una varianza del mismo orden. De este modo, cada dato nos dará una idea de a cuántos desvíos de la media está ese punto.

Estas operaciones pueden hacerse muy fácilmente con la clase `StandardScaler`, del módulo `scikitlearn`:

```python
from sklearn.preprocessing import StandardScaler

scaler = StandardScaler()
iris_escaleado = scaler.fit_transform(iris)
```

> Ejecutá este código en tu cuaderno. 

