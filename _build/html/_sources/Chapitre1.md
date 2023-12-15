## Chapitre 1 : Complément sur les séries chronologiques

### Complément sur les séries chronologiques

#### 1. Rappels et concepts de base 



```{admonition} Définition
<i>On appelle série chronologique ou temporelle ou encore chronique une suite d’observations chiffrées d’un même phénomène et ordonnées dans le temps (t).</i>

$$
Y = \lbrace Y_t ~~; ~~t \in \Theta \rbrace
$$
```


```{admonition} Fréquence d'observation

Les dates d’observations sont généralement ordonnées de manière régulière dans le temps (t). 

Le temps est défini comme variable discrète et les données observées peuvent être des secondes, minutes, heures, jours, semestres, années ...etc. On parle alors de fréquence de données.
```


**Exemples** : 

**Série chronologique économique** : 

PIB, taux d'inflation, taux de croissance, taux de chômage au Maroc.

**Série chronologique financière** : 

CAC40, Oil, la consommation d'électricité au Maroc, le nombre de passagers en milliers dans les transports aériens, Evolution de la population des Etats Unis, en millions d’habitants, entre 1790 et 2023.


```{admonition} Pourquoi analyse t-on les Séries Chronologiques ?
L'objectif de l'analyse des séries chroniques est :

- Comprendre 

- Modéliser

- Prévenir et contrôler
```


```{admonition} Série chronologique univariée
<i> Une série chronologique univariée peut être représentée par : </i>

$$
Y = \lbrace (Y_t, t) : t \in \mathbb{N}, Y_t \in \mathbb{R} \rbrace ~ avec ~  Y: \mathbb{N} \rightarrow \mathbb{R}
$$

<i>Ainsi, une série temporelle univariée se limite à l'évolution d'une variable unique dans le temps.<\i>
```

```{admonition} Série chronologique multivariée
<i> Une série chronologique multivariée peut être représentée par :<\i>

$$
Y = \lbrace (Y_t, t) : t \in \mathbb{N}, Y_t \in \mathbb{R}^{p} \rbrace ~ avec ~  Y: \mathbb{N} \rightarrow \mathbb{R}^{p}
$$

<i> Une série chronologique multivariée regroupe plusieurs séries univariées. Elle permet d'identifier les corrélations entre plusieurs variables évoluant dans le temps.</i>
```

#### 2. Décomposition d’une série chronologique

```{admonition} Décomposition d’une série chronologique

Un série temporelle  $(Y_t)$  repose sur la décomposition de la variable observée selon le temps en plusieurs composantes :

- la tendance (Trend component ou encore Trend-Cycle)  $T_t$ : observée sur une longue durée, elle traduit l’orientation (baisse ou hausse) générale de la série étudiée

-  La composante saisonnière (Seasonality component) $S_t$ : variation due à un effet momentané se reproduisant à intervalles réguliers

- La composante résiduelle (Noise term) $\eta_t$ : correspond à des fluctuations irrégulières, en général de faible intensité mais de nature aléatoire. On parle aussi  de ou bruit ou résidu
 
Ces éléments peuvent s'associer de manière :

- Additive : $Y_t = T_t + S_t + \eta_t$

-  Multiplicative : $Y_t = T_t \times S_t  \times \eta_t$

```



#### 3. Causalité and invisibilité

```{admonition} Définition

Un processus stochastique $(Y_t)$ est dit causal si il existe une suite réelle $\psi = (\psi_t)_{t \in \mathbb{Z}}$ telle que :

$$
Y_t = \mu + \sum_{j=0}^{\infty} \psi_j \eta_{t-j} ~~~~~,~~~~ t \in \mathbb{Z}
$$

Avec :

- $(\eta_j)$ est un bruit blanc de moyenne nulle et de variance $\sigma^2$ 

- $ \sum_{j=0}^{\infty} |\psi_j| < \infty$

```

```{admonition} Exercice
:class: warning


Soit $Y = (Y_t)$ le processus défini par :

$$
Y_t= 0,7 Y_{t-1} + \eta_t
$$

Chercher l’écriture causale de $(Y_t)$ 

$$
Y_t &= 0,7 Y_{t-1} + \eta_t \\
	&= 0,7 (0,7 Y_{t-2}+ \eta_{t-1}) + \eta_t \\
	&= 0,7^2Y_{t-2}+ 0,7 \eta_{t-1} + \eta_t \\
	&= 0,7^3Y_{t-3}+ 0,7^2 \eta_{t-2} + 0,7 \eta_{t-1} + \eta_t \\
	& = \cdots \\
	&= \eta_t+ 0,7 \eta_{t-1} + 0,7^2 \eta_{t-2} + \cdots \\
	&= \sum_{j=0}^{\infty} 0,7^j \eta_{t-j} \\
$$

Ce processus est donc causal.

```

```{admonition} Définition
Un processus stochastique $(Y_t)$ est dit inversible si il existe une suite réelle $\pi= (\pi_t)_{t \in \mathbb{Z}}$ telle que :

$$
\eta_t = \sum_{j=0}^{\infty} \pi_j Y_{t-j} ~~~~~,~~~~ t \in \mathbb{Z}
$$

Avec :

$$ \sum_{j=0}^{\infty} |\pi_j| < \infty
$$
```

```{admonition} Exercice
:class: warning

Considérons le processus suivant :

$$
Y_t = 0,8 \eta_{t-1}+ \eta_t ~~,~~ t \in \mathbb{Z} 
$$

Y est-l inversible ?

$$
Y_t = 0,8 \eta_{t-1}+ \eta_t & \Rightarrow \eta_t = Y_t - 0,8 \eta_{t-1} \\ 
& \Rightarrow \eta_t = Y_t - 0,8 (Y_{t-1}- 0,8 \eta_{t-2}) \\ 
& \Rightarrow \cdots \\
& \Rightarrow \eta_t = Y_t - 0,8 Y_{t-1}- 0,8^2Y_{t-2} - 0,8^3Y_{t-3}  - \cdots \\
& \Rightarrow \eta_t =  \sum_{j=0}^{\infty} 0,8^jY_{t-j}
$$

Donc $Y = (Y_t)$ est inversible
```


#### 4. Processus stationnaire


La stationnairité est la propriété d'une série temporelle à garder ses caractéristiques inchangées au passage du temps. 

Elle implique l'absence de tendance dans les données ainsi qu'une moyenne et variance constantes pour la Série Temporelle. On distingue deux types de stationnarité :



##### 4.1. Stationnairité au sens stricte


```{admonition} Définition
<i>Un processus $\lbrace Y_t, {t \in T}\rbrace$, est **stationnaire au sens stricte** si : </i> 

$$
{(Y_{t_{1}}, Y_{t_{2}}, \ldots, Y_{t_{k}})}^{t} \stackrel{\text{d}}{=} {(Y_{t_{1}+\tau}, Y_{t_{2}+ \tau}, \ldots, Y_{t_{k}+ \tau})}^{t}
$$

$$
\mathbb{P}(Y_{t_{1}} \leq y_{1}, \ldots ,Y_{t_{k}} \leq y_{k} ) =             \mathbb{P}(Y_{t_{1}+\tau} \leq y_{1}, \ldots ,Y_{t_{k}+\tau} \leq y_{k} ) 
$$

```

