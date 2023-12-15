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


**Exemple** : 

Série chronologique économique : PIB, taux d'inflation .

Série chronologique financière : CAC40, Oil .


```{admonition} Pourquoi analyse t-on les SC ?
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

Un série temporelle  $Y_t$  repose sur la décomposition de la variable observée selon le temps en plusieurs composantes :

- la tendance (Trend component ou encore Trend-Cycle)  $T_t$ : observée sur une longue durée, elle traduit l’orientation (baisse ou hausse) générale de la série étudiée

-  La composante saisonnière (Seasonality component) $S_t$ : variation due à un effet momentané se reproduisant à intervalles réguliers

- La composante résiduelle (Noise term) $\eta_t$ : correspond à des fluctuations irrégulières, en général de faible intensité mais de nature aléatoire. On parle aussi  de ou bruit ou résidu
 
Ces éléments peuvent s'associer de manière :

- Additive : $Y_t = T_t + S_t + \eta_t$

-  Multiplicative : $Y_t = T_t \times S_t  \times \eta_t$

```


```{admonition} Remarque
The main interest of this decomposition is to understand and better describe the evolution of the series studied, and on the other hand to forecast their evolution over time (based on the trend and seasonal variations).
```


#### 3. Causalité and invisibilité

```{admonition} Définition

Un processus stochastique $(Y_t)$ est dit causal si il existe une constante $\psi_j$ telle que :

$$
Y_t = \sum_{j=1}^{\infty} \psi_j \eta_{t-j} ~~~~~,~~~~ t \in \mathbb{Z}
$$

Avec $\eta_j$ est un bruit blanc de moyenne nulle et de variance $\sigma^2$ et $ \sum_{j=1}^{\infty} |\psi_j| < \infty$

```

```{admonition} Définition
Un processus stochastique $(Y_t)$ est dit inversible si il existe une constante $\pi_j$ telle que :

$$
Y_t = \sum_{j=1}^{\infty} \pi_j Y_{t-j} ~~~~~,~~~~ t \in \mathbb{Z}
$$

Avec $\eta_j$ est un bruit blanc de moyenne nulle et de variance $\sigma^2$ et $ \sum_{j=1}^{\infty} |\pi_j| < \infty$
```

#### 4. Processus stationnaire


La stationnairité est la propriété d'une ST à garder ses caractéristiques inchangées au passage du temps. Elle implique l'absence de tendance dans les données ainsi qu'une moyenne et variance constantes pour la ST. On distingue deux types de stationnarité :



##### 4.1. Stationnairité au sens stricte


```{admonition} Définition
<i>Un processus $\lbrace Y_t, {t \in T}\rbrace$, est stationnaire au sens stricte si : </i> 

$$
{(Y_{t_{1}}, Y_{t_{2}}, \ldots, Y_{t_{k}})}^{t} \stackrel{\text{d}}{=} {(Y_{t_{1}+\tau}, Y_{t_{2}+ \tau}, \ldots, Y_{t_{k}+ \tau})}^{t}
$$

$$
\mathbb{P}(Y_{t_{1}} \leq y_{1}, \ldots ,Y_{t_{k}} \leq y_{k} ) =             \mathbb{P}(Y_{t_{1}+\tau} \leq y_{1}, \ldots ,Y_{t_{k}+\tau} \leq y_{k} ) 
$$

-  $\tau \in \mathbb{Z}$ ,  $(t_1, \ldots, t_k)$ set of time indices, k $\in \mathbb{N}^{*}$,  $(t_1, \ldots, t_k) \in$ T ,  $(t_1+\tau, \ldots, t_k+\tau) \in$ T et $\stackrel{\text{d}}{=}$ indicates equality in distribution.
```

##### 4.2. Stationnairité au au second ordre

