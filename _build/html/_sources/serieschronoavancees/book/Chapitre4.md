### Chapitre 3 : Causalité au sens de Granger

#### Prof. Jouilil Youness

###### 1. Opérations sur les matrices


```{admonition} Exercice 1
Soient A et B deux matrices de même dimension à valeurs dans $\mathbb{Z}$ telles que :

$$
A = 
\begin{pmatrix}
0 & -2 & 7 \\
0 & 6 & 0  \\
2 & 1 & 0 
\end{pmatrix}
$$

$$
B = 
\begin{pmatrix}
1 & -2 & 5 \\
0 & 3 & 0  \\
1 & 1 & 0 
\end{pmatrix}
$$

- Calculer $A + B$, $A-B$, $A-I$, $I-B$.
- Calculer $\dfrac{1}{2} A$, $3A-2B$, $5I-2B$
- Calculer $IB$ et $BI$. Conclure
- Calculer $AB$ et $BA$. Conclure
- Calculer $(AB)^{t}$ et $B^tA^t$. Conclure
- Calculer $A^2$ et $A^3$.
```

```{admonition} <font color='blue'>Réponse de l'exercice 1</font>
:class: attention, dropdown

$$
A = 
\begin{pmatrix}
0 & -2 & 7 \\
0 & 6 & 0  \\
2 & 1 & 0 
\end{pmatrix}
$$

$$
B = 
\begin{pmatrix}
1 & -2 & 5 \\
0 & 3 & 0  \\
1 & 1 & 0 
\end{pmatrix}
$$
```

###### 2. Transposé et symétrie d'une matrice
```{admonition} Exercice 2

Soient A et B deux matrices dans $M_n$($\mathbb{K})$ telles que : 

$$
A = 
\begin{pmatrix}
1 & 0 & 0 \\
0 & 2 & 0 \\
0 & 0 & -4 
\end{pmatrix} ; 
$$

$$
B = 
\begin{pmatrix}
0 & -2  \\
2 & 0 
\end{pmatrix}
$$

- Déterminer l'ordre de A et B.
- Calculer $A^{'}$ et $B^{'}$.
- Peut-on calculer AB  et BA ? Justifier votre réponse !
- Montrer que A est symétrique. Justifier votre réponse !
- Montrer que B est antisymétrique. Justifier votre réponse !

```

```{admonition} <font color='blue'>Réponse de l'exercice 2</font>
:class: attention, dropdown
$$
A = 
\begin{pmatrix}
1 & 0 & 0 \\
0 & 2 & 0 \\
0 & 0 & -4 
\end{pmatrix} ; 
$$

$$
B = 
\begin{pmatrix}
0 & -2  \\
2 & 0 
\end{pmatrix}
$$

```



###### 2. Déterminant, trace et inversion de matrices

```{admonition} Exercice 3
Soient A  et B deux matrices à valeurs dans $\mathbb{R}$ telles que: 

$$
A = 
\begin{pmatrix}
2 & 6 \\
2 & 0 
\end{pmatrix}
$$

$$
B = 
\begin{pmatrix}
1 & -2 & 3 \\
0 & 3 & 2  \\
2 & 1 & 4 
\end{pmatrix}
$$

- Calculer tr(A) et tr(B)
- Calculer det(A). Déduire que A est inversible ( c.à.d A $\in$ $Gl_2(\mathbb{R})$)
- Calculer det(B). Déduire que B $\in$ $Gl_3(\mathbb{R})$
- Calculer $A^{-1}$

```

```{admonition} <font color='blue'>Réponse de l'exercice 3</font>
:class: attention, dropdown

Soient A  et B deux matrices à valeurs dans $\mathbb{R}$ telles que: 

$$
A = 
\begin{pmatrix}
2 & 6 \\
2 & 0 
\end{pmatrix}
$$

$$
B = 
\begin{pmatrix}
1 & -2 & 3 \\
0 & 3 & 2  \\
2 & 1 & 4 
\end{pmatrix}
$$
```

```{admonition} Exercice 4
On considère les matrices suivantes :

$$
A = \begin{pmatrix}
1 & 0 & 0 \\
1 & 1 & 0  \\
0 & 1 & 1 
\end{pmatrix}
$$

$$
A - B = I_3
$$

- La matrice A est-elle symétrique ?
- Calculer $B^p ~;~ p \ge 1$
- Déduire $A^p ~;~ p \ge 1$
```

```{admonition} <font color='blue'>Réponse de l'exercice 4</font>
:class: attention, dropdown
$$
A = \begin{pmatrix}
1 & 0 & 0 \\
1 & 1 & 0  \\
0 & 1 & 1 
\end{pmatrix}
$$

$$
A - B = I_3
$$
```

```{admonition} Exercice 5

On considère la matrice A définie par :

$$
A = \begin{pmatrix}
0 & 1 & -1 \\
-3 & 4 & -3  \\
-1 & 1 & 0 
\end{pmatrix}
$$


- Montrer que $A^2-3A+2I_3 = 0$
- Calculer $A^{-1}$
```

```{admonition} <font color='blue'>Réponse de l'exercice 5</font>
:class: attention, dropdown
$$
A = \begin{pmatrix}
0 & 1 & -1 \\
-3 & 4 & -3  \\
-1 & 1 & 0 
\end{pmatrix}
$$

```
```{admonition} Exercice 6

Soit la matrice A définie par 

$$
A = \begin{pmatrix}
0 & 1 & 1  \\
1 & 0 & 1  \\
1 & 1 & 0 
\end{pmatrix}
$$

1- Trouver $\alpha$, $\beta$ $\in$ $\mathbb{R}$ tels que $A^2 = \alpha I + \beta A$

2- En déduire que A est inverible et donner son inverse
```
```{admonition} <font color='blue'>Réponse de l'exercice 6</font>
:class: attention, dropdown

$$
A = \begin{pmatrix}
0 & 1 & 1  \\
1 & 0 & 1  \\
1 & 1 & 0 
\end{pmatrix}
$$

```

```{admonition} Exercice 7
On considère la matrice suivante :

$$
A = \begin{pmatrix}
1 & 2 & 0 \\
0 & 1 & 3  \\
0 & 0 & 1 
\end{pmatrix}
$$

- Vérifier que A est une matrice triangulaire supérieure

- Calculer ${(A-I_3)}^{n}$ pour tout n $\in$ $\mathbb{N}^{*}$

- Monter que A est non singulier

- Déduire $A^{-1}$
```

```{admonition} <font color='blue'>Réponse de l'exercice 7</font>
:class: attention, dropdown
$$
A = \begin{pmatrix}
1 & 2 & 0 \\
0 & 1 & 3  \\
0 & 0 & 1 
\end{pmatrix}
$$

```