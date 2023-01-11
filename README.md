# p22-classes-dunder

Un petit TP sur les méthodes spéciales("dunder").

Contrairement à nos TPs habituels, pas de grader ici. Vous devrez faire tourner les tests à la main,
soit dans VS Code, soit en éxécutant:

```python
# Tous les tests
python -m unittest
# Juste un fichier
python test_polynomial.py
```

## Polynomial


On se propose d'écrire une classe pour représenter les polynômes :

* avec un constructeur qui prend en argument les coefficients en commençant par les degrés les plus élevés ; ainsi par exemple
  * `Polynomial()` aussi bien que `Polynomial(0)` représentent le polynôme nul,
  * `Polynomial(3, 2, 1)` représente $3X^2 + 2X + 1$, et
  * `Polynomial(3, 0, 1, 0, 0)` représente $3X^4 + X^2$
  
* avec un **attribut `degree`** pour accéder au degré

* avec une **méthode `derivative()`** pour calculer le polynôme dérivé

* qui sait s'**additionner**, se **multiplier** et se **comparer** avec `==`

* et qu'on **peut appeler** (autrement dit qui est un *callable*)  
  ce qui signifie qu'on peut écrire par exemple
  
  ```python
  P = Polynomial(3, 2, 1)
  P(10) == 321
  ```
  
**Note importante**

Le système de correction automatique a besoin également que votre classe définisse son comportement vis-à-vis de `repr()` ; regardez les exemples pour voir la représentation choisie.


**Quelques exemples:**

```python
>>> P = Polynomial()
>>> P
'0'
>> P.degree
0
```

```python
>>> P = Polynomial(0)
>>> P
'0'
>> P.degree
0
```

```python
>>> P = Polynomial(1)
>>> P
'1'
>> P.degree
0
>>> Polynomial() == Polynomial(0)
True
>>> Polynomial(0) == P * Polynomial()
true
```

```python
>>> P = Polynomial(1, 2, 3)
>>> P
'X^2 + 2X +3'
>> P.degree
2
```

```python
>>> P = Polynomial(1, 0, 3, 0, 0)
>>> P
'X^4 + 3X^2'
>> P.degree
4
```

```python
>>> Polynomial(0, 0, 1, 0, 3) == Polynomial(1, 0, 3)
True
```

```python
>>> P = Polynomial(1, 2, 3)
>>> P.derivative()
2X + 2
>>> P.derivative()(10)
22
```

```python
>>> P = Polynomial(1, 2, 3)
>>> P + Polynomial(3, 2, 1) == Polynomial(4, 4, 4)
True
>>> P * Polynomial()
'0'
```

```python
>>> P = Polynomial(1, 2, 3)
>>> P * Polynomial(1, 2) == Polynomial(3, 8, 5, 2)
True
```

## Quaternion

On se propose d'implémenter une classe représentant le [corps des
quaternions](https://fr.wikipedia.org/wiki/Quaternion), sur lesquels on peut effectuer une addition
et une multiplication.

Comme je n'ai pas eu le temps d'écrire le sujet, je vous laisse voir dans les tests
`test_quaternion.py` pour voir des exemples de ce qu'il faut faire.

En super-bonus, `test_quaternion_avance.py` contient des exemples d'addition et multiplications
entre des quaternions et des entiers, des complexes, etc...