```{admonition} Stationnairité au au second ordre

<i>Le processus Y = $\lbrace Y_t , {t \in \mathbb{Z}\rbrace}$, est stationnaire au second ordre ou  au sens faible (wide-sense stationary) si :</i>

- $\mathbb{E}(Y_t) = cst ~~,~~ \forall t \in \mathbb{Z}$ indépendant de t

-  $E(Y^2_t) < \infty ~~,~~ \forall t \in \mathbb{Z}$

-  $\gamma_Y (k) = Cov(Y_t, Y_{t-k})  ~~,~~ \forall t \in \mathbf{Z}, \forall k \in \mathbb{Z}$ est indépendant de t.

```

```{admonition} Remarque
:class: tip

<i>Un processus ${Y_t}$ est faiblement stationnaire si ses moments ne dépend pas du temps.</i>
```

On pratique, la stationnairité au second ordre est la plus utilisée dans l'analyse des ST et elle est souvent appelée stationnairité en covariance.


##### 4.3. White Noise


```{admonition} Définition
<i>Le processus stochastique $\lbrace \eta_t \rbrace_{t \in \mathbb{Z}}$, est un bruit blanc (white noise)  si : </i>

- $\mathbb{E}(\eta_t) = 0 ~~,~~ \forall t \in \mathbb{Z}$

-  $\mathbb{E}(\eta^2_t) = \sigma^2 ~~,~~ \forall t \in \mathbb{Z}$

-  $Cov(\eta_t, \eta_{t-k}) = 0 ~~,~~ \forall t \in \mathbb{Z}, \forall k \in \mathbb{Z}^{*}$

<i>On note $(\eta_t) \sim bb(0, \sigma^2 )$</i>
```


```{admonition} Remarque
:class: tip
Le processus stochastique $\lbrace \eta_t \rbrace_{t \in \mathbb{Z}}$, est un bruit blanc gaussien si $\eta_t$ $\sim$ i.i.d $N(0, \sigma^2)$
```


```{admonition} Exemple 1
:class: warning

On considère le modèle suivant :

$$
    Y_t = \eta_t + 2\eta_{t-1}
$$

Avec $\eta_t \stackrel{i.i.d}{\sim} ( 0, \sigma^2)$ et $t \in \mathbb{Z}$.

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
    0 & \mbox{Otherwise }
    \end{array}
\right.
$$

Ainsi, $\lbrace Y_t \rbrace_{t \in \mathbb{Z}}$ est stationaraire.

```


```{admonition} Exemple 2
:class: warning

On considère le modèle suivant :

$$
 y_t = \alpha_0 + \alpha_1 \eta_t + \alpha_2 \eta_{t-1} ~~,~~ t \in \mathbb{Z}
$$

$$
(\alpha_0, \alpha_1, \alpha_2) \in \mathbf{R}^3~~ ,~~ a_t \stackrel{i.i.d}{\sim} ( 0, \sigma^2)
$$

$$
    \mathbb{E}(y_t) &=  \mathbb{E}( \alpha_0 + \alpha_1 \eta_t + \alpha_2 \eta_{t-1}) &~~(t ~ \in ~\mathbb{Z})\\
    & = \alpha_0  + \alpha_1 \mathbb{E}( \eta_t)+ \alpha_2 \mathbb{E}(\eta_{t-1}) &~~(t ~\in ~ \mathbb{Z})\\
    & = \alpha_0 &~~(t ~\in ~\mathbb{Z})
$$

$$
    Var(y_t) &= Var(\alpha_0 + \alpha_1 \eta_t + \alpha_2 \eta_{t-1}) &~~(t ~ \in ~\mathbb{Z})\\
     &= Var(\alpha_1 \eta_t + \alpha_2 \eta_{t-1}) &~~(t ~ \in ~\mathbb{Z})\\
    & =   \alpha_1^2  Var( \eta_t)+ \alpha_2^2 Var(\eta_{t-1})+\alpha_1 \alpha_2 Cov(\eta_t,\eta_{t-1}) &~~(t ~ \in ~\mathbb{Z})\\
    & = (\alpha_1^2 + \alpha_2^2 + \alpha_1 \alpha_1)\sigma^2 &~~(t ~ \in ~\mathbb{Z})
$$

$$
\gamma_Y(k) &= Cov(y_t, y_{t-k}) \\
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
    0 & \mbox{Otherwise }
    \end{array}
\right.
$$

Ainsi, $\lbrace Y_t \rbrace_{t \in \mathbb{Z}}$ est un processus stationaraire

```