##### 4.2. Stationnairité au au second ordre

```{admonition} Stationnairité au au second ordre

<i>Le processus Y = $\lbrace Y_t , {t \in \mathbb{Z}\rbrace}$, est **stationnaire au second ordre** ou  au **sens faible (wide-sense stationary)** si :</i>

- $\mathbb{E}(Y_t) = cst ~~,~~ \forall t \in \mathbb{Z}$ indépendant de t

-  $E(Y^2_t) < \infty ~~,~~ \forall t \in \mathbb{Z}$

-  $\gamma_Y (k) = Cov(Y_t, Y_{t-k})  ~~,~~ \forall t \in \mathbf{Z}, \forall k \in \mathbb{Z}$ est indépendant de t.

```

```{admonition} Remarque
:class: tip

<i>Un processus $(Y_t)$ est faiblement stationnaire si ses moments ne dépend pas du temps.</i>
```

On pratique, la stationnairité au second ordre est la plus utilisée dans l'analyse des Série Temporelle et elle est souvent appelée stationnairité en covariance.


##### 4.3. White Noise


```{admonition} Définition
<i>Le processus stochastique $\lbrace \eta_t \rbrace_{t \in \mathbb{Z}}$, est **un bruit blanc (white noise)**  si : </i>

- $\mathbb{E}(\eta_t) = 0 ~~,~~ \forall t \in \mathbb{Z}$

-  $\mathbb{E}(\eta^2_t) = \sigma^2 ~~,~~ \forall t \in \mathbb{Z}$

-  $Cov(\eta_t, \eta_{t-k}) = 0 ~~,~~ \forall t \in \mathbb{Z}, \forall k \in \mathbb{Z}^{*}$

<i>On note $(\eta_t) \sim bb(0, \sigma^2 )$</i>
```


```{admonition} Remarque
:class: tip
Le processus stochastique $\lbrace \eta_t \rbrace_{t \in \mathbb{Z}}$, est un bruit blanc gaussien si $\eta_t$ $\sim$ i.i.d $N(0, \sigma^2)$
```



```{admonition} Exercice
:class: warning

On considère le modèle suivant :

$$
    Y_t = \eta_t + 2\eta_{t-1}
$$

Avec $(\eta_t) \stackrel{i.i.d}{\sim} ( 0, \sigma^2)$ et $t \in \mathbb{Z}$.

Mq $\lbrace Y_t \rbrace_{t \in \mathbb{Z}}$ est stationaraire au second ordre.

$$
    \mathbb{E}(Y_t) &=  \mathbb{E}( \eta_t + 2\eta_{t-1}) &~~(t ~ \in ~\mathbb{Z})\\
    & = \mathbb{E}( \eta_t)+2 \mathbb{E}(\eta_{t-1}) &~~(t ~\in ~ \mathbb{Z})\\
    & = 0 &~~(t ~\in ~\mathbb{Z})
$$

$$
    Var(Y_t) &= Var( \eta_t + 2\eta_{t-1}) &~~(t ~ \in ~\mathbb{Z})\\
    & =     Var( \eta_t)+ 2^2 Var(\eta_{t-1})+2 Cov(\eta_t,\eta_{t-1}) &~~(t ~ \in ~\mathbb{Z})\\
    & = 5\sigma^2 &~~(t ~ \in ~\mathbb{Z})
$$

$$
\gamma_Y(k) &= Cov(Y_t, Y_{t-k}) \\
& = Cov( \eta_t + 2\eta_{t-1},  \eta_{t+k} + 2\eta_{t-1+k})\\
& = Cov( \eta_t,  \eta_{t+k}) + 2Cov( \eta_t, \eta_{t-1+k}) + 2Cov(\eta_{t-1}, \eta_{t+k}) + 4Cov(\eta_{t-1}, \eta_{t-1+k})\\
& = \sigma^2(\mathbb{1}_{k=0}+2\mathbb{1}_{k=1}+2\mathbb{1}_{k=-1}+4\mathbb{1}_{k=0})\\
& = \sigma^2(5\mathbb{1}_{k=0}+2\mathbb{1}_{k=1}+2\mathbb{1}_{k=-1})
$$

$$
\gamma_Y(k)
& = \left\{
    \begin{array}{ll}
      5 \sigma^2   & \mbox{if } k = 0 \\
    2  \sigma^2 & \mbox{if } k = \pm 1\\
    0 & \mbox{Sinon}
    \end{array}
\right.
$$

Ainsi, $\lbrace Y_t \rbrace_{t \in \mathbb{Z}}$ est stationaraire au second ordre.

```


```{admonition} Exercice
:class: warning

On considère le modèle suivant :

$$
 Y_t = \alpha_0 + \alpha_1 \eta_t + \alpha_2 \eta_{t-1} ~~,~~ t \in \mathbb{Z}
$$

$$
(\alpha_0, \alpha_1, \alpha_2) \in \mathbf{R}^3~~ ,~~ (\eta_t) \stackrel{i.i.d}{\sim} ( 0, \sigma^2)
$$

Mq $\lbrace Y_t \rbrace_{t \in \mathbb{Z}}$ est un processus stationaraire en covariance.

$$
    \mathbb{E}(Y_t) &=  \mathbb{E}( \alpha_0 + \alpha_1 \eta_t + \alpha_2 \eta_{t-1}) &~~(t ~ \in ~\mathbb{Z})\\
    & = \alpha_0  + \alpha_1 \mathbb{E}( \eta_t)+ \alpha_2 \mathbb{E}(\eta_{t-1}) &~~(t ~\in ~ \mathbb{Z})\\
    & = \alpha_0 &~~(t ~\in ~\mathbb{Z})
$$

$$
    Var(Y_t) &= Var(\alpha_0 + \alpha_1 \eta_t + \alpha_2 \eta_{t-1}) &~~(t ~ \in ~\mathbb{Z})\\
     &= Var(\alpha_1 \eta_t + \alpha_2 \eta_{t-1}) &~~(t ~ \in ~\mathbb{Z})\\
    & =   \alpha_1^2  Var( \eta_t)+ \alpha_2^2 Var(\eta_{t-1})+\alpha_1 \alpha_2 Cov(\eta_t,\eta_{t-1}) &~~(t ~ \in ~\mathbb{Z})\\
    & = (\alpha_1^2 + \alpha_2^2 + \alpha_1 \alpha_1)\sigma^2 &~~(t ~ \in ~\mathbb{Z})
$$

$$
\gamma_Y(k) &= Cov(Y_t, Y_{t+k}) \\
& = Cov(\alpha_0 + \alpha_1 \eta_t + \alpha_2 \eta_{t-1},  \alpha_0 + \alpha_1 \eta_{t+k} + \alpha_2 \eta_{t+k-1})\\
& = \alpha_1^2Cov( \eta_t,  \eta_{t+k}) + \alpha_1\alpha_2Cov( \eta_t, \eta_{t-1+k}) \\ 
    &+\alpha_2\alpha_1Cov(\eta_{t-1}, \eta_{t+k}) + \alpha_2^2Cov(\eta_{t-1}, \eta_{t-1+k})\\
& = \sigma^2((\alpha_1^2 + \alpha_2^2)\mathbb{1}_{k=0}+\alpha_1\alpha_2\mathbb{1}_{k=1}+\alpha_1\alpha_2\mathbb{1}_{k=-1})
$$

$$
\gamma_Y(k)
& = \left\{
    \begin{array}{ll}
     ( \alpha_1^2 + \alpha_2^2 )\sigma^2   & \mbox{if } k = 0 \\
    \alpha_1\alpha_2  \sigma^2 & \mbox{if } k = \pm 1\\
    0 & \mbox{Sinon }
    \end{array}
\right.
$$

Ainsi, $\lbrace Y_t \rbrace_{t \in \mathbb{Z}}$ est un processus stationaraire en covariance.

```

