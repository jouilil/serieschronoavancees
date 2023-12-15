### Chapitre 2 : Les processus aléatoires non stationnaires

#### Prof. Jouilil Youness

###### 1. Projet pratique sur Python \& R


```{admonition} Projets pratiques sur Python \& R

- Les tests usuels de stationnarité : Etude comparative

- Causalité : Granger vs Sims

- Cointégration entre deux séries \& l’algorithme de Engle et Granger

- Cointégration \& modèle à correction d’erreur

- Var vs Svar : Etude de cas

- Prévisions d’inflation au Maroc par les modèles vectoriels autorégressifs : Etude de cas avec R

- Prévisions d’inflation au Maroc par les modèles vectoriels autorégressifs : Etude de cas avec Python

- Impact de l'inflation sur la croissance économique : Etude de cas avec R

- Impact de l'inflation sur la croissance économique : Etude de cas avec Python

- Impact de la dette publique sur la croissance économique du Sénégal (Etude de cas avec R)

- Impact de la dette publique sur la croissance économique du Sénégal (Etude de cas avec Python)

- Endettement public et taux d'intérêt. Une étude empirique avec R

- Endettement public et taux d'intérêt. Une étude empirique avec Python

- Analyse de la relation entre l’ouverture commerciale et la croissance économique: Etude de cas avec R

- Analyse de la relation entre l’ouverture commerciale et la croissance économique: Etude de cas avec Python

- Les déterminants macroéconomiques de l'épargne  : une étude économétrique à l'aide de R

- Les déterminants macroéconomiques de l'épargne  : une étude économétrique à l'aide de Python

- Modélisation économétrique des déterminants des IDE au Maroc : Etude empirique avec R

- Modélisation économétrique des déterminants des IDE au Maroc : Etude empirique avec Python


```


###### 2. Les processus TS

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

###### 3. Les processus DS
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

##### ARCH process
###### ARCH (1) process

```{admonition} Corollary
The process $\eta_t$ is an ARCH(1) process if it is stationary and if it satisfies, for all t and some strictly positive-valued process $\sigma_t$, the equations :

$$
        \eta_t &= \sigma_t z_t \\
    \sigma^{2}_t & = \alpha_0 + \alpha_j a^2_{t-1} \\
    z_t    & \stackrel{i.i.d}{\sim} (\mu = 0, \sigma^2 = 1)
$$

As a consequence of equation (\ref{arch(1)}), we can say that the conditional variance $\sigma^{2}_t$ at time t in ARCH(1) process depends and influences only by the errors in the previous time periods, especially at time t-1.
```


```{admonition} Proposition
If $\eta_t$ $\sim$ ARCH(1) process then :

$$
\mathbb{E}(\eta_t) &= 0 \\
\mathbb{E}(\eta_t/I_{t-1}) &= 0 \\
Var(\eta_t/I_{t-1}) &= \alpha_0 + \alpha_j a^2_{t-j} \\
Cov(\eta_t, \eta_{t+k}) &= \gamma(k) = 0 \\
Cov(\eta_t, \eta_{t+k}/I_{t-1}) &= 0
$$
```

```{admonition} theorem
if $\eta_t$ is an ARCH(1) then $\eta_t \sim AR(1)$ such as :

$$
    \eta_t^2 =  \alpha_0 + \alpha_1 \eta_{t-1}^2 + \mu_t ~~ ,~~ \mu_t = \eta_t^2- \sigma_t^2
$$
```


##### ARCH (p) process
```{admonition} definition
The process $\eta_t$ is a ARCH(p) process if it is stationary and if it satisfies, for all t and some strictly positive-valued process $\sigma_t$, the equations :

$$
\left\{
    \begin{array}{ll}
    y_t & = f(t, y_{t-1}, y_{t-2}, \ldots) + \eta_t \\
        \eta_t & = \sigma_t z_t  \\
        \sigma^{2}_t& = \alpha_0 + \sum_{j=0}^{q}\alpha_j a^2_{t-j}  \\
        z_t & \sim N(0,1)
        \label{garch_model}
      \end{array}
\right.
$$

Where :

- $\alpha_0 \in  \mathbf{R}^{+*} $

- $\alpha_i \in \mathbf{R}^{+}; i \in \lbrace 1,2,\ldots, q \rbrace$

```