```{admonition} Exemple 3
:class: warning

Supposons que :

$$
y_t = y_{t-1} + \eta_t ~~ ,~~ \eta_t \stackrel{i.i.d}{\sim} ( 0, \sigma^2)
$$

$$
    y_t = &y_{t-1} + \eta_t ~~ ,~~ \eta_t \stackrel{i.i.d}{\sim} ( 0, \sigma^2) \\
    =& y_{t-2} + \eta_{t-1} + \eta_t ~~ ,~~ \eta_t \stackrel{i.i.d}{\sim} ( 0, \sigma^2) \\
     = & y_{t-3} + \eta_{t-2} + \eta_{t-1} + \eta_t ~~ ,~~ \eta_t \stackrel{i.i.d}{\sim} ( 0, \sigma^2) \\
    &  \vdots \\
    = & y_0 + \sum_{j=0}^{t-1} \eta_{t-j}  ~~ ,~~ \eta_t \stackrel{i.i.d}{\sim} ( 0, \sigma^2) \\
$$

Ainsi:

$$
    \mathbb{E}(y_t) &=  \mathbb{E}( y_0 + \sum_{j=0}^{t-1} \eta_{t-j} ) &~~(t ~ \in ~\mathbb{Z})\\
    & = y_0 = cst &~~(t ~\in ~\mathbb{Z})
$$

Aussi :

$$
    Var(y_t) &= Var(y_0 + \sum_{j=0}^{t-1} \eta_{t-j}) &~~(t ~ \in ~\mathbb{Z})\\
     &= Var( \sum_{j=0}^{t-1} \eta_{t-j}) &~~(t ~ \in ~\mathbb{Z})\\
     &= \sum_{j=0}^{t-1} Var(\eta_{t-j}) &~~(t ~ \in ~\mathbb{Z})\\
    & = t\sigma^2 &~~(t ~ \in ~\mathbb{Z})
$$

$$
\gamma_Y(k) &= Cov(y_t, y_{t-k}) \\
& = Cov(y_0 + \sum_{j=0}^{t-1} \eta_{t-j},  y_0 + \sum_{j=0}^{t-k-1} \eta_{t-j})\\
& = Cov(\sum_{j=0}^{t-1} \eta_{t-j},  \sum_{j=0}^{t-k-1} \eta_{t-j})\\
& = \sigma^2  \underset{(t,k)\in \mathbb{Z}^2}{\mathrm{Min(t, t-k)}}
$$

Ainsi, le processus stochastique   $ \lbrace y_t , {t \in \mathbb{Z}}\rbrace $,  n'est pas stationnaire.

```

```{admonition} corollaire 
:class : tip

$\lbrace \eta_t \rbrace_{t \in \mathbb{Z}} \sim bb( 0, \sigma^2) \Rightarrow \lbrace \eta_t \rbrace_{t \in \mathbb{Z}}$  un processus faiblement stationnaire

```


```{admonition} Transformation des ST

- la transformation logarithmique : Cette technique est utilisée lorsque les données présentent une croissance exponentielle, pour obtenir une ST ayant une croissance linéaire.

- la différentiation :  est la technique la plus utilisée pour stationnariser les variables : différence première $\Delta X_t$, différence seconde $\Delta^2 X_t$.

- la différentiation logarithmique : différence sur les transformations logarithmiques.

```

```{admonition} Remarque importante
:class : tip

- une ST qui devient stationnaire après différentiation est dit : stationnaire en différence.

- une ST qui devient stationnaire après d différences est dit : intégrée d'ordre d.

```

#### 5. Les modèles des séries temporelles