```{admonition} Exercice
:class: warning

Supposons que :

$$
Y_t = Y_{t-1} + \eta_t ~~ ,~~ (\eta_t) \stackrel{i.i.d}{\sim} ( 0, \sigma^2)
$$

Etudier la stationnarité de $(Y_t)$.

$$
    Y_t = &Y_{t-1} + \eta_t ~~ ,~~ (\eta_t) \stackrel{i.i.d}{\sim} ( 0, \sigma^2) \\
    =& Y_{t-2} + \eta_{t-1} + \eta_t ~~ ,~~ (\eta_t) \stackrel{i.i.d}{\sim} ( 0, \sigma^2) \\
     = & Y_{t-3} + \eta_{t-2} + \eta_{t-1} + \eta_t ~~ ,~~ (\eta_t) \stackrel{i.i.d}{\sim} ( 0, \sigma^2) \\
    &  \vdots \\
    = & Y_0 + \sum_{j=0}^{t-1} \eta_{t-j}  ~~ ,~~ (\eta_t) \stackrel{i.i.d}{\sim} ( 0, \sigma^2) \\
$$

Ainsi:

$$
    \mathbb{E}(Y_t) &=  \mathbb{E}( Y_0 + \sum_{j=0}^{t-1} \eta_{t-j} ) &~~(t ~ \in ~\mathbb{Z})\\
    & = Y_0 = cst &~~(t ~\in ~\mathbb{Z})
$$

Aussi :

$$
    Var(Y_t) &= Var(Y_0 + \sum_{j=0}^{t-1} \eta_{t-j}) &~~(t ~ \in ~\mathbb{Z})\\
     &= Var( \sum_{j=0}^{t-1} \eta_{t-j}) &~~(t ~ \in ~\mathbb{Z})\\
     &= \sum_{j=0}^{t-1} Var(\eta_{t-j}) &~~(t ~ \in ~\mathbb{Z})\\
    & = t\sigma^2 &~~(t ~ \in ~\mathbb{Z})
$$

$$
\gamma_Y(k) &= Cov(Y_t, Y_{t+k}) \\
& = Cov(Y_0 + \sum_{j=0}^{t-1} \eta_{t-j},  y_0 + \sum_{j=0}^{t+k-1} \eta_{t-j})\\
& = Cov(\sum_{j=0}^{t-1} \eta_{t-j},  \sum_{j=0}^{t+k-1} \eta_{t-j})\\
& = \sigma^2  \underset{(t,k)\in \mathbb{Z}^2}{\mathrm{Min(t, t+k)}}
$$

Ainsi, le processus stochastique   $ \lbrace Y_t , {t \in \mathbb{Z}}\rbrace $,  n'est pas stationnaire au second ordre.

```

```{admonition} corollaire 
:class : tip

$\lbrace \eta_t \rbrace_{t \in \mathbb{Z}} \sim bb( 0, \sigma^2) \Rightarrow \lbrace \eta_t \rbrace_{t \in \mathbb{Z}}$  un processus faiblement stationnaire

```


```{admonition} Transformation des ST

- La transformation logarithmique : 

Cette technique est utilisée lorsque les données présentent une croissance exponentielle, pour obtenir une ST ayant une croissance linéaire.

- La différentiation :  

Est la technique la plus utilisée pour stationnariser les variables : différence première $\Delta X_t$, différence seconde $\Delta^2 X_t$.

- La différentiation logarithmique : 

Différence (d) sur les transformations logarithmiques.

```

```{admonition} Remarque importante
:class : tip

- Une série temporelle qui devient stationnaire après différentiation est dit : stationnaire en différence.

- Une série temporelle qui devient stationnaire après d différences est dit : intégrée d'ordre d.

```

#### 5. Les processus stochastiques


##### 5.1. Le processus moyenne mobile

```{admonition}  Définition
<i>On dit que la série chronologique $\lbrace Y_t \rbrace_{t \in \mathbb{Z}}$ est un processus moyenne mobile q si elle est définie, pour tout $t \in \mathbb{Z}$, par:</i>


$$
Y_t = \mu + \sum_{j=1}^{q} \theta_{j} \eta_{t-j}  + \eta_{t}
$$

Avec $\mu \in \mathbb{R}$, $\theta  = (\theta_1, \theta_2, \ldots, \theta_q)\in \mathbb{R}^q$ et  $(\eta_{t})  \stackrel{i.i.d}{\sim} (0, \sigma^2)$.

Pour signifier que le processus $(Y_t)$ est engendré par une moyenne mobile d’ordre q, nous noterons :

$$
\lbrace Y_t \rbrace_{t \in \mathbb{Z}} \sim MA(q)
$$
```

```{admonition} Remarque
:class: attention
**Attention aux notations !**

Les parenthèses autour de $(Y_t)$ sont ici indispensables : elles signifient que l’on considère le processus, alors que $Y_t$ sans parenthèses désigne la variable aléatoire extraite du processus à l’instant t.
```

```{admonition} Remarque
Par définition, le processus stochastique moyenne mobile MA(q) est toujours causal.
```

```{admonition} Proposition
:class: tip

Soit $(Y_t)$ $\sim$ MA(1) alors :

$$
\mathbb{E}(Y_t)=\mu~~,~~ Var(Y_t) = \sigma^2 (1+ \theta^2)
$$

$$
    \gamma_Y(k) = \sigma^2 (1+\theta^2)\mathbb{1}_{k=0} + \theta \sigma^2 \mathbb{1}_{k=1}
$$

$$
    \rho_Y(k) = \mathbb{1}_{k=0} +  \dfrac{\theta}{(1+\theta^2)} \mathbb{1}_{k=1}
$$
```


