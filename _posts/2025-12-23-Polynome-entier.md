---
title: "Polynôme d'entiers naturels"
---

Petit exercice transmis par un de mes collègues à Marianne.

## Énoncé

Soit $P \in \mathbb{N}[X]$ un polynôme à coefficients entiers *naturels*. Comment déterminer les coefficients de $P$ à l'aide de deux évaluations $P(a)$ et $P(b)$, avec $a$ et $b$ deux réels ?

## Correction

On prend $a = 1$. Alors $C = P(a)$ correspond à la somme des coefficients du polynôme. 

Si $C = 0$, alors $P$ est le polynôme nul.

Si $C = 1$, alors $P$ est un monôme $X^n$. Pour trouver $n$, il suffit de l'évaluer en $2$. 

On suppose alors que $C \geq 2$. Puisque nous travaillons sur $\mathbb{N}$, ce nombre est supérieur à chacun des coefficients du polynome. On utilise alors l'unicité de l'écriture d'un nombre en base $C$.

En effet, si $x$ est un nombre entier, alors $x$ peut s'écrire de manière unique sous la forme

$$
x = a_0 + a_1 C + a_2 C^2 + \dots + a_n C^n
$$

avec $a_0; a_1; a_2; \dots; a_n$ des entiers naturels inférieurs strictement à $C$.

Il suffit de prendre $b = C$, d'évaluer $P(b)$ et de regarder sa décomposition unique en base $C$. Chacun des "chiffres" obtenus correspondra au coefficient correspondant dans le polynôme.