```{admonition} theorem

If $\eta_t$ $\sim$ ARCH(q) process then :

$$
\mathbb{E}(\eta_t) &= 0 \\
\mathbb{E}(\eta_t/I_{t-1}) &= 0 \\
Var(\eta_t/I_{t-1}) &= \alpha_0 + \sum_{j=0}^{q}\alpha_j a^2_{t-j} \\
Cov(\eta_t, \eta_{t+k}) &= \gamma(k) = 0 \\
Cov(\eta_t, \eta_{t+k}/I_{t-1}) &= 0
$$
```

```{admonition} theorem
if $\eta_t$ is an ARCH(p) then $\eta_t \sim AR(p)$ such as :

$$
    \eta_t^2 =  \alpha_0 + \sum_{j=1}^{p} \alpha_j \eta_{t-j}^2 + \mu_t
$$
```




# GARCH process
GARCH process or even Generalized ARCH process is commonly implied to .. \cite{b3} \footnote{Bollerslev, T. (1986) Generalized autoregressive conditional heteroskedasticity. Journal of
Econometrics, 31, 307–327.}

## GARCH(1,1) model
## GARCH(p,q) model
\begin{definition}
The process $\eta_t$ is a GARCH(p,q) process if it is stationary and if it satisfies, for all t and some strictly positive-valued process $\sigma_t$, the equations :
\begin{align}
\left\{
    \begin{array}{ll}
    y_t & = f(t, y_{t-1}, y_{t-2}, \ldots) + \eta_t \\
        \eta_t & = \sigma_t z_t  \\
        \sigma^{2}_t& = \alpha_0 + \sum_{j=0}^{q}\alpha_j a^2_{t-j} + \sum_{j=0}^{p}\beta_j \sigma^{2}_{t-j} \\
        z_t & \sim N(0,1)
        \label{garch_model}
      \end{array}
\right.
\end{align}
    
Where :
\begin{itemize}
    \item $\alpha_0 \in  \mathbf{R}^{+*} $
    \item $\alpha_i ; i \in \lbrace 1,2,\ldots ,q \rbrace$
    \item $\beta_j ; j \in \lbrace 1,2,\ldots , p \rbrace$
    \item function $y_t$ refers to a deterministic information process.
\end{itemize}
\end{definition}
\begin{Remark}
According to the equation (\ref{garch_model}), when can remark that q is null (q=0), the GARCH process reduces to be an ARCH process.
\end{Remark}

\begin{Example} Here are some examples of GARCH models :

\begin{itemize}
    \item GARCH(p,0)= ARCH(p)
    
\begin{align}
\left\{
    \begin{array}{ll}
        \eta_t & = \sigma_t z_t  \\
        \sigma^{2}_t& = \alpha_0 + \sum_{j=0}^{q}\alpha_j a^2_{t-j}  \\
    z_t    & \stackrel{i.i.d}{\sim} (\mu = 0, \sigma^2 = 1)
      \end{array}
\right.
\end{align}

    \item GARCH(1,0)= ARCH(1)
    
\begin{align}
\left\{
    \begin{array}{ll}
        \eta_t &= \sigma_t z_t \\
    \sigma^{2}_t & = \alpha_0 + \alpha_1 \eta^2_{t-1} \\
    z_t    & \stackrel{i.i.d}{\sim} (\mu = 0, \sigma^2 = 1)
          \end{array}
          \right.
\end{align}

    \item GARCH(1,1)

\begin{align}
\left\{
    \begin{array}{ll}
        \eta_t &= \sigma_t z_t \\
    \sigma^{2}_t & = \alpha_0 + \alpha_1 \eta^2_{t-1} + + \beta_1 \sigma^2_{t-1} \\
    z_t    & \stackrel{i.i.d}{\sim} (\mu = 0, \sigma^2 = 1)
          \end{array}
          \right.
\end{align}

    \item GARCH(2,1)
    
\begin{align}
\left\{
    \begin{array}{ll}
        \eta_t &= \sigma_t z_t \\
    \sigma^{2}_t & = \alpha_0 + \alpha_1 \eta^2_{t-1} +  \alpha_2 \eta^2_{t-2} + \beta_1 \sigma^2_{t-1} \\
    z_t    & \stackrel{i.i.d}{\sim} (\mu = 0, \sigma^2 = 1)
          \end{array}
          \right.
\end{align}

    \item GARCH(1,3)
    
\begin{align}
\left\{
    \begin{array}{ll}
        \eta_t &= \sigma_t z_t \\
    \sigma^{2}_t & = \alpha_0 + \alpha_1 \eta^2_{t-1}  + \beta_1 \sigma^2_{t-1} + \beta_2 \sigma^2_{t-2} + \beta_3 \sigma^2_{t-3}\\
    z_t    & \stackrel{i.i.d}{\sim} (\mu = 0, \sigma^2 = 1)
          \end{array}
          \right.
\end{align}

\end{itemize}
\end{Example}

\subsubsection*{Estimating GARCH Model}
As seen in equation (\ref{garch_model}), A GARCH model with orders (p, q) $\in$ $\mathbf{N}^{*}$ $\times$ $\mathbf{N}^{*}$ can be defined as follows :

\begin{align}
        \eta_t  &= \sigma_t z_t  \\
        \sigma^{2}_t &= \alpha_0 + \sum_{j=0}^{q}\alpha_j \eta^2_{t-j} + \sum_{j=0}^{p}\beta_j \sigma^{2}_{t-j} ~~~~;~~~~ t \in \mathbf{Z}
        \label{eq21}
\end{align}
Let : $\theta$ = $(\alpha_0, \alpha_1, \ldots, \alpha_q, \beta_0,\beta_1, \ldots, \beta_q)^{'}$ vector of unknown parameters and the innovations $\lbrace z_t , t\in \mathbb{Z}\rbrace $  are unobservable i.i.d  with mean zero and unit variance ($z_t\sim_{i.i.d} (0,1))$.
\begin{Remark}
Note that the equation (\ref{eq21}) could be rewritten using the lag operator (B).\\
Therefore,
\begin{align}
        \sigma^{2}_t &= \alpha_0 +\alpha(B) \eta^2_{t} + \beta(B) \sigma^{2}_{t} ~~~~;~~~~ t \in \mathbf{Z}
\end{align}
Where : 
\begin{align*}
\alpha(B) = \alpha_1B + \alpha_2 B^2 +\ldots + \alpha_q B^q \\
\beta(B)= \beta_1B + \beta_2 B^2 + \ldots + \beta_p B^p
\end{align*}
\end{Remark}


# Hybridization of ARIMA-GARCH

Hybrid ARIMA-GARCH is a statistical model that combines the ARIMA model and the GARCH model  for the analysis and forecasting of univariate time-series data.

The ARIMA model is used to deal with time-series patterns in the mean of the data, while the GARCH model is used to deal with volatility patterns in the data. In other words, ARIMA is employed to model the mean of the series, while GARCH is used to model the variance.

The ARIMA-GARCH model is particularly suitable for financial time series analysis, as it is often seen that the volatility of financial data is not constant over time. The GARCH element of the model contributes to capturing this volatility, which is essential for risk management and forecasting.

The hybrid ARIMA-GARCH model is conventionally estimated using maximum likelihood estimation. The model parameters are estimated using historical data and the model is then used to produce forecasts for future periods. The accuracy of the model can be judged by comparing the predicted values with the observed values for the test period.

As a result, the combination of the ARIMA and GARCH model is a very efficient tool for predicting and forecasting financial time series data, as it considers both the mean and the volatility of the data, which are relevant for risk management and forecasting.

Procedure of Hybridization

\begin{figure}[H]
    \centering
        \caption{Procedure of Hybridization of ARIMA and GARCH models}
    \includegraphics[scale=0.3]{diagram.png}
    \label{fig:my_label}
\end{figure}











###### 2. Tests de racine unitaire (Unit Root Test)

Il existe trois méthodes principales pour détecter la non-stationarité :

1. Le graphique de la série

2. Son corrélogramme.

3. Des tests statistiques formels pour détecter les racines unitaires.

Les tests de racine unitaire (Unit Root Test) permettent non seulement de détecter l’existence d’une non-stationnarité 
mais surtout de déterminer de quelle non-stationnarité il s’agit (processus TS ou DS) et donc la bonne méthode pour
stationnariser la série.




```
```