```{admonition}  Démonstration
Soit $(Y_t)$ $\sim$ MA(1) alors :

$$
    \mathbb{E}(Y_t)= \mathbb{E}(\mu + \theta \eta_{t-1} + \eta_{t})=\mu +  \mathbb{E}(\theta \eta_{t-1}) + \mathbb{E}( \eta_{t}) = \mu
$$

Aussi,

$$
    Var(Y_t)= Var(\mu + \theta \eta_{t-1} + \eta_{t}) =Var(\theta \eta_{t-1}) + Var(\eta_{t}) = \sigma^2 (1+ \theta^2)
$$

$$
    \gamma_Y(k)&= Cov(Y_t, Y_{t+k})\\
    & = Cov(\mu + \theta \eta_{t-1} + \eta_{t} , \mu + \theta \eta_{t+k-1} + \eta_{t+k}) \\
    & =Cov(\theta \eta_{t-1} + \eta_{t} , \theta \eta_{t+k-1} + \eta_{t+k}) \\
    &= Cov(\theta \eta_{t-1} , \theta \eta_{t+k-1}) + Cov(\theta \eta_{t-1} , \eta_{t+k}) + Cov(\eta_{t} , \theta \eta_{t+k-1}) + Cov(\eta_{t} , \eta_{t+k}) \\
    & =\theta^2\mathbb{1}_{k=0} + \theta \sigma^2 \mathbb{1}_{k=1} + \sigma^2\mathbb{1}_{k=0}\\
    &= \sigma^2 (1+\theta^2)\mathbb{1}_{k=0} + \theta \sigma^2 \mathbb{1}_{k=1}
$$

Ainsi,

$$
    \rho_Y(k) &= \dfrac{\gamma_Y(k)}{\gamma_Y(0)} ~~~~~~~~~~~~~~,~~~~ \text{Avec} ~~~\gamma_Y(0) = Var(Y_t) \\
    & = \mathbb{1}_{k=0} +  \dfrac{\theta}{(1+\theta^2)} \mathbb{1}_{k=1}\\
    &= 
    \left\{
    \begin{array}{ll}
   1  & \mbox{ , k = 0 }\\
\dfrac{\theta}{(1+\theta^2)} & \mbox{, k = 1} \\
0  & \mbox{,Sinon}
      \end{array}
\right.
$$
```

```{admonition}  EXERCICE
:class: warning

Soient $\epsilon_t$ et $(\eta_t)$ deux bruits blancs de moyenne nulle et de variance $\sigma^2$, et $\theta \in \left]-1;1\right[\setminus{0}$. 

On suppose que :

$$
X_t = \epsilon_t + \theta \epsilon_{t-1} ~~~~~~,~~~~~~Y_t = \eta_t + \dfrac{1}{\theta}\eta_{t-1}
$$ 

**Questions**

-  Déterminer le type des processus $(X_t)$ et $(Y_t)$ ?
 
-  $(X_t)$ et $(Y_t)$ sont-elles stationnaires ?

-  $(X_t)$ et $(Y_t)$  sont-elles causales ?

- Montrer que les séries $(X_t)$ et $(Y_t)$ ont les mêmes fonctions d'autocorélation.

```
```{admonition}  EXERCICE
:class: warning

Soit X= $(X_t)$ un processus stochastique tel que :

$$
X_t = -0,35\eta_{t-1} + \eta_t
$$

Avec $(\eta_t)$ est un bruit blanc de moyenne nulle et de variance $\sigma^2$.

**Questions**

-  Est-il stationnaire en covariance ?

-  Est-il causal ?

-  Est-il inversible ?


-  On notee  $\psi_j$ les coefficients du processus $MA(\infty)$ correspondant à ce processus :

- a). calculer alors les coefficients $\psi_1$, $\psi_2$, $\psi_3$, $\psi_4$, $\psi_5$ et $\psi_6$.

- b). Déterminer $\psi_{2023}$

```
```{admonition}  Proposition
Si $(Y_t)$ $\sim$ MA(2) alors :

$$
\mathbb{E}(Y_t)=\mu~~,~~ Var(Y_t) = \sigma^2 (1+\sum_{j=1}^{q} \theta_{j}^2)
$$

$$
    \gamma_Y(k) = \sigma^2 (\theta_k + \sum_{j=1}^{q-k} \theta_{j} \theta_{k+j})\mathbb{1}_{k\in [1,q]}
$$
```



```{admonition} Théorème
Soit $(Y_t)$ $\sim$ MA(q) alors :

$$
\mathbb{E}(Y_t)=\mu~~,~~ Var(Y_t) = \sigma^2 (1+\sum_{j=1}^{q} \theta_{j}^2)
$$

$$
    \gamma_Y(k) = \sigma^2 (\theta_k + \sum_{j=1}^{q-k} \theta_{j} \theta_{k+j})\mathbb{1}_{k\in [1,q]}
$$
```

```{admonition} Théorème
Si $\lbrace Y_t \rbrace_{t \in \mathbb{Z}}$ MA(q) alors $\lbrace Y_t \rbrace_{t \in \mathbb{Z}}$ est nécessairement stationnaire.
```

```{admonition} Démonstration
Soit t $\in \mathbb{Z}$ and $\theta_j \in \mathbb{R}$. Supposons que $(Y_t)$ $\sim$ MA(q) tels que :

$$
Y_t = \mu + \sum_{j=1}^{q} \theta_{j} \eta_{t-j} + \eta_{t} ~~,~~(\eta_{t})  \stackrel{i.i.d}{\sim} (0, \sigma^2)
$$

D'où,

$$
    \mathbb{E}(Y_t) & = \mathbb{E}( \mu + \sum_{j=1}^{q} \theta_{j} \eta_{t-j} \ + \eta_{t})\\
    & = \mu + \sum_{j=1}^{q}\theta_{j} \mathbb{E}( \eta_{t-j})  +\mathbb{E}(\eta_{t})\\
    & = \mu
$$

$$
Var(Y_t) & = Var( \mu + \sum_{j=1}^{q} \theta_{j} \eta_{t-j} + \eta_{t})\\
    & = Var(\sum_{j=1}^{q} \theta_{j} \eta_{t-j}  + \eta_{t})\\
    & = \sum_{j=1}^{q} \theta_{j}^2Var( \eta_{t-j}) + Var(\eta_{t})\\
        & = \sigma^2\sum_{j=1}^{q} \theta_{j}^2 + \sigma^2\\
        & = \sigma^2(1+\sum_{j=1}^{q} \theta_{j}^2)
$$

Aussi,

$$
\gamma_Y(k) & = Cov( \mu + \sum_{j=1}^{q} \theta_{j} \eta_{t-j} + \eta_{t}~,~ \mu + \sum_{j=1}^{q} \theta_{j} \eta_{t+k-j} + \eta_{t+k})\\
    & = Cov( \sum_{j=1}^{q} \theta_{j} \eta_{t-j} + \eta_{t}~,~ \sum_{j=1}^{q} \theta_{j} \eta_{t+k-j} + \eta_{t+k})\\
    & = Cov( \sum_{j=1}^{q} \theta_{j} \eta_{t-j} ~,~ \sum_{j=1}^{q} \theta_{j} \eta_{t+k-j})  + Cov( \sum_{j=1}^{q} \theta_{j} \eta_{t-j} ~,~  + \eta_{t+k})\\ &+ Cov(\eta_{t}~,~ \sum_{j=1}^{q} \theta_{j} \eta_{t+k-j}) + Cov( \eta_{t}~,~ \eta_{t+k}) \\
    & = 
$$

Ainsi, si le processus $\lbrace Y_t \rbrace_{t \in \mathbb{Z}}$ suit un MA(q) alors $\lbrace Y_t \rbrace_{t \in \mathbb{Z}}$ est nécessairement stationnaire.
```

