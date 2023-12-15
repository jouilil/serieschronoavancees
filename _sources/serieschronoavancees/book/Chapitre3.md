### Chapitre 3 : Tests de Cointégration et MCE


###### 2. Tests de racine unitaire (Unit Root Test)

Il existe trois méthodes principales pour détecter la non-stationarité :

1. Le graphique de la série

2. Son corrélogramme.

3. Des tests statistiques formels pour détecter les racines unitaires.

Les tests de racine unitaire (Unit Root Test) permettent non seulement de détecter l’existence d’une non-stationnarité 
mais surtout de déterminer de quelle non-stationnarité il s’agit (processus TS ou DS) et donc la bonne méthode pour
stationnariser la série.


###### 2. 1 Processus DS et TS


```{admonition} Processus DS

Un processus DS avec dérive s’écrit : :

$$
X_t = X_{t-1} + \eta_t + \beta
$$

Avec $\gamma = constant ~ \in ~\mathbb{R}$

- Démontrer que $f$ est une application linéaire quel que soit $\gamma$
```

```{admonition} <font color='blue'>Réponse de l'exercice 2</font>
:class: attention, dropdown

Soit $f$ l'application de $\mathbb{R}^3$ dans $\mathbb{R}^2$ définie par :

$$
f(x; y; z) = (\gamma x - y; y -\gamma z)
$$

Avec $\gamma = constant ~ \in ~\mathbb{R}$

- Démontrons que $f$ est une application linéaire quel que soit $\gamma$

```
###### 2. Noyau et image d’une application linéaire

```{admonition} Exercice 3
Soit $f$ l'application de $\mathbb{R}^2$ dans $\mathbb{R}^3$ définie par :

$$
f : \mathbb{R}^2 \rightarrow \mathbb{R}^3, f(x, y) = (x - y; 3x + y; -x + y )
$$

1. Déterminer une base du noyau de f.
2. Déduire la dimension du noyau de f.
```

```{admonition} <font color='blue'>Réponse de l'exercice 3</font>
:class: attention, dropdown

Soit $f$ l'application de $\mathbb{R}^2$ dans $\mathbb{R}^3$ définie par :

$$
f : \mathbb{R}^2 \rightarrow \mathbb{R}^3, f(x, y) = (x - y; 3x + y; -x + y )
$$

- Déterminons une base du noyau de f.

```

```{admonition} Exercice 4
Soit $f$ l'application de $\mathbb{R}^3$ dans $\mathbb{R}^2$ définie par :

$$
f : \mathbb{R}^2 \rightarrow \mathbb{R}^3, f(x, y) = (x - y -z; y + z -x  )
$$

1. Déterminer une base de Ker( f )
2. Déterminer une base de Im( f )
```

```{admonition} <font color='blue'>Réponse de l'exercice 4</font>
:class: attention, dropdown

Soit $f$ l'application de $\mathbb{R}^3$ dans $\mathbb{R}^2$ définie par :

$$
f : \mathbb{R}^2 \rightarrow \mathbb{R}^3, f(x, y) = (x - y -z; y + z -x  )
$$

- Déterminons une base de Ker( f )

```

###### 3. Applications linéaires injectives et surjectives.

```{admonition} Exercice 5
Soit $f$ l'application de $\mathbb{R}^2$ dans $\mathbb{R}^3$ définie par :

$$
f : \mathbb{R}^2 \rightarrow \mathbb{R}^3, f(x, y) = (x - y; 3x + y; -x + y )
$$

1. Déterminer une base du noyau de f.
2. Déduire la dimension du noyau de f.
3. f est-elle injective ? Justifier votre réponse.
4. f est-elle surjective ? Justifier votre réponse.

```

```{admonition} <font color='blue'>Réponse de l'exercice 5</font>
:class: attention, dropdown

Soit $f$ l'application de $\mathbb{R}^2$ dans $\mathbb{R}^3$ définie par :

$$
f : \mathbb{R}^2 \rightarrow \mathbb{R}^3, f(x, y) = (x - y; 3x + y; -x + y )
$$

- Déterminons une base du noyau de f.

```

```{admonition} Exercice 6
On considère l’application linéaire f définie par :

$$
 f( x,y,z) = (x + y, y + z, z + x, x + y + z)
$$

On vous demande alors de :

- Calculer l’image de la base canonique de $\mathbb{R}^3$  par $f$ .

- Déduire une base de $Im(f)$

- Déduire le rang de f.

- Déterminer le noyau de $f(Ker(f))$ et en déduire le rang de $f(rg( f ))$. 
```

```{admonition} <font color='blue'>Réponse de l'exercice 6</font>
:class: attention, dropdown

$$
 f( x,y,z) = (x + y, y + z, z + x, x + y + z)
$$

- Calculons l’image de la base canonique de $\mathbb{R}^3$  par $f$ .

```

```
```