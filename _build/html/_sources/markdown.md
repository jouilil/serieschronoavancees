###  Module : Algèbre
### Professeur Jouilil Youness
### Série 1


$a$ et $b$ désignent deux réels tels que $a \leq b $. Toutes    les fonctions sont supposées définies sur $[a, b]$ et a valeurs réelles.
Le but de l'intégration est de définir un nombre qui, pour une fonction $f$ positive sur un segment $[a, b]$ , mesure l'aire délimitée par sa courbe représentative, l'axe des abscisses et les deux droites d'équations $x = a$ et $x = b$.
Ce nombre sera appelé intégrale de $f$ sur $[a, b]$ et notée : 

$$
\int_a^b f(x)dx
$$


## Intégrale des fonctions en escalier

### Subdivision d'un segment


```{admonition} Exercice 1
* On considère l'ensemble suivant:

$$
A = X \in \mathbb{R}^4 ; (x+2y,y-z, -x+3z,-z) x,y,z \in \mathbb{R}
$$
\delta(u)=\max_{i \in [1, n]}(x_i - x_{i-1})
$$
```
```{admonition} Exemple
Une subdivision $(x_i)_{i=0}^n$ ou $n$ un entier naturel non nul est dite a pas constant si:

$$
\forall i \in \{0, \ldots, n\}, x_i = a+i\dfrac{b-a}{n}
$$

Son module est $\dfrac{b-a}{n}$
```


```{admonition} Définition 2
Si $u$ et $v$ sont deux subdivisions de $[a, b]$ , on dit que $u$ est plus fine que $v$ si tout élément de $v$ est élément de $u$.
```


```{note}
Par définition, une subdivision est une partie finie de $[a, b]$ contenant $a$ et $b$. Ceci dit, une subdivision $u$ est plus fine qu'une autre $v$ est équivaut à dire que $v \subset u$.
```

```{admonition} Proposition 1
Pour toutes subdivisions $u$ et $v$ de $[a, b]$ il existe une subdivision plus fine que  $u$ et $v$.
```

### Fonctions en escalier


```{admonition} Définition 3


Une fonction $\varphi$ de $[a,b]$ dans $\mathbb{R}$ est dite en escalier si l'on peut trouver une subdivision $u=(x_i)_{i=0}^n$ de $[a, b]$ telle que $\varphi$ soit constante sur chacun des intervalles $]x_{i-1}, x_i[, (1\leq i \leq n)$.
La subdivision $u$ est dite adaptée à la fonction $\varphi$. 

```


```{admonition} Exemples


- Une fonction constante sur l’intervalle $[a,b]$ est une fonction en escalier sur $[a,b]$.
- La fonction _partie entière_ est une fonction en escalier sur segment $[a,b]$ (pensez à une subdivision adaptée!).

```

**Remarques**:

1. Une fonction en escalier prend un nombre fini de valeurs. En particulier, elle est bornée.
2. Si $u$ est une subdivision adaptée à une fonction $\varphi$ en escalier, alors toute subdivision plus fine que $u$ est adaptée à $\varphi$.
3. Si $\varphi$ et $\psi$ sont deux fonctions en escalier sur $[a. b]$, alors il existe une subdivision adaptée à $\varphi$ et $\psi$.


```{admonition} Proposition 2
L'ensemble des fonctions en escalier sur $[a, b]$ est un sous-espace vectoriel de l'espace des fonctions définies sur $[a, b]$
```

```{hint} 
Penser à utiliser la proposition 1!
```

```{admonition} Demontsration
:class: dropdown

Soient $\varphi$ et $\psi$ deux fonctions en escalier sur $[a, b]$.

Soient $\lambda$ et $\mu$ deux réels.

D'après la proposition 1 il existe une subdivision $u=(x_i)_{i=0}^n$ adaptées à $\varphi$ et $\psi$.
Donc les deux fonctions sont constantes sur $]x_{i-1}, x_{i}[$
Il en est de même pour $\lambda \varphi + \mu \psi$ (constante sur $]x_{i-1}, x_{i}[$).
Donc, $u$ est une subdivision adaptée pour $\lambda \varphi + \mu \psi$ qui est par la suite une fonction en escalier.

Les autres conditions sont faciles à vérifier !
```

### Intégrale d'une fonction en escalier




```{admonition} Proposition 3
Soit $\varphi$ une fonction en escalier sur $[a, b]$ et $u=(x_i)_{i=0}^n$ une subdivision  adaptées à $\varphi$. Soit $c_i$ la valeur prise par $\varphi$ sur $]x_{i-1}, x_i[$ pour $i \in \{1, \ldots, n\}$ (i.e $\varphi(x)=c_i$ pour tout $x \in ]x_{i-1}, x_i[$). Alors la quantité

$$
\sum_{i=1}^nc_i(x_i-x_{i-1})
$$

ne dépend pas de la subdivision choisie.

Cette quantité s'appelle `l'intégrale` de $\varphi$ sur  $[a, b]$ et on le note:

$$
\int_a^b \varphi(x)dx=\int_{[a, b]}\varphi
$$
```


```{admonition} Demonstration
:class: dropdown

Pour toute $u$ une subdivision adaptée à la fonction $\varphi$, on note 

$$
I(\varphi, u)= \sum_{i=1}^nc_i(x_i-x_{i-1})
$$

Le but est de montrer que $\forall u, v$ subdivision adaptée à $\varphi$, $I(\varphi, u)=I(\varphi, v)$

- Si $v$ est plus fine que $u$,
Elle est obtenue en rajoutant un nombre fini d'éléments à la subdivision $u$. Pour démontrer que $I(\varphi, u)=I(\varphi, v)$, il suffit de le démontrer dans le cas où  $v$ a un élément de plus que $u$.


Soit donc $u=(x_i)_{i=0}^n$ et $v=(x_1, \ldots, x_p, y, x_{p+1}, \ldots, x_n)$

Il est claire que la fonction $\varphi$ sur $]x_p, y[$ et $]y, x_{p+1}[$. Donc :


$$
\begin{aligned}
I(\varphi, v) & =  \sum_{i=1}^{p-1}c_i(x_i-x_{i-1})+c_p(y-x_p) + c_p(x_{p+1}-y) + \sum_{i=p+2}^{n}c_i(x_i-x_{i-1})  \\ \\
 & =  \sum_{i=1}^{n}c_i(x_i-x_{i-1}) = I(\varphi, u) 
\end{aligned}
$$

- Dans le cas général:

D'après la proposition 1, il existe une subdivision $w$ plus fine que $u$ et $v$, cette subdivision est aussi adaptée à $\varphi$ (remarque 2).
Donc on aura d'une part $I(\varphi, w)=I(\varphi, u)$ et d'autre part $I(\varphi, w)=I(\varphi, v)$.

Par conséquent, 

$$
I(\varphi, v)=I(\varphi, u)
$$

```

### Propriétés de l'intégrale des fonctions en escalier

Dans ce qui suit on va noter l'ensemble des fonctions en escalier sur $[a, b]$ par $\mathcal{E}([a, b])$. 

```{admonition} Proposition 4
Montrer que :

1- pour toutes fonctions en escalier sur $[a, b]$ $\varphi$ et $\psi$, et pour tous réels $\alpha$ et $\beta$ nous avons:

$$
\int_{[a, b]}\alpha\varphi + \beta\psi = \alpha\int_{[a, b]}\varphi + \beta\int_{[a, b]}\psi
$$

2- une fonction en escalier positive a une intégrale positive.

3- si  $\varphi$ et $\psi$ sont deux fonctions en escalier sur $[a, b]$ alors:

$$
\varphi \leq \psi \Rightarrow  \int_{[a, b]}\varphi \leq \int_{[a, b]}\psi
$$

```


```{admonition} Démonstration
:class: dropdown
1-

Soient $\varphi$ et $\psi$ deux fonctions en escalier sur $[a, b]$ et $\alpha$ et $\beta$ deux réels.

Soit $u=(x_i)_{i=0}^n$ une subdivision adaptée à  $\varphi$ et $\psi$. Si, pour $i \in \{1, \ldots, n\}$, $c_i$ et $d_i$ sont respectivement les valeurs prises par $\varphi$ et $\psi$ sur $]x_{i-1}, x_i[$ alors $\alpha\varphi + \beta\psi$ est une fonction en escalier qui prend $\alpha c_i + \beta d_i$ sur $]x_{i-1}, x_i[$.

Nous avons donc,


$$
\begin{aligned}
\int_{[a, b]}\alpha\varphi + \beta\psi & = \sum_{i=1}^{n}(\alpha c_i + \beta d_i)(x_i-x_{i-1})   \\ \\
 & =  \alpha\sum_{i=1}^{n} c_i(x_i-x_{i-1}) +  \alpha\sum_{i=1}^{n} d_i(x_i-x_{i-1}) \\ \\
 & = \alpha\int_{[a, b]}\varphi + \beta\int_{[a, b]}\psi
\end{aligned}
$$

2- 

Soit $\varphi$ une fonction en escalier sur $[a, b]$ qui est positive et  $u=(x_i)_{i=0}^n$ une subdivision adaptée à $\varphi$. Puisqu’elle est positive, les valeurs $c_i$ prise par $\varphi$ sont positives. D'autre part, puisque pour tout $i \in \{1, \ldots, n\}, x_{i-1} \leq x_i$ (par définition de la subdivision) alors $\int_{[a, b]}\varphi = \sum_{i=1}^{n} c_i(x_i-x_{i-1}) \geq 0$.

3-

La fonction $\varphi - \psi$ est une fonction en escalier positive donc son intégral est positive.

```


```{admonition} Proposition 5
Une fonction $\varphi$ est en escalier sur $[a, b]$ si et seulement si pour tout $c \in ]a, b[$, ses restrictions sur $]a, c[$ et $]c, b[$ le sont. Le cas échéant,

$$
\int_{[a, b]}\varphi = \int_{[a, c]}\varphi_{|[a, c]} + \int_{[c, b]}\varphi_{|[c, b]}
$$



```


```{admonition} Démonstration
:class: dropdown

- $\Rightarrow$
    Soit $\varphi$ une fonction en escalier sur $[a, b]$ et $u$ une subdivision adaptée à $\varphi$. On ajoutant $c$ a la subdivision $u$ on obtient un subdivision $v=(x_i)_{i=0}^n$ qui est encore adaptée à $\varphi$. Soit $p$ l'entier naturel tel que $c=x_p$. Alors nous avons :
    * $(x_1, \ldots, x_p)$ une subdivision de  $[a, c]$ et puisque $\varphi$ est constante sur chaque $]x_{i-1}, x_{i}[$ donc $\varphi_{|[a, c]}$ est fonction en escalier sur $[a, c]$. Nous avons donc :

    $$
    \int_{[a, c]}\varphi_{|[a, c]} = \sum_{i=1}^{p} c_i(x_i-x_{i-1})
    $$

    * $(x_{p+1}, \ldots, x_n)$ une subdivision de  $[c, b]$ et puisque $\varphi$ est constante sur chaque $]x_{i-1}, x_{i}[$ donc $\varphi_{|[c, b]}$ est fonction en escalier sur $[c, b]$. Nous avons donc :

    $$
    \int_{[c, b]}\varphi_{|[c, b]} = \sum_{i=1}^{p} c_i(x_i-x_{i-1})
    $$

    Par suite :

    $$
    \begin{aligned}
    \int_{[a, b]}\varphi &= \sum_{i=1}^{n} c_i(x_i-x_{i-1})=\sum_{i=1}^{p} c_i(x_i-x_{i-1}) + \sum_{i=p+1}^{n} c_i(x_i-x_{i-1}) \\ \\ 
     &= int_{[a, c]}\varphi_{|[a, c]} + \int_{[c, b]}\varphi_{|[c, b]}
    \end{aligned}
    $$


* $\Leftarrow$
Supposons que $\varphi_{|[a, c]}$ et $\varphi_{|[c, b]}$ sont en escalier sur $[a, c]$ et $[c, b]$ respectivement.

Soit $u=(x_i)_{i=0}^p$ (respectivement $v= (x_i)_{i=0}^q$) une subdivision de $[a, c]$ (respectivement de $[c, b]$) adaptée à $\varphi_{|[a, c]}$ (respectivement q $\varphi_{|[c, b]}$). 

Alors, $(x_0, \ldots, x_{p-1}, x_p=c=y_1, \ldots, y_q)$ est une subdivision $[a, b]$. De plus $\varphi$ est constante sur chaque intervalle $]x_{i-1}, x_{i}[$ et $]y_{i-1}, y_{i}[$. Donc $\varphi$ est en escalier sur $[a, b]$.
```


## Fonctions continues par morceaux

### Definition, exemples 


```{admonition} Definition 4
Une application $f$ de $[a, b]$ and $\mathbb{R}$ est dit continue par morceaux s'il existe une subdivision $u=(x_i)_{i=0}^n$ de $[a, b]$ telle que pour chaque $i \in \{1,\ldots, n\}$ la restriction de $f$ a $]x_{i-1}, x_i[$ soit continue et admette des limites finies en $x_{i-1}$ et $x_{i}$.

La subdivision $u$ est dite adaptee a la fonction $f$.
```

**Illustration avec un exemple graphique**:

```{image} fig1.png
:alt: fishy
:class: bg-primary mb-1
:width: 500px
:align: center
```


```{admonition} Exemples
- Toute fonction en escalier est continue par morceaux. 
- Toute fonction continue est continue par morceaux.
- La fonction $f$ definie sur $[-1, 1]$ par : 

$$f(0)=0 \mbox{  et  } \forall x \in [-1, 1] \setminus \{0\}, f(x)=\dfrac{1}{x}
$$

n'est pas continue par morceaux, car elle n'a pas de limite finie a droite et a gauche de $0$.

```

```{admonition} Remarques

Comme pour les fonctions en escalier, on peut verifier que :
- si $u$ est une subdivision adaptee a une fonction  $f$ continue par marceaux,
alars toute subdivision plus fine que $u$ est adaptee it $f$,
- si $f$ et $g$ sont deux fonctions continues par morceaux sur $[a, b]$ , alors il existe
une subdivision adaptee a $f$ et $g$.
```


```{admonition} Proposition 6
Une fonction continue par morceaux sur  $[a, b]$ est bornee sur $[a, b]$ .
```


```{admonition} Démonstration
:class: dropdown


Soit $f$ une fonction continue par morceaux sur  $[a, b]$. Soit $u=(x_i)_{i=0}^n$ une subdivision adaptee a $f$.

Pour chaque $i \in \{1, \ldots, n\}$ admet des limites finies en $x_{i-1}$ et $x_i$. donc la restriction de $f$ sur $]x_{i-1}, x_i[$ admet un prolongement par continuite sur $[x_{i-1}, x_i]$ qui donc borne. Par suite, $f$ est bornee sur $]x_{i-1}, x_i[$.

Ceci dit, 

$$
\forall i \in \{1, \ldots, n\}, \exists M_i \geq 0, \forall x \in ]x_{i-1}, x_i[, |f(x)| \leq M_i
$$

En prenant $M = \max_{i \in \{1, \ldots, n\}} M_i$, nous aurons $\forall x \in ]a, b[, |f(x)| \leq M$.

Par suite, $f$ est bonrnee sur $]a, b[$.


```



```{admonition} Proposition 7
Soienl $f$ et $g$ deux fonctions continues par morceaux sur $[a,b]$. Les assertions suivantes sont correctes:

- $ \forall \lambda, \mu \in \mathbb R, \lambda f + \mu g$ est continue par morceaux.
- $fg$ est continue par morceaux.
```


```{admonition} Démonstration
:class: dropdown

Soit $u=(x_i)_{i=0}^n$ une subdivision adaptee a $f$ et $g$.

Les restrictions des fonctions $f$ et $g$ a chacun des intervatles $ ]x_{i-1}, x_i[$ sont continues et admettent
des limites finies en  $x_{i-1}$ et $x_i$, donc il en est de meme pour $\lambda f + \mu g$ et $fg$. Les fonctions
$\lambda f + \mu g$ et $fg$ sont donc continues par morceaux sur $[a, b]$.

```
### Integrale d'une fonction continue par morceaux 

```{admonition} Theoreme (admis)


Soit $f$ une fonction continue par morceaux sur le segment $[a, b]$ . Pour tout
reel $\epsilon > O$:

- il existe une fonction en escalier $\theta$ telle que $|f - \theta| \leq \epsilon$
- il existe des fonctions en escalier $\varphi$ et $\psi$ telles que :  

$$
\varphi \leq f \leq \psi \mbox{   et  } \psi - \varphi \leq \epsilon
$$
```

**Notations**: Dans ce qui suit, pour une fonction continue par morceaux $f$ nous allons adopte les notations suivantes:

- $\mathcal{E}^+(f)$ l'ensemble des fonctions en escalier plus grandes que $f$ .
- $\mathcal{E}^-(f)$ l'ensemble des fonctions en escalier plus petites que $f$.

```{admonition} Proposition 8


Soit $f$ une fonction continue par morceaux sur le segment $[a, b]$. Alors:

- $\left\{\int_{[a, b]} \varphi | \varphi \in \mathcal{E}^-(f)\right\}$ admet une borne superieure,
- $\left\{\int_{[a, b]} \psi | \psi \in \mathcal{E}^+(f)\right\}$ admet une borne inferieure,

de plus,

$$
sup\left\{\int_{[a, b]} \varphi | \varphi \in \mathcal{E}^-(f)\right\}= inf\left\{\int_{[a, b]} \psi | \psi \in \mathcal{E}^+(f)\right\}
$$
```

```{admonition} Démonstration
:class: dropdown

Soit $f$ une fonction continue par morceaux sur $[a, b]$. Donc $\left\{f(x)|x\in [a, b]\right\}$ est une partie non vide de $\mathbb R$ bornee donc admet une borne superieure et une borne inferieure. Soit $m=\inf_{[a, b]}$ et $M=\sup_{[a, b]}$.

les deux fonctions constantes $m$ et $M$ sur $[a, b]$ sont aussi continues par morceaux sur $[a, b]$. $\left\{\int_{[a, b]} \varphi | \varphi \in \mathcal{E}^-(f)\right\}$ est donc une partie de $\bb R$ non vide majoree (par $M(b-a)$) donc possede une borne superieure ($\alpha$). De meme, $\left\{\int_{[a, b]} \psi | \psi \in \mathcal{E}^+(f)\right\}$ une partie de $\bb R$ non vide minoree donc possede une borne inferieure ($\beta$). 


-------------
----------

donc 

$$
\alpha \leq \beta
$$


D'aute part, d'apres le theoreme



 

```