```{admonition} Theorème
Soit $(X_t)$ $\sim$ MA(q) tel que :

$$
X_t = \mu + \Theta(B)\eta_t
$$

$(X_t)$ est inversible si ses racines sont de modules supérieurs à 1. Autrement dit :

$$
\lbrace z : \Theta(z)= 0\rbrace \subseteq \lbrace z : |z|>1\rbrace
$$
```

```{admonition} Exercice
:class: warning


Soit le processus $(X_t)$  de type MA(q) suivant:

$$
X_t  = 0.4 -0.2\eta_{t-1} + \eta_t
$$


Où $(a_t)$ est un bruit blanc de variance notée $\sigma^2$

-  De quel type est le processus  $(X_t)$ ?

-  Déterminer le nombre de retard q associé à ce processus.

-  Calculez l’espérance et la variance du processus  $(X_t)$. 

-  Le processus est-il stationnaire ? Justifier votre réponse!

-  Calculer sa fonction d'autocorrélation $\rho$.

-  Le processus est-il causal ? justifier.

-  Le processus est-il inversible ? 

-  On note  $\pi_j$ les coefficients du processus $AR(\infty)$ correspondant à ce processus, calculer alors les coefficients $\pi_1$, $\pi_2$, $\pi_3$, $\pi_4$, $\pi_5$ et $\pi_6$.
```

##### 5.2. Le processus autorégressif


```{admonition} Définition
<i>On dit que la série chronologique $\lbrace Y_t \rbrace_{t \in \mathbb{Z}}$ est un processus autorégressif d’ordre p si elle est définie, pour tout $t \in \mathbb{Z}$, par:</i>

$$
Y_t = \mu + \sum_{j=1}^{p} \Phi_{j} Y_{t-j}  + \eta_{t} ~~~~,~~~~ (\forall t \in \mathbb{Z})
$$

ou encore :

$$
    Y_t = \mu + \Phi_{1} Y_{t-1} + \Phi_{2} Y_{t-2} + \ldots + \Phi_{p} Y_{t-p} + \eta_{t}  ~~~,~~~ (\forall t \in \mathbb{Z})
$$

Avec $\mu \in \mathbb{R}$ , $\Phi  = (\Phi_1, \Phi_2, \ldots, \Phi_p)\in \mathbb{R}^p$ et $\eta_{t}  \stackrel{i.i.d}{\sim} (0, \sigma^2)$.

Pour signifier que le processus $(Y_t)$ est engendré par un processus autorégressif d’ordre p, nous noterons :


$$
\lbrace Y_t \rbrace_{t \in \mathbb{Z}} \sim AR(p)
$$

```

```{admonition} Remarque

Par définition, le processus autorégressif AR(p) est toujours inversible.

```

```{admonition} Théorème
Soit $(Y_t)$ $\sim$ AR(p).

Le processus $(Y_t)$ stationnaire et causal si si les racines du polynôme $A(z) = 1 − \phi_1z −· · ·- \phi_pz^p$ sont de module strictement supérieur à 1. 


```
```{admonition} Proposition
:class: important


$$
    (Y_t) \sim AR(1) \Rightarrow 
    \begin{cases}
     \mathbb{E}(Y_t) =  \dfrac{\mu}{1-\Phi}  \\
     Var(Y_t) =  \dfrac{\sigma^2}{1-\Phi^2}  \\
     \gamma_Y(k) = \dfrac{\sigma^2}{1-\Phi^2}\Phi^k ~~,~ k \in \mathbb{N} \\
     \rho_Y(k) = \Phi^k ~~, ~k \in \mathbb{N}
    \end{cases}
$$

```

```{admonition} Preuve
On considère $(Y_t) \sim AR(1)$. Ainsi ,

$$
    Y_t = \mu +  \Phi Y_{t-1}+ \eta_{t}
$$

Avec $|\Phi|<1$, $\mu \in \mathbb{R}$ and $\eta_{t}  \stackrel{i.i.d}{\sim} (0, \sigma^2)$

$$
    Y_t = \mu +  \Phi Y_{t-1}+ \eta_{t} &\Rightarrow
    Y_{t} - \Phi Y_{t-1}= \mu + \eta_{t}  \\
        & \Rightarrow Y_{t} -\Phi B Y_{t} = \mu + \eta_{t}  \\
    & \Rightarrow (1-\Phi B) Y_{t} = \mu + \eta_{t}  \\
        & \Rightarrow Y_{t} = \sum_{j \geq 0} (\Phi B)^{j} (\mu + \eta_{t})  ~~~,~if ~~ |\Phi|< 1\\
 & \Rightarrow Y_{t} = \sum_{j \geq 0} (\Phi B)^{j}\mu + \sum_{j \geq 0} (\Phi B)^{j} \eta_{t}  \\
  & \Rightarrow Y_{t} = \sum_{j \geq 0} (\Phi)^{j}\mu + \sum_{j \geq 0} \Phi^{j} \eta_{t-j}  \\
    & \Rightarrow Y_{t} = \dfrac{\mu}{1-\Phi} + \sum_{j \geq 0} \Phi^{j} \eta_{t-j}  \\
$$

Aussi,

$$
    \mathbb{E}(Y_t) &=     \mathbb{E}(\dfrac{\mu}{1-\Phi} + \sum_{j \geq 0} \Phi^{j} \eta_{t-j}) = \dfrac{\mu}{1-\Phi} \\
Var(Y_t) &=  Var(\dfrac{\mu}{1-\Phi} + \sum_{j \geq 0} \Phi^{j} \eta_{t-j}) = \dfrac{\sigma^2}{1-\Phi^2} \\
     \gamma_Y(k) &= Cov(Y_t, Y_{t+k}) =\dfrac{\sigma^2}{1-\Phi^2}\Phi^k ~~,~ k \in \mathbb{N} \\
     \rho_Y(k) &= \dfrac{\gamma_Y(k) }{\gamma_Y(0) }\Phi^k ~~, ~k \in \mathbb{N}
$$

```


