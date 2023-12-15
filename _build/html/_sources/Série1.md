### Série 1 : Espace vectoriel

#### Prof. Jouilil Youness

###### 1. Sous-espace vectoriel

```{admonition} Exercice 1
**Montrer que les sous-ensembles suivants des sous-espaces vectoriels**

- $A_1$ =$ \left\{ (x,y,z) \in \mathbb{R}^3 / x+y+z = 0 \right\}$

- $A_2$ = $ \left\{ (x,y,z) \in \mathbb{R}^3 / x-y = 0 \right\}$

- $A_3$ = $ \left\{ (x,y,z) \in \mathbb{R}^3 / x =3z \right\}$

```


<center><font color='red'>Vous avez 5 min !</font></center>


```{admonition} <font color='blue'>Réponse de l'exercice 1</font>
:class: attention, dropdown

- $A_1$ =$ \left\{ (x,y,z) \in \mathbb{R}^3 / x+y+z = 0 \right\}$

$(0,0,0) ~\in$ $A_1 ~~ \Rightarrow A_1 \neq  \emptyset$

Soit :  $X=(x,y,z) ~ et~ X'= (x',y',z') ~ \in ~A_1$

On a :

$X+ X' = (x,y,z) + (x',y',z') = (x+x',y+y',z+z')$

tel que : $x+y+z = 0 ~et~ x'+y'+z' = 0 \Rightarrow x+x'+y'+ y+ z +z' = 0 $

$X=(x,y,z) ~ et~ X'= (x',y',z') ~ \in ~A_1 \Rightarrow X+ X'~ \in ~A_1$

$\lambda X = (\lambda x, \lambda y,\lambda z)$

tel que : 
$\lambda x+ \lambda y+ \lambda z = 0 \Rightarrow \lambda (x+y+z) = 0$

Ainsi, $\lambda X \in ~A_1$
 
- $A_2$ = $ \left\{ (x,y,z) \in \mathbb{R}^3 / x-y = 0 \right\}$


$(0,0,0) ~\in$ $A_2 ~~ \Rightarrow A_2 \neq  \emptyset$

Soit :  $X=(x,y,z) ~ et~ X'= (x',y',z') ~ \in ~A_2$

On a :

$X+ X' = (x,y,z) + (x',y',z') = (x+x',y+y',z+z')$

tel que : $x-y = 0 ~et~ x'-y' = 0 \Rightarrow x+x'-(y'+y) = 0 $

$X=(x,y,z) ~ et~ X'= (x',y',z') ~ \in ~A_2 \Rightarrow X+ X'~ \in ~A_2$

$\lambda X = (\lambda x, \lambda y,\lambda z)$

tel que : 
$\lambda x- \lambda y = 0 \Rightarrow \lambda (x-y) = 0$

Ainsi, $\lambda X \in ~A_2$

- $A_3$ = $ \left\{ (x,y,z) \in \mathbb{R}^3 / x =3z \right\}$


$(0,0,0) ~\in$ $A_3 ~~ \Rightarrow A_3 \neq  \emptyset$

Soit :  $X=(x,y,z) ~ et~ X'= (x',y',z') ~ \in ~A_3$

On a :

$X+ X' = (x,y,z) + (x',y',z') = (x+x',y+y',z+z')$

tel que : $x= =3z ~et~ x'=3z' \Rightarrow x+x'==3(z+z') $

$X=(x,y,z) ~ et~ X'= (x',y',z') ~ \in ~A_3 \Rightarrow X+ X'~ \in ~A_3$

$\lambda X = (\lambda x, \lambda y,\lambda z)$

tel que : 
$\lambda x =\lambda 3z $

Ainsi, $\lambda X \in ~A_3$


```

```{admonition} Exercice 2
**Les sous-ensembles suivants sont-ils des sous-espaces vectoriels ?**

- $A_1$ =$ \left\{ (x,y,z) \in \mathbb{R}^3 / x+y-3z = 2 \right\}$

- $A_2$ =  $\left\{ (x,y,z) \in \mathbb{R}^3 / x+y > z \right\}$

- $A_3$ = $ \left\{ (x,y,z) \in \mathbb{R}^3 / xyz = 0 \right\}$

- $A_4$ = $ \left\{ (x,y,z, t) \in \mathbb{R}^4 / x = 2y= -z=3t \right\}$

- $A_5$ = $ \left\{ (x,y,z) \in \mathbb{R}^3 / y(x^2+z) = 0 \right\}$

```