##### 5.1. Le processus moyenne mobile

```{admonition}  Définition
<i>On dit que la série chronologique $\lbrace Y_t \rbrace_{t \in \mathbb{Z}}$ est un processus moyenne mobile q si elle est définie, pour tout $t \in \mathbb{Z}$, par:</i>


$$
Y_t = \mu + \sum_{j=1}^{q} \theta_{j} \eta_{t-j}  + \eta_{t}
$$

Avec $\mu \in \mathbb{R}$, $\theta  = (\theta_1, \theta_2, \ldots, \theta_q)\in \mathbb{R}^q$ et  $\eta_{t}  \stackrel{i.i.d}{\sim} (0, \sigma^2)$.

On note $Y_t$ $\sim$ MA(q)
```


```{admonition} Remarque
Par définition, le processus stochastique moyenne mobile MA(q) est toujours causal.
```

```{admonition} Proposition
:class: tip

Soit $Y_t$ $\sim$ MA(1) alors :

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
Soit $Y_t$ $\sim$ MA(1) alors :

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
    \rho_Y(k) &= \dfrac{\gamma_Y(k)}{\gamma_Y(0)} ~~~~~~~~~~~~~~,~~ \gamma_Y(0) = Var(Y_t) \\
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



```{admonition}  Proposition
Si $Y_t$ $\sim$ MA(2) alors :

$$
\mathbb{E}(Y_t)=\mu~~,~~ Var(y_t) = \sigma^2 (1+\sum_{j=1}^{q} \theta_{j}^2)
$$

$$
    \gamma_Y(k) = \sigma^2 (\theta_k + \sum_{j=1}^{q-k} \theta_{j} \theta_{k+j})\mathbb{1}_{k\in [1,q]}
$$
```



```{admonition} Théorème
Soit $Y_t$ $\sim$ MA(q) alors :

$$
\mathbb{E}(Y_t)=\mu~~,~~ Var(y_t) = \sigma^2 (1+\sum_{j=1}^{q} \theta_{j}^2)
$$

$$
    \gamma_Y(k) = \sigma^2 (\theta_k + \sum_{j=1}^{q-k} \theta_{j} \theta_{k+j})\mathbb{1}_{k\in [1,q]}
$$
```

```{admonition} Théorème
Si $\lbrace Y_t \rbrace_{t \in \mathbb{Z}}$ MA(q) alors $\lbrace Y_t \rbrace_{t \in \mathbb{Z}}$ est nécessairement stationnaire.
```

```{admonition} Démonstration
Soit t $\in \mathbb{Z}$ and $\theta_j \in \mathbb{R}$. Supposons que $Y_t$ $\sim$ MA(q) tels que :

$$
Y_t = \mu + \sum_{j=1}^{q} \theta_{j} \eta_{t-j} + \eta_{t} ~~,~~\eta_{t}  \stackrel{i.i.d}{\sim} (0, \sigma^2)
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

On note $(Y_t)$ $\sim$ AR(p).

```

```{admonition} Remarque

Par définition, le processus autorégressif AR(p) est toujours inversible.

```

```{admonition} Théorème
Soit $Y_t$ $\sim$ AR(p).

Le processus $(Y_t)$ stationnaire et causal si si les racines du polynôme $A(z) = 1 − \phi_1z −· · ·- \phi_pz^p$ sont de module strictement supérieur à 1. 


```
```{admonition} Proposition
:class: important


$$
    Y_t \sim AR(1) \Rightarrow 
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