```{admonition} Théorème
On considère $\lbrace Y_t \rbrace_{t \in \mathbb{Z}} \sim AR(1)$. Si $\Phi = 1$ alors  $\lbrace Y_t \rbrace_{t \in \mathbb{Z}}$ est un processus non stationnaire
```

```{admonition} Preuve
Soit $\lbrace Y_t \rbrace_{t \in \mathbb{Z}} \sim AR(1)$.

On suppose que $\Phi = 1$. Alors :

$Y_t = \mu + \Phi Y_{t-1} + \eta_t = \mu + Y_{t-1} + \eta_t$

$$
Y_1 & = \mu + Y_{0} + \eta_1  \\
Y_2 &= \mu + Y_{1} + \eta_{2}  \\
Y_3 &=  \mu + Y_{2} + \eta_{3} \\
&  \vdots \\
Y_t &= \mu + Y_{t-1} +  \eta_{t}\\
&-------\\
\sum_{i=1}^t Y_i & = \sum_{i=1}^t \mu + \sum_{i=1}^t Y_{i-1} + \sum_{i=1}^t  \eta_i \\
\sum_{i=1}^t  Y_i - \sum_{i=1}^t  Y_{i-1} &= \sum_{i=1}^t  \mu + \sum_{i=1}^t  \eta_i \\
Y_t - Y_{0} &= t \mu + \sum_{i=1}^t  \eta_i \\
$$

D'où, 

$$
\lbrace Y_t \rbrace_{t \in \mathbb{Z}} \sim AR(1) ~~\land~~  \Phi = 1  &\Rightarrow Y_t = t \mu + Y_{0} + \sum_{i=1}^t  \eta_i \\
&\Rightarrow \mathbb{E}(Y_t) = t \mu + Y_{0} ~~ \land ~~  Var(Y_t) = t\sigma^2\\
&\Rightarrow \lbrace Y_t \rbrace_{t \in \mathbb{Z}}~~ \mbox{n'est pas un processus stationnaire}
$$

```



```{admonition} Définition
Soit  $Y = \lbrace Y_t, t \in \mathbb{Z} \rbrace$  un processus autoregressive d'ordre 2, AR(2). 

$$
    Y_t = \mu + \Phi_{1} Y_{t-1} + \Phi_{2} Y_{t-2} + \eta_{t}
$$

Avec $\mu \in \mathbb{R}$ , $\Phi  = (\Phi_1, \Phi_2)\in \mathbb{R}^{2}$ et $\eta_{t}  \stackrel{i.i.d}{\sim} (0, \sigma^2)$.


$Y$ est stationnaire et causal si les racines du polynôme $A(z) = 1 − \phi_1z − \phi_2z^2$ sont de module strictement supérieur à 1. 


```

```{admonition} Exercice
:class: warning
Nous supposons que le rendement quotidien des séries temporelles à l’instant t peut s’exprimer comme suit :

$$
    r_t = 0.5 - 0.2r_{t-1} + 0.48r_{t-2} +\zeta_t  ~~,~~(\zeta_{t})  \stackrel{i.i.d}{\sim} (0, \sigma^2)
$$

Soit alors $(\zeta_{t})  \stackrel{i.i.d}{\sim} (0, \sigma^2)$ et $t \in \mathbb{Z}$

$$
     r_t = 0.5 - 0.2r_{t-1} + 0.48r_{t-2} +\zeta_t  &\Rightarrow       r_t + 0.2r_{t-1} - 0.48r_{t-2} = 0.5 +\zeta_t  \\
      &\Rightarrow       r_t + 0.2Br_{t} - 0.48B^2r_{t} = 0.5 +\zeta_t  \\
            &\Rightarrow       (1 + 0.2B - 0.48B^2)r_t = 0.5 +\zeta_t \\
                        &\Rightarrow       A(B)r_t = 0.5 +\zeta_t 
$$

Avec $A(z) = (1 + 0.2z - 0.48z^2)$ indique l'équation characteristique.

Cherchons alors les racines de A. Il est à noter que les racines du polynome quadratique $ax^2+bx+c=0$ sont données par $\dfrac{-b \pm \sqrt{b^2-4ac}}{2a}$ , si a $\neq$ 0.

$$
A(z) = 0 \Rightarrow z_1 = -\dfrac{5}{4} \vee z_2 =\dfrac{5}{3} 
$$

Ainsi, $\lbrace r_t \rbrace_{t \in \mathbb{Z}}$ est causal et strictement stationnaire puisque toutes les racines A(z) sont outside du  circle unitaire (i.e. $|z_j|>1 ~,~ j \in \lbrace  1,2\rbrace )$.

```

```{admonition} Exercice
:class: warning

Considérons le processus stochastique suivant :

$$
    \pi_t = 0.5 + 1.2\pi_{t-1} + 1.2\pi_{t-2} + \eta_t ~~,~~ t \in \mathbb{Z}
$$

Avec $(\eta_t)$ est le white noise usuel.

$$
        \pi_t = 0.5 + 1.2\pi_{t-1} + 1.2\pi_{t-2} + \eta_t &\Rightarrow         \pi_t -1.2 \pi_{t-1} - 1.2\pi_{t-2}= 0.5  + \eta_t \\
        &\Rightarrow         (1-1.2B - 1.2B^2)\pi_t = 0.5  + \eta_t \\
                &\Rightarrow         A(B)\pi_t = 0.5  + \eta_t
$$

Ainsi, l'équation characteristique est donnée par $A(z) = 1-1.2z - 1.2z^2= 0$.

$$
    \Delta_A > 0 &\Rightarrow z_1 = -\dfrac{3+\sqrt{39}}{4} \approx-1.54 \vee z_2= \dfrac{-3+\sqrt{39}}{4}\approx0.54 \\
    &\Rightarrow \exists ~ (i \in \lbrace 1, 2 \rbrace) ~;~ |z_i| <  1 \\
    &\Rightarrow \lbrace \pi_t , t \in \mathbb{Z}\rbrace ~~ processus ~~ explosif
$$
```

Graphiquement, on peut montrer que les racines inverses de notre série chronologique se trouvent dans le cercle unité. En effet, au moins une de ses racines réelles $z_1\approx -1.54$ , $z_2\approx 0.54$, est en dehors du cercle unité ce qui signifie que le processus est explosif (non stationnaire).


```{admonition} Théorème

$$
    (Y_t) \sim AR(2) \Rightarrow 
    \begin{cases}
     \mathbb{E}(Y_t) &= \dfrac{\mu}{1-\Phi_1 - \Phi_2} \\
     Var(Y_t) & =\dfrac{\sigma^2}{1-\Phi_1 \rho_Y(1)- \Phi_2 \rho_Y(2)}\\
     \rho_Y(2) & =\Phi_1 \rho_Y(1)+ \Phi_2 \\
        \rho_Y(k) & =\Phi_1 \rho_Y(k-1)+ \Phi_2 \rho_Y(k-2) ~~,~~ k \in \mathbb{N}^{*}
    \end{cases}
$$
```