<center><font color='red'>Vous avez 5 min !</font></center>


```{admonition} <font color='blue'>Réponse de l'exercice 2</font>
:class: attention, dropdown
Pour  
- $A_1$ =$ \left\{ (x,y,z) \in \mathbb{R}^3 / x+y-3z = 2 \right\}$

Méthode 1 :

Soit :  $X=(0,2,0) ~ et~ X'= (2,0, 0) ~ \in ~A_1$
$X+ X' = (2,2,0)~ \notin ~A_1$

$A_1$ n'est pas un s.e.v de $\mathbb{R}^3$

Méthode 2 : 

$(0,0,0)~ \notin ~A_1$

Donc : $A_1$ n'est pas un s.e.v de $\mathbb{R}^3$

- $A_2$ =  $\left\{ (x,y,z) \in \mathbb{R}^3 / x+y > z \right\}$

$(0,0,0)~ \notin ~A_2$

Donc : $A_2$ n'est pas un s.e.v de $\mathbb{R}^3$

- $A_3$ = $ \left\{ (x,y,z) \in \mathbb{R}^3 / xyz = 0 \right\}$

Soit :  $X=(x,y,z) ~ et~ X'= (x',y',z') ~ \in ~A_3$

On a :

$X+ X' = (x,y,z) + (x',y',z') = (x+x',y+y',z+z')$

tel que : $xyz= 0 ~et~ x'y'z' = 0 \Rightarrow xyz(x'y'z') = 0 $

$X=(x,y,z) ~ et~ X'= (x',y',z') ~ \in ~A_3 \Rightarrow X+ X'~ \in ~A_3$

$\lambda X = (\lambda x, \lambda y,\lambda z)$

tel que : 
$\lambda xyz = 0 \Rightarrow \lambda (xyz) = 0$

Ainsi, $\lambda X \in ~A_3$

Donc : $A_3$ est un s.e.v de $\mathbb{R}^3$


- $A_4$ = $ \left\{ (x,y,z, t) \in \mathbb{R}^4 / x = 2y= -z=3t \right\}$

De même, on peut montrer que $A_4$ est un s.e.v de $\mathbb{R}^4$


- $A_5$ = $ \left\{ (x,y,z) \in \mathbb{R}^3 / y(x^2+z) = 0 \right\}$

$X= (1,0,2) \in ~A_5$ et $ X'=(3,1, -9) \in ~A_5$

$X + X'= (1,0,2)+(3,1, -9) = (4, 1, -7) \notin ~A_5$

Donc : $A_5$ n'est pas un s.e.v de $\mathbb{R}^3$


```

###### 2. Combinaison linéaire

```{admonition} Exercice 3
On considère les vecteurs de $\mathbb{R}^3$ suivants :
$
u_1=(1,0,1) ; u_2=(0,1,1) ; u_3=(1,1,0)
$

- **Est-ce que le vecteur $u = (2,3,0)$ est combinaison linéaire des vecteurs $u_1$, $u_2$ et $u_3$ ?**
```

```{admonition} <font color='blue'>Réponse de l'exercice 3</font>
:class: attention, dropdown
On a : 

$$
u_1=(1,0,1) ; u_2=(0,1,1) ; u_3=(1,1,0)
$$

- **Est-ce que le vecteur $E$$(2,3,0)$ est combinaison linéaire des vecteurs $u_1$, $u_2$ et $u_3$ ?**

Le vecteur $u=(2,3,0)$ est combinaison linéaire des vecteurs $u_1$, $u_2$ et $u_3$ si 

il existe $\alpha_1, \alpha_2, \alpha_3 \in \mathbb{R}$ tel que :

$$
u = \alpha_1E_1 + \alpha_2E_2 + \alpha_3E_3
$$

$$
    \begin{cases}
      2 =\alpha_1 *1 + \alpha_2* 0 + \alpha_3*1\\
      3 =\alpha_1* 0 + \alpha_2*1 + \alpha_3* 1 \\
      0 = \alpha_1* 1 + \alpha_2* 1 + \alpha_3* 0 
    \end{cases} 
    \Rightarrow
        \begin{cases}
      2 =\alpha_1 + \alpha_3\\
      3 =\alpha_2 + \alpha_3 \\
      0 = \alpha_1 + \alpha_2
    \end{cases} 
        \Rightarrow
        \begin{cases}
      \alpha_1 = -\dfrac{1}{2} \\
      \alpha_2 = \dfrac{1}{2} \\
      \alpha_3 = \dfrac{5}{2} 
      \end{cases}
$$

Donc :

$$
u = -\dfrac{1}{2}u_1 + \dfrac{1}{2}u_2 + \dfrac{5}{2}u_3
$$

```