```{admonition} Exemple
:class: warning

We suppose that the daily return of time series at time t can be expressed as :

$$
    r_t = 0.5 - 0.2r_{t-1} + 0.48r_{t-2} +\zeta_t  ~~,~~\zeta_{t}  \stackrel{i.i.d}{\sim} (0, \sigma^2)
$$

Let $\zeta_{t}  \stackrel{i.i.d}{\sim} (0, \sigma^2)$ and $t \in \mathbb{Z}$

$$
     r_t = 0.5 - 0.2r_{t-1} + 0.48r_{t-2} +\zeta_t  &\Rightarrow       r_t + 0.2r_{t-1} - 0.48r_{t-2} = 0.5 +\zeta_t  \\
      &\Rightarrow       r_t + 0.2Br_{t} - 0.48B^2r_{t} = 0.5 +\zeta_t  \\
            &\Rightarrow       (1 + 0.2B - 0.48B^2)r_t = 0.5 +\zeta_t \\
                        &\Rightarrow       A(B)r_t = 0.5 +\zeta_t 
$$

Where $A(z) = (1 + 0.2z - 0.48z^2)$ indicates the autoregressive polynomial. \\

Let's findings the A's roots \footnote{It should be recall that the roots for quadratic polynomial $ax^2+bx+c=0$ are given by the following expression $\dfrac{-b \pm \sqrt{b^2-4ac}}{2a}$ , if a $\neq$ 0} by solving the equation A(z)=0. \\

$A(z) = 0 \Rightarrow z_1 = -\dfrac{5}{4} \vee z_2 =\dfrac{5}{3} $\\

Therefore, the return $\lbrace r_t \rbrace_{t \in \mathbb{Z}}$ is a causal and a strictly stationary process since all A(z) roots are outside the unit circle (i.e. $|z_j|>1 ~,~ j \in \lbrace  1,2\rbrace )$.\\

Graphically, the fitted time series can be represented as follows

```

```{admonition} Exemple
:class: warning

Let us consider the following stochastic process :

$$
    \pi_t = 0.5 + 1.2\pi_{t-1} + 1.2\pi_{t-2} + \eta_t ~~,~~ t \in \mathbb{Z}
$$

Where $\eta_t$ is the usual white noise process.

$$
        \pi_t = 0.5 + 1.2\pi_{t-1} + 1.2\pi_{t-2} + \eta_t &\Rightarrow         \pi_t -1.2 \pi_{t-1} - 1.2\pi_{t-2}= 0.5  + \eta_t \\
        &\Rightarrow         (1-1.2B - 1.2B^2)\pi_t = 0.5  + \eta_t \\
                &\Rightarrow         A(B)\pi_t = 0.5  + \eta_t
$$

Thus, the characteristic equation is given by $A(z) = 1-1.2z - 1.2z^2= 0$.

$$
    \Delta_A > 0 &\Rightarrow z_1 = -\dfrac{3+\sqrt{39}}{4} \approx-1.54 \vee z_2= \dfrac{-3+\sqrt{39}}{4}\approx0.54 \\
    &\Rightarrow \exists ~ (i \in \lbrace 1, 2 \rbrace) ~;~ |z_i| <  1 \\
    &\Rightarrow \lbrace \pi_t , t \in \mathbb{Z}\rbrace ~~ explosive 
$$
```
Graphically, figure \ref{fig3l} shows the inverse roots of our time series within the unit circle. Indeed, at least one of its real is roots $z_1\approx -1.54$ , $z_2\approx 0.54$ is outside the unit circle which means the process is explosive (non stationary). 

```{admonition} Théorème

$$
    Y_t \sim AR(2) \Rightarrow 
    \begin{cases}
     \mathbb{E}(Y_t) &= \dfrac{\mu}{1-\Phi_1 - \Phi_2} \\
     Var(Y_t) & =\dfrac{\sigma^2}{1-\Phi_1 \rho_Y(1)- \Phi_2 \rho_Y(2)}\\
     \gamma_Y(k) & =\Phi_1 \rho_Y(k-1)+ \Phi_2 \rho_Y(k-2) ~~,~~ k \in \mathbb{N}^{*}
    \end{cases}
$$
```


```{admonition} Théorème
$$
    Y_t \sim AR(p) \Rightarrow 
    \begin{cases}
     \mathbb{E}(Y_t) = \dfrac{\mu}{1-\Phi_1 - \Phi_2 -\ldots - \Phi_p} & \\
     Var(Y_t) = & \\
     \gamma_Y(k) = 
    \end{cases}
$$
```