##### 5.3. Processus autorégressifs et moyennes mobiles

```{admonition} Définition
Les processus ARMA généralise les modèles autorégressifs et moyennes mobiles. Ces processus sont très
utiles en pratique pour modéliser des séries éonomiques et financières en nécessitant moins de paramètres que les modèles AR ou
MA simples.
```
```{admonition} Définition
On dit que la série chronologique $(y_t)$ définie sur $\mathbb{Z}$ est un processus autorégressif moyenne mobile d’ordre (p, q) si elle est définie, pour tout t $\in \mathbb{Z}$, par

$$
y_t = \mu + \sum_{j=1}^{p} \Phi_{j} y_{t-j} + \sum_{j=1}^{q} \theta_j \eta_{t-j} + \eta_{t}
$$

$$
y_t -  \underbrace{\Phi_1y_{t-1} - \ldots - \Phi_py_{t-p}}_{AR(p)~ part} = \underbrace{\mu + \theta_1\eta_{t-1} + \ldots + \theta_{q}\eta_{t-q} + \eta_{t}}_{MA(q) ~ part}
$$

Where :

- $(\eta_t)$ est un white noise tel que $(\eta_t)$ $\sim$ WN (0 , $\sigma^2$).

- $\Phi_1, \Phi_2, \ldots \Phi_p $ representent les coefficients du modèle MA.

-  $\theta_1, \theta_2, \ldots \theta_q $ representent les coefficients du modèle AR.

-  $\mu$ $\in$ $\mathbb{R}$ represente le terme constant.

Pour signifier que le processus $(y_t)$ est un autorégressif moyenne mobile d’ordre (p, q), nous noterons :

$$
(y_t) \sim ARMA(p,q)
$$

```


l’application de l’opérateur retard (B) conduit à l'écriture suivante :

$$
\Phi_p (B)y_t = \Theta_q(B)\eta_t
$$

Avec

$$
      \begin{cases}
      B^{k}y_{t} =y_{t-k} ~ , ~~~ \forall ~~ k \in \mathbb{N} \\
\Phi(B) = 1- \Phi_1 B - \Phi_2 B^2 - \ldots - \Phi_p B^p \\
\Theta(B) = 1- \theta_1 B - \theta_2 B^2 - \ldots - \theta_q B^q
	\end{cases}
$$


```{admonition} Exercice


-  ARMA(1,0)= AR(1) :

$\Phi_1 (B)y_t = \Theta_1(B)\eta_t  \Leftrightarrow y_t = \Phi_1 y_{t-1}$

- ARMA(0,1)= MA(1) :
    
$\Phi_1 (B)y_t = \Theta_1(B)\eta_t  \Leftrightarrow y_t = \Theta_1\eta_{t-1} + \eta_t $.

- ARMA(1,1) :
    
$\Phi_1 (B)y_t = \Theta_1(B)\eta_t  \Leftrightarrow y_t = \Phi_1 y_{t-1} + \Theta_1\eta_{t-1} + \eta_t $.

- ARMA(2,1) :

$\Phi_2 (B)y_t = \Theta_1(B)\eta_t  \Leftrightarrow y_t = \Phi_1 y_{t-1} + \Phi_2 y_{t-2} + \theta_1\eta_{t-1} + \eta_t $.

- ARMA(1,2) :
    
$\Phi_1 (B)y_t = \Theta_2(B)\eta_t  \Leftrightarrow y_t =  \Phi_1 y_{t-1}+ \theta_2 \eta_{t-2} + \theta_1\eta_{t-1} + \eta_t $.

-  ARMA(2,2) :

$\Phi_2 (B)y_t = \Theta_2(B)\eta_t  \Leftrightarrow y_t = \Phi_1 y_{t-1}+ \Phi_2 y_{t-2} + \theta_2 \eta_{t-2} + \theta_1\eta_{t-1} + \eta_t $

```

```{admonition} Remarque

-  Quand q = 0 alors ARMA(p,0) $\equiv	$ AR(p):
    
$$
y_t = \Phi_1y_{t-1} + \Phi_2y_{t-2} + \ldots + \Phi_py_{t-p}
$$

-  Quand p = 0 alors ARMA(0,q) $\equiv	$ MA(q):
    
$$
y_t = \theta_1\eta_{t-1} + \theta_2\eta_{t-2} + \ldots + \theta_q\eta_{t-q} + \eta_t
$$
```

```{admonition} Exercice

Soit $(X_t)$ un ARMA(2,2) tel que $\Phi_1= 3$, $\Phi_2= 6$, $\theta_1=-\dfrac{14}{3}$ and $\theta_1=5$. 

- $(X_t)$  est-il un processus causal ?


$$
        X_t -3X_{t-1}-6X_{t-2} &= \eta_t -\dfrac{14}{3}\eta_{t-1} + 5\eta_{t-2} ~~ , ~~~ (\eta_t) \sim WN (0 , \sigma^2) \\
(1 -3B-6B^2)X_t &= (1 -\dfrac{14}{3}B + 5B^2)\eta_t ~~ , ~~~ (\eta_t) \sim WN (0 , \sigma^2)
$$

$(X_t)$ peut être exprimé :

$$
 \begin{align*}
(1 -2L)(1-3L)X_t &= (1 -3L)(1-\dfrac{14}{3})\eta_t ~~ , ~~~ (\eta_t) \sim WN (0 , \sigma^2) \\
(1 -2L)X_t &= (1-\dfrac{14}{3})\eta_t ~~ , ~~~ (\eta_t) \sim WN (0 , \sigma^2)
\end{align*}
$$

Ainsi, $(X_t)$  est un ARMA(2,2) causal et stationnaire (les racines du polynôme characteristique associé sont superieures à un), avec : 

$$
  X_t = 2y_{t-1} +\eta_t -\dfrac{14}{3}\eta_t ~ , ~ (\eta_t) \sim WN (0 , \sigma^2)  
$$

puisque elle est surparametré ( peut être paramétré à un processus ARMA(1,1)).
```

```{admonition} Remarque
Pour idéntifier les MA(q) and AR(p), on peut utiliser les ACF et PACF. 
```

#### 6. Prévision des séries chroniques

##### 6.1. Le modèle naïf

```{admonition} Le modèle naïf
Dans une prévision naïve, la prévision pour l'instant t correspond à la valeur de données à l'instant t -1.

$$
\hat{Y}_{T+h|T}=Y_t
$$

Il suffit alors de reconduire de manière constante la dernière valeur connue du passé pour l'avenir. On parle de prévision naïve.

```

##### 6.2. Average Forecast

```{admonition} Average Forecast
Dans Average Forecast, la prévision pour l'instant t correspond à la moyenne de la série étudiée.

$$
\hat{Y}_{T+h|T}=\overline{Y_t}
$$

```
##### 6.3. Prévision dans un processus autorégressif