```{admonition} Exercice 4
On considère les ensembles suivants

$ 
E_1 = \left\{  A = \begin{pmatrix}
a& d\\
b&c \\
\end{pmatrix} \in M(2) ~;~ 
a,b,c, d \in \mathbb{R} ~/~ ac = 1\right\}
$


$ 
E_2 = \left\{  A = \begin{pmatrix}
a& a & c\\
b& d & a\\
b& d & a
\end{pmatrix} \in M(3) ~;~
a,b,c, d \in \mathbb{R} ~/~ ab-c = 2\right\}
$

$ 
E_3 = \left\{  A \in M(2) ~;~
A' = -A \right\}
$

$ 
E_4 = \left\{  A \in M(3) ~;~
A' = A \right\}
$


tels que $M(2)$, $M(3)$ sont resp. les espaces vectoriels des matrices carrées d’ordre 2 et 3.

1. Parmi ces ensembles, quels sont ceux qui sont des sous-espaces vectoriels ?
2. Donner, _en justifiant vos réponses_, une famille génératrice pour chaque sous-espace vectoriel.

```

```{admonition} <font color='blue'>Réponse de l'exercice 4</font>
:class: attention, dropdown
On a : 


1. Parmi ces ensembles, quels sont ceux qui sont des sous-espaces vectoriels ?

$ 
E_1 = \left\{  A = \begin{pmatrix}
a& d\\
b&c \\
\end{pmatrix} \in M(2) ~;~ 
a,b,c, d \in \mathbb{R} ~/~ ac = 1\right\}
$


$E_1$ est-il un sous-espace vectoriel !?


$ 
E_2 = \left\{  A = \begin{pmatrix}
a& a & c\\
b& d & a\\
b& d & a
\end{pmatrix} \in M(3) ~;~
a,b,c, d \in \mathbb{R} ~/~ ab-c = 2\right\}
$

$E_2$ est-il un sous-espace vectoriel !?


$ 
E_3 = \left\{  A \in M(2) ~;~
A' = -A \right\}
$

$E_3$ est-il un sous-espace vectoriel !?

$ 
E_4 = \left\{  A \in M(3) ~;~
A' = A \right\}
$

$E_4$ est-il un sous-espace vectoriel !?


```



###### 4. Famille libre
```{admonition} Exercice 5
** Les familles de vecteurs suivantes sont-elles libres ou liées ? **

1. $e_1=(0,1,3)$, $e_2=(-1,1,0)$ et $e_3=(-2,0,5)$ dans $\mathbb{R}^3$.

2. $e_1=(0,1,1)$, $e_2=(1,1,0)$ et $e_3=(1,1,1)$ dans $\mathbb{R}^3$.

3. $e_1=(5,1,-1,0)$, $e_2(0,-1,3,7)$ et $e_3=(8,1,-1,7)$ dans $\mathbb{R}^4$.
```
```{admonition} <font color='blue'>Réponse de l'exercice 5</font>
:class: attention, dropdown

Les familles de vecteurs suivantes sont-elles libres ou liées ?

1. $e_1=(0,1,3)$, $e_2=(-1,1,0)$ et $e_3=(-2,0,5)$ dans $\mathbb{R}^3$.

$ S = \left\{  e_1, e_2, e_3 \right\} $ est libre dans $\mathbb{R}^3$ si 

$\exists! (\alpha_1, \alpha_2, \alpha_3) \in \mathbb{R}^3$ : $\alpha_1 e_1 + \alpha_2 e_2 + \alpha_3 e_3= (0,0,0) \Rightarrow \alpha_1= \alpha_2 = \alpha_3 = 0 $

```


