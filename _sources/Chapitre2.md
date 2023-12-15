### Chapitre 2 : Les processus aléatoires stationnaires et non stationnaires

#### Prof. Jouilil Youness


#####  1. Autoregressive integrated moving average model

```{admonition} Définition
Un modèle ARIMA(p,d,q) prend la forme suivante :

$$
\nabla^dy_t = (1-B)^dy_{t} ~~~~ , \forall t \in \mathbb{Z}^{*+}
$$

Ou 

$$
( 1- \Phi_1 B - \Phi_2 B^2 - \ldots - \Phi_p B^p ) \nabla^dy_t= (1- \theta_1 B - \theta_2 B^2 - \ldots - \theta_q B^q)\eta_t
$$

Avec :

-  $\nabla$ indique l'opérateur de différence.

- d un entier positif ( d $\in$ $\mathbf{N}$)

- Le processsus $(Y_t)$ suit un ARMA(p,q). 

```


```{admonition} Remarque
 Les processus ARIMA sont alors des extensions the processus ARMA.
```

```{admonition} Lemme
Soit $\lbrace Y_t \rbrace_{t \in \mathbb{Z}^{*+}}$  un processus stochastique. 

Si $(Y_t)$  suit un ARIMA(p,d,q) alors :


$$
    \Phi_p (B)(1-B)^{d}Y_t = \Theta_q(B)\eta_t ~~ , ~~~ \eta_t \sim WN (0 , \sigma^2)
$$

Ainsi,

$\nabla^dY_t = (1-B)^dY_{t}$ un processus stationnaire ARMA(p,q)
```

#####  2. Modélisation des processus stochastiques


Le principal défi de la modélisation des processus stochastiques est de trouver le processus générateur approprié aux données. Pour ce faire, on peut impliquer la procédure Box-Jenkins.

```{admonition} Proposition

Soit $(y_t) \sim ARIMA(p,d,q)$.

Les ordres p et q du processus ARIMA sont déterminés par les critères de sélection statistiques et/ou graphiques, tels que le critère d'information bayésien (BIC), le critère d'information de Schwarz (SIC) et le critère de Hannan-Quinn (HQC) ou soit le critère d'information d'Akaike ( AIC).
```


```{admonition} Algorithme de Box \& Jenkins

Cette méthodologie suggère une procédure à quatre étapes :

- Etape 1 : Identification du processus

Déterminer à partir de l'observation des fonctions d'autocorrélation simple et partielle dans la famille des modèles de types ARMA (p, q) le modèle adéquat.

- Etape 2 : Estimation des coefficients 

Estimation des coefficients des modèles séléctionnés à travers la méthode de MV ou MCO

- Etape 3 : Validation du modèle (Test de diagnostique des résidus) 

les résidus doivent être autocorrélés et ne présentent pas d'hétéroscédasticité.

- Etape 4 : Prévision à l'horizon h

```

##### 3. Les processus TS

```{admonition} Processus TS

$(x_t;t \in Z)$ est un processus TS (Trend Stationary) s’il peut s’écrire sous la forme

$$
x_t= f(t) + \eta_t
$$

où $f (t)$ est une fonction linéaire ou non linéaire, déterministe (mécanique, non aléatoire) du temps et $\eta_t$ est
une composante aléatoire stationnaire.
```

Dans ce cas, le processus $x_t$ s’écrit comme la somme d’une fonction déterministe du temps
et d’une composante stochastique stationnaire, éventuellement de type ARMA.

```{admonition} Exemple 01
Soient $f(t)$ un polynôme du premier degré en t et $\eta_t$ un bruit blanc. L’évolution de $X_t$ est décrite par la relation suivante :

$$
X_t = a + bt + \eta_t ~~;~~\forall t = 1, . . ., T
$$

Le terme $a + bt$ est la partie déterministe de $X_t$, à une tendance déterministe linéaire. Le terme $\eta_t$
est la partie aléatoire ou stochastique de $X_t$. 

Dans ce cas, on vérifie que le processus $(X_t)$ est non stationnaire

$$
E(X_t) = a + bt
$$

$$
V(X_t) =\sigma^2
$$

$$
Cov(X_t,X_{t'})= 0  ~~;~~ t \ne t'
$$

En revanche, le processus $(Z_t)$ défini par l’écart entre $X_t$ et la composante déterministe $f (t) = a + bt$; est quand à lui stationnaire : $Z_t = X_t -(a + bt)$ est un bruit blanc, par définition stationnaire.
```


```{admonition} Exemple 02
Soient $f(t)$ un polynôme du deuxième degré en t et $\eta_t$ un bruit blanc. L’évolution de $X_t$ est décrite par la relation suivante :

$$
X_t = a + bt + c t^2 + \eta_t ~~;~~\forall t = 1, . . ., T
$$

Le terme $a + bt c t^2 $ est la partie déterministe de $X_t$, à une tendance déterministe quadratique. Le terme $\eta_t$
est la partie aléatoire ou stochastique de $X_t$. 

Dans ce cas, on vérifie que le processus $(X_t)$ est non stationnaire

$$
E(X_t) = a + bt + c t^2 
$$

$$
V(X_t) =\sigma^2
$$

$$
Cov(X_t,X_{t'})= 0 ~~;~~ t \ne t'
$$

En revanche, le processus $(Z_t)$ défini par l’écart entre $X_t$ et la composante déterministe $f (t) = a + bt + c t^2 $; est quand à lui stationnaire : $Z_t = X_t -(a + bt + c t^2 )$ est un bruit blanc, par définition stationnaire.
```
```{admonition} Remarque
Ainsi, il est possible de généraliser cet exemple à des fonctions polynômiales de degré quelconque.
```

##### 4. Les processus DS

```{admonition} Processus DS
Un processus non stationnaire $(X_t~~;t~~ \in Z)$ est un processus DS (Differency Stationnary) d’ordre d; où d désigne l’ordre d’intégration, si le processus filtré défini par $(1 - L)^d X_t= \beta + \eta_t$ est stationnaire.
```

```{admonition} Exemple 01
Soit $(X_t~;t~ \in Z)$ est un processus DS (Differency Stationnary) d’ordre d=1. On suppose que le modèle DS est sans dérive càd  $\beta=0$

$$
(1 - L)^d X_t= \beta + \eta_t \Leftrightarrow X_t = X_{t-1} + \eta_t
$$ 
```

```{admonition} Exemple 02
Soit $(X_t~;t~ \in Z)$ est un processus DS (Differency Stationnary) d’ordre d=1. On suppose que le modèle DS est avec dérive càd  $\beta \ne 0$

$$
(1 - L)^d X_t= \beta + \eta_t \Leftrightarrow X_t = X_{t-1} + \beta +\eta_t
$$ 

```




##### 5.  processus ARCH 

###### 6.1. processus ARCH (1)



```
```