##### 5.3. Autoregressive moving average model

```{admonition} Définition
An Auto Regressive Moving Average (ARMA) model of p and q orders is a combination of the Auto-Regressive (AR) model and Moving Average (MA) one ~\cite{b2}.
```
```{admonition} Définition
Mathematically, an ARMA(p,q) process takes the following form: 

$$
y_t = \mu + \sum_{j=1}^{p} \Phi_{j} y_{t-j} + \sum_{j=1}^{q} \theta_j \eta_{t-j} + \eta_{t}
$$

$$
y_t -  \underbrace{\Phi_1y_{t-1} - \ldots - \Phi_py_{t-p}}_{AR(p)~ part} = \underbrace{\mu + \theta_1\eta_{t-1} + \ldots + \theta_{q}\eta_{t-q} + \eta_{t}}_{MA(q) ~ part}
$$

Where :

- $\eta_t$ refers to the white noise series such as $\eta_t$ $\sim$ WN (0 , $\sigma^2$).

- $\Phi_1, \Phi_2, \ldots \Phi_p $ represent the coefficients of the moving average model.

-  $\theta_1, \theta_2, \ldots \theta_q $ represent the coefficients of the autoregressive model.

-  $\mu$ $\in$ $\mathbb{R}$ represents the constant term.

- t indexes time i.e (t $\in$ $\mathbb{Z}^{*+}$)

```



Therefore, implying a reduced form by using the backward shift operator (B), we can write :

$$
\Phi_p (B)y_t = \Theta_q(B)\eta_t
$$

Where

$$
      \begin{cases}
      B^{k}y_{t} =y_{t-k} ~ , ~~~ \forall ~~ k \in \mathbb{N} \\
\Phi(B) = 1- \Phi_1 B - \Phi_2 B^2 - \ldots - \Phi_p B^p \\
\Theta(B) = 1- \theta_1 B - \theta_2 B^2 - \ldots - \theta_q B^q
	\end{cases}
$$

The ARMA models assume the stationary of the time series ~\cite{b3}.

```{admonition} Exemples 

Here are some examples of ARMA models


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
It should be noticed that :

-  When q = 0 then ARMA(p,0) $\equiv	$ AR(p):
    
$y_t = \Phi_1y_{t-1} + \Phi_2y_{t-2} + \ldots + \Phi_py_{t-p}$

-  When p = 0 then ARMA(0,q) $\equiv	$ MA(q):
    
$y_t = \theta_1\eta_{t-1} + \theta_2\eta_{t-2} + \ldots + \theta_q\eta_{t-q} + \eta_t$
```

```{admonition} Exemple

Let $X_t$ be an ARMA(2,2) process such as $\Phi_1= 3$, $\Phi_2= 6$, $\theta_1=-\dfrac{14}{3}$ and $\theta_1=5$. Let's check the causality ?.\\
The process can be written as : 

$$
        X_t -3X_{t-1}-6X_{t-2} &= \eta_t -\dfrac{14}{3}\eta_{t-1} + 5\eta_{t-2} ~~ , ~~~ \eta_t \sim WN (0 , \sigma^2) \\
(1 -3B-6B^2)X_t &= (1 -\dfrac{14}{3}B + 5B^2)\eta_t ~~ , ~~~ \eta_t \sim WN (0 , \sigma^2)
\end{align*}
 $X_t$ can be re-exporessed in factored form as follows :
 \begin{align*}
(1 -2L)(1-3L)X_t &= (1 -3L)(1-\dfrac{14}{3})\eta_t ~~ , ~~~ \eta_t \sim WN (0 , \sigma^2) \\
(1 -2L)X_t &= (1-\dfrac{14}{3})\eta_t ~~ , ~~~ \eta_t \sim WN (0 , \sigma^2)
$$

Therefore, $X_t$ is a causal and stationary ARMA(2,2) (the roots of the associated characteristic polynomial are superior than one) with : 

$$
  X_t = 2y_{t-1} +\eta_t -\dfrac{14}{3}\eta_t ~ , ~ \eta_t \sim WN (0 , \sigma^2)  
$$

Since it was highly over parametrized and it is now carefully parametrized as an ARMA(1,1) process.
```