```{admonition} Exercice 6
**Les familles de vecteurs $e_1$, $e_2$ et $e_3$ forment-elles des bases de  $\mathbb{R}^3$ dans chacun des cas suivants ?**

1. $e_1 =(0,1,0)$, $e_2 =(-1,1,1)$ et $e_3 =(1,0,5)$.

2. $e_1=(1,0,-1)$, $e_2=(-1,1,0)$ et $e_3=(1,0,2)$.

```
```{admonition} <font color='blue'>Réponse de l'exercice 6</font>
:class: attention, dropdown

Les familles de vecteurs suivantes sont-elles libres ?


1. <font color='red'>Pour $e_1 =(0,1,0)$, $e_2 =(-1,1,1)$ et $e_3 =(1,0,5)$</font>


Posons : $S_1 = \left\{  e_1, e_2, e_3 \right\} $

$S_1 = \left\{  e_1, e_2, e_3 \right\} $ forme une base de $\mathbb{R}^3$ si $S_1 = \left\{  e_1, e_2, e_3 \right\} $ est libre 

Ainsi, pour montrer que $S_1 = \left\{  e_1, e_2, e_3 \right\} $ est une base, il suffit de montrer que $S_1 = \left\{  e_1, e_2, e_3 \right\} $ est libre.

Soit alors $\alpha_1, \alpha_2,\alpha_3 \in \mathbb{R}$ :

$$
\alpha_1 e_1 + \alpha_2 e_2 + \alpha_3 e_3= (0,0,0) \Rightarrow 
    \begin{cases}
      \alpha_1*0 + \alpha_2* (-1) +\alpha_3*1= 0 \\
      \alpha_1*1 + \alpha_2*1 + \alpha_3*0= 0 \\
      \alpha_1*0 + \alpha_2*1 + \alpha_3*5= 0 
      \end{cases}
\Rightarrow        
       \begin{cases}
      \alpha_1 = 0 \\
      \alpha_2 = 0 \\
      \alpha_3 = 0 
      \end{cases}
$$

Donc la famille de vecteurs $S_1 = \left\{  e_1, e_2, e_3 \right\} $ forme une base de $\mathbb{R}^3$

2- <font color='red'> Pour $e_1=(1,0,-1)$, $e_2=(-1,1,0)$ et $e_3=(1,0,2)$</font>

Posons : $S_2 = \left\{  e_1, e_2, e_3 \right\} $

Montrons alors que $S_2 = \left\{  e_1, e_2, e_3 \right\} $ forme une base de $\mathbb{R}^3$

Soit $\alpha_1, \alpha_2,\alpha_3 \in \mathbb{R}$ :

$$
\alpha_1 e_1 + \alpha_2 e_2 + \alpha_3 e_3= (0,0,0) \Rightarrow 
    \begin{cases}
      \alpha_1*1+ \alpha_2* (-1) +\alpha_3*1= 0 \\
      \alpha_1*0 + \alpha_2*1 + \alpha_3*0= 0 \\
      \alpha_1*(-1) + \alpha_2*0 + \alpha_3*2= 0 
      \end{cases}
\Rightarrow        
       \begin{cases}
      \alpha_1 = 0 \\
      \alpha_2 = 0 \\
      \alpha_3 = 0 
      \end{cases}
$$

Donc la famille de vecteurs $S_2 = \left\{  e_1, e_2, e_3 \right\} $ forme une base de $\mathbb{R}^3$
```

```{admonition} Exercice 7
Sous quelles conditions sur le paramètre $\lambda$ , les vecteurs $e_1(\lambda, 1,0)$,  $e_2(-1,1, 2)$ et
$e_3(0, 1, -1)$ forment-ils une base de $\mathbb{R}^3$ ?
```
```{admonition} <font color='blue'>Réponse de l'exercice 7</font>
:class: attention, dropdown

Posons : $S = \left\{  e_1, e_2, e_3 \right\} $

 $$
 
 S = \left\{  e_1, e_2, e_3 \right\} ~forme ~une ~ base ~ de ~ \mathbb{R}^3 \Leftrightarrow (\alpha_1 e_1 + \alpha_2 e_2 + \alpha_3 e_3= (0,0,0) \Rightarrow \alpha_1 =\alpha_2= \alpha_3 = 0)
 
 $$

Soit alors $\alpha_1, \alpha_2,\alpha_3 \in \mathbb{R}$ :

$$
\alpha_1 e_1 + \alpha_2 e_2 + \alpha_3 e_3= (0,0,0) \Rightarrow 
    \begin{cases}
      \alpha_1*\lambda+ \alpha_2* (-1) +\alpha_3*0= 0 \\
      \alpha_1*1 + \alpha_2*1 + \alpha_3*1= 0 \\
      \alpha_1*0 + \alpha_2*2 + \alpha_3*(-1)= 0 
      \end{cases}
\Rightarrow        
    \begin{cases}
      \lambda*\alpha_1- \alpha_2= 0 \\
      \alpha_1 + \alpha_2 + \alpha_3= 0 \\
      2\alpha_2 - \alpha_3= 0 
      \end{cases}
$$

Donc la famille de vecteurs $S = \left\{  e_1, e_2, e_3 \right\} $ forme une base de $\mathbb{R}^3$ $\Leftrightarrow$  $\lambda = $

```

