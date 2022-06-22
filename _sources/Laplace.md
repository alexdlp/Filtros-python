---
jupytext:
  cell_metadata_filter: -all
  formats: md:myst
  text_representation:
    extension: .md
    format_name: myst
    format_version: 0.13
    jupytext_version: 1.11.5
kernelspec:
  display_name: Python 3
  language: python
  name: python3
---

# Transformada de Laplace
Los entendidos dicen que el chisme este es lo mas cerca que puedes estar a tomar un sistema y restarle 2 o 3 años de matemática avanzada a la dificultad de su resolución solo con aplicarla. Por ejemplo podrías transformar una PDE en una ODE, que es más facil de resolver. Del mismo modo, también se podría transformar una ODE en una simple ecuación algebraica. Total, que al final donde es más útil esta cosa es en teoría de control.

$$ \mathscr{L}\{f(t)\}=\int_{t=0}^{\infty}f(t)e^{-st}dt $$

No asustarse: la primera parte quiere decir que la transformada de laplace $\mathscr{L}$ se aplica sobre una función que varía en el tiempo $f(t)$. Esta función $f(t)$ (osea, cualquier función que tengamos entre manos) se multiplica por un exponencial decreciente $e^{-st}$. Así lo que se obtiene es una conversión de una función expresada en función del tiempo $t$, a otra función expresada en base al plano complejo (o frecuencia compleja) $s$. 

````{margin}
```{code-cell}
from numpy import exp, linspace
import matplotlib.pyplot as plt

time = linspace(0,1,50)
s = 5 # valor de la frecuancia compleja, no tiene por qué ser un entero
ft = exp(-s*time)

plt.plot(time,ft)
```
````

```{warning}
En muchos sitios la integral aparece definida desde $-\infty$ a $\infty$. Por lo general, para menesteres ingenieríles nos quedamos con la integral desde $0$ a $\infty$, y dejaremos la parte negativa para movidas más matematicas.
```