```{admonition} Prévision dans un processus autorégressif

La prévision optimale d’un processus autorégressif AR(p):

$$
X_t =  \phi_1 X_{t-1} + \phi_2 X_{t-2} + ... + \phi_p X_{t-p} + \mu + \eta_{t}
$$

à la date t + 1, faite à la date t, $\hat{X}_{t+1}$, est :

$$
\hat{X}_{t+1} =  \phi_1 X_{t} + \phi_2 X_{t-1} + ... + \phi_p X_{t-p+1} + \mu 
$$

```

```{admonition} Exercice
On vous donne les valeurs suivantes d'une série $(X_t)$,

| t | 1   | 2   | 3   | 4    | 5 | 6   | 7   |
|:---:|:---:|:---:|:---:|:----:|:---:|:---:|:---:|
| X | 2,5 | 5,3 | 1,1 | -1,9 | 3 | 2,8 | 2,6 |

Après analyse, le modèle suivant est jugé adéquat pour cette série temporelle :

$$
X_t = 1,4 - 0,2 X_{t-1}- 1,2 X_{t-2} + 2,7 X_{t-3} + \eta_t
$$

avec $(\eta_t) \sim WN(0, 4)$.

-  Donner l'expression de $\hat{X}_{t+1}$.

- Calculer la meilleure prévision de $\hat{X_8}$.

```

```{admonition} Exercice
On vous donne les valeurs suivantes d'une série chronique $(X_t)$ ,


| t | 1   | 2   | 3   | 4    | 5 | 6   | 7   |
|:---:|:---:|:---:|:---:|:----:|:---:|:---:|:---:|
| X | 2,5 | 5,3 | 1,1 | -1,9 | 3 | 2,8 | 2,6 |


Après analyse, le modèle suivant est jugé adéquat pour cette série $(\eta_t) \sim WN(0, 4)$


![A test image](26.JPG)


- Donner l'expression explicite de $(X_t)$.

- Donner l'expression de $\hat{X}_{t+1}$.

-  Calculer la meilleure prévision de $\hat{X_8}$.

```

###### 6.3.1 Prévisions d’un processus autorégressif AR(1) à horizon 1

```{admonition} Prévisions d’un processus autorégressif AR(1) à horizon 1
Pour un processus AR(1) : $X_t = \phi X_{t-1}+ \mu + \eta_t$

Si $|\phi|<1$ alors La prévision optimale à la date t + 1, $\hat{X}_{t+1}$, est : 

$$
\hat{X}_{t+1} = \phi X_{t}+ \mu
$$
```

###### 6.3.2 Prévisions d’un processus autorégressif AR(1) à horizon k

```{admonition} Prévisions d’un processus autorégressif AR(1) à horizon k
Pour un processus AR(1) : $X_t = \phi X_{t-1}+ \mu + \eta_t$

Si $|\phi|<1$ alors La prévision optimale à la date t + k, $\hat{X}_{t+k}$, est 

$$
\hat{X}_{t+k} = \phi^k X_{t}+ \mu \sum_{j=0}^{k-1} \phi^j
$$

```

```{admonition} Démonstration

$$
X_t = \phi X_{t-1}+ \mu + \eta_t & \Rightarrow \hat{X}_{t+1} = \phi X_{t}+ \mu \\
& \Rightarrow \hat{X}_{t+2} = \phi \hat{X}_{t+1}+ \mu \\
& \Rightarrow \hat{X}_{t+2} = \phi (\phi X_{t}+ \mu)+ \mu \\
& \Rightarrow \hat{X}_{t+2} = \phi^2 X_{t}+ \phi \mu+ \mu \\
& \Rightarrow \hat{X}_{t+3} = \phi \hat{X}_{t+2}+ \mu \\
& \Rightarrow \hat{X}_{t+3} = \phi^3 X_{t}+\phi^2 \mu+ \phi \mu+ \mu \\
& ~~~~~\vdots  ~~~~~~~~~~~~~~~~~~~~~~\vdots \\
& \Rightarrow \hat{X}_{t+k} = \phi^k X_{t}+ \mu \sum_{j=0}^{k-1} \phi^j
$$

```
###### 6.3.3 Prévisions d’un processus autorégressif AR(2) à horizon k

```{admonition} Prévisions d’un processus autorégressif AR(2) à horizon k

Pour un processus AR(2) :

$$
X_t= \phi_1X_{t-1} + \phi_2X_{t-2} + \mu + \eta_t
$$

La prévision optimale à la date t + 1, $\hat{X}_{t+1}$, est :

$$
\hat{X}_{t+1}= \phi_1X_{t} + \phi_2X_{t-1} + \mu
$$


La prévision optimale à la date t + 2, $\hat{X}_{t+2}$, est :

$$
\hat{X}_{t+2}= \phi_1\hat{X}_{t+1} + \phi_2X_{t} + \mu
$$


La prévision optimale à la date t + 3, $\hat{X}_{t+3}$, est :

$$
\hat{X}_{t+3}= \phi_1\hat{X}_{t+2} + \phi_2\hat{X}_{t+1} + \mu
$$

```

```{admonition} Exercice
On vous donne les valeurs suivantes d'une série $(X_t)$ ,


| t | 1   | 2   | 3   | 4    | 5 | 6   | 7   |
|:---:|:---:|:---:|:---:|:----:|:---:|:---:|:---:|
| X | 2,5 | 5,3 | 1,1 | -1,9 | 3 | 2,8 | 2,6 |


Après analyse, le modèle suivant est jugé adéquat pour cette série $(\eta_t) \sim WN(0, 4)$


![A test image](26.JPG)

- Donner l'expression de $\hat{X}_{t+1}$, $\hat{X}_{t+2}$ et $\hat{X}_{t+3}$.

- Calculer la meilleure prévision de $\hat{X_8}$, $\hat{X_9}$ et $\hat{X_{10}}$.

```

##### 6.4. Prévision dans les processus moyenne mobile

La prévision optimale d’un processus MA(1) :

$$
X_t = \mu + \theta \eta_{t-1} + \eta_{t}
$$

à la date t + 1, faite à la date t, $\hat{X}_{t+1}$, est :

$$
\hat{X}_{t+1} = \mu + \theta \eta_{t}
$$

Pour $k \geq 2$, la prévision optimale à la date t + k, $\hat{X}_{t+k} $, est

$$
\hat{X}_{t+k} = \mu
$$

```{admonition} Remarque
C’est à dire qu’à partir d’un horizon 2, la meilleure prévision pour
un processus Moyenne Mobile MA(1) est la moyenne du processus.
```

```{admonition} La prévision optimale d’un processus MA(p)
A partir d’un horizon k, la meilleure prévision pour
un processus Moyenne Mobile MA(p) est la moyenne du processus $(k\geq p+1)$
$$
\hat{X}_{t+k} = \mu ~~~~, ~~ \forall k \geq p +1
$$
```




```

```