###### 3. base

```{admonition} Exercice 8
Soit $e_1 = (1,0,1)$, $e_2= (-1,1,0)$, $e_3 = (-1,1,1)$

- Montrer que la famille {$e_1$, $e_2$, $e_3$} constitue une base de $\mathbb{R}^3$
- Exprimer les coordonnées du vecteur (1,2,3) dans cette base
```

```{admonition} <font color='blue'>Réponse de l'exercice 8</font>
:class: attention, dropdown

Soit $e_1 = (1,0,1)$, $e_2= (-1,1,0)$, $e_3 = (-1,1,1)$

- Montrons que la famille {$e_1$, $e_2$, $e_3$} constitue une base de $\mathbb{R}^3$.


Posons : $S= \left\{  e_1, e_2, e_3 \right\}$

S est une base de $\mathbb{R}^3$ ssi S est libre.

Soit alors $\alpha_1, \alpha_2,\alpha_3 \in \mathbb{R}$ :

$$
\alpha_1 e_1 + \alpha_2 e_2 + \alpha_3 e_3= (0,0,0) \Rightarrow 
    \begin{cases}
      \alpha_1*1 + \alpha_2* (-1) +\alpha_3*(-1)= 0 \\
      \alpha_1*0 + \alpha_2*1 + \alpha_3*1= 0 \\
      \alpha_1*1 + \alpha_2*0 + \alpha_3*1= 0 
      \end{cases}
\Rightarrow        
       \begin{cases}
      \alpha_1 = 0 \\
      \alpha_2 = 0 \\
      \alpha_3 = 0 
      \end{cases}
$$

Donc la famille {$e_1$, $e_2$, $e_3$} constitue une base de $\mathbb{R}^3$.

- Exprimons les coordonnées du vecteur $E = (1,2,3)$ dans cette base.

$$
E = \lambda_1 e_1 + \lambda_2 e_2 + \lambda_3 e_3
$$

$$
E = \lambda_1 e_1 + \lambda_2 e_2 + \lambda_3 e_3 \Rightarrow 
    \begin{cases}
      \lambda_1*1 + \lambda_2* (-1) +\lambda_3*(-1)= 1 \\
      \lambda_1*0 + \lambda_2*1 + \lambda_3*1= 2 \\
      \lambda_1*1 + \lambda_2*0 + \lambda_3*1= 3 
      \end{cases}
$$

Donc :

$$
E = \lambda_1 e_1 + \lambda_2 e_2 + \lambda_3 e_3
$$


$$
E = \lambda_1 e_1 + \lambda_2 e_2 + \lambda_3 e_3
$$
```



###### 4. Famille génératrice

```{admonition} Exercice 9
- La famille de vecteurs $E = \left\{(1; 1; 0); (1;-1; 0); (1; 0; -1)\right\}$ est-elle une famille génératrice de $\mathbb{R}^3$ ? _Justifier_

```



```{admonition} <font color='blue'>Réponse de l'exercice 9</font>
:class: attention, dropdown


$E = \left\{(1; 1; 0); (1;-1; 0); (1; 0; -1)\right\}$ est-elle une famille génératrice de $\mathbb{R}^3$ ?

On pose : $v_1 = (1; 1; 0)$; $v_2=(1;-1; 0)$ ; $v_3= (1; 0; -1)$

La famille {$v_1$, $v_2$, $v_3$} est-elle génératrice de $\mathbb{R}^3$ ?

La famille {$v_1$, $v_2$, $v_3$} est génératrice de $\mathbb{R}^3$

Pour n’importe quel vecteur $v = (x, y,z)$ de $\mathbb{R}^3$, on doit trouver a,b, c $\in$ $\mathbb{R}$ tels que 

$$
av_1 +bv_2 +cv_3 = v
$$

```

```

```