```{admonition} Remark
In order to identify the MA(q) and AR(p) process, it is very suitable to use the ACF and PACF respectively. 
```

##### 5.4. Autoregressive integrated moving average model

```{admonition} Définition
An ARIMA(p,d,q) takes the following form

$$
\nabla^dy_t = (1-B)^dy_{t} ~~~~ , \forall t \in \mathbb{Z}^{*+}
$$

Or 

$$
( 1- \Phi_1 B - \Phi_2 B^2 - \ldots - \Phi_p B^p ) \nabla^dy_t= (1- \theta_1 B - \theta_2 B^2 - \ldots - \theta_q B^q)\eta_t
$$

Where :

-  $\nabla$ refers  to the difference operator

- d refers to a positive integer ( d $\in$ $\mathbf{N}$)

- The process $y_t$ follows an ARMA(p,q). 

```


```{admonition} Remarque
Based on the definition above, it clearly seems that the ARIMA models are the extension of the ARMA ones.
```

```{admonition} Lemma
Let $\lbrace y_t \rbrace_{t \in \mathbb{Z}^{*+}}$ be a stochastic process. If $y_t$  follows an ARIMA(p,d,q) thus it can be expressed as :
```

$$
    \Phi_p (B)(1-B)^{d}y_t = \Theta_q(B)\eta_t ~~ , ~~~ \eta_t \sim WN (0 , \sigma^2)
$$


Hence, \\
$\nabla^dy_t = (1-B)^dy_{t}$ will be a stationary ARMA(p,q)


#### 6. Prévision des séries temporelles

###### 6.1. Naive forecast

###### 6.2. Simple average

###### 6.3. Algorithme de Box \& Jenkins


```{admonition} Algorithme de Box \& Jenkins

Cette méthodologie suggère une procédure à quatre étapes :

- Identification du processus : Déterminer à partir de l'observation des fonctions d'autocorrélation simple et partielle dans la famille des modèles de types ARMA (p, q) le modèle adéquat.

- Estimation des coefficients des modèles séléctionnés

- Validation du modèle (Test de diagnostique des résidus) : les résidus doivent être autocorrélés et ne présentent pas d'hétéroscédasticité.

- Prévision à l'horizon h

```



#### Modelling time process

The main challenge in modeling a stochastic process is to find the appropriate  generated process based on historical data information. To do this, we can imply the ARMA procedure.

```{admonition} Proposition

Let $y_t \sim ARIMA(p,d,q)$.

ARIMA orders p  and q are determined by the mean of statistical and graphical model selection criteria, such as the Bayesian information criterion (BIC), Schwarz Information Criterion (SIC), and Hannan-Quinn criterion (HQC) or either the Akaike Information Criterion (AIC).
```


```{admonition} Box-Jenkins algorithm

Step 1:  Plot the time series to observe any unusual behavior  and  to find out if it is stationary or not.

Step 2 : Difference target time series if non-stationary

Step 3 : Model identification 

To choose the model specification ARIMA(p, d, q), we start by examining the stationarity and seasonality of our target series by using algebraic or graphical procedures. Then, we can determine the orders p and q by using the ACF and PACF functions.

Step 4 : Parameter estimation 

To determine parameter estimation, we can imply the maximum likelihood or the least squares approach

Step 5 :Diagnostic checking

To check whether the model specified is adequate, we can use diagnostic residuals checking 
Evaluate the fitted model

Step 6 : Selected Model’s based on minimum BIC and AIC values, and pick up the best one.
Selected Models’ use in terms of explaining and forecasting.

Step 7 : Draw ACF plot of residuals. Is it look like a white noise term? If yes, forecast. If not, go to step 2
```

