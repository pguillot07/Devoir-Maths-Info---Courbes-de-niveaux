## **Question 1 :**

Soit $c \in \mathbb{R}$.
On suppose que la fonction $f:\mathbb{R}^2 \to \mathbb{R}$ est continue et vérifie $f(x_1, x_2) \to +\infty$ quand $\|(x_1, x_2)| \to +\infty$.
Que peut-on dire de l'ensemble  de niveau $c$ de $f$ ?

Dans la suite la fonction $f$ est supposée continûment différentiable. On suppose également que le gradient $\nabla f$ ne s'annule pas dans un voisinage du point $x_0 = (x_{10}, x_{20}) \in \mathbb{R}^2$. On pose alors
$$
p(x_1, x_2) := \frac{\partial_2 f(x_0)}{\|\nabla f(x_0)\|} (x_1 - x_{10}) -
\frac{\partial_1 f(x_0)}{\|\nabla f(x_0)\|} (x_2 - x_{20}).
$$


#### **Réponse :**

Notons $C = \{(x_1,x_2) | f(x_1,x_2) = c\}$

- $C = f^{-1} (\{c\})$, c'est-à-dire que $C$ est l'ensemble des images réciproques de $\{c\}$, qui est un fermé de $\mathbb{R}$, par la fonction $f$ continue sur $\mathbb{R}^2$. 

Donc, d'après le critère de l'image réciproque, $C$ est un fermé de $\mathbb{R}^2$.

- De plus, $f(x_1,x_2) \to +\infty$ quand $\|(x_1,x_2)\| \to +\infty$  
Donc pour tout A $\in \mathbb{R}$, il existe $M \in \mathbb{R^*}$ tel que $\forall (x_1,x_2) \in \mathbb{R}, \|(x_1,x_2)\| \ge M => f(x_1,x_2) \ge A$.   
Donc, pour $c \in \mathbb{R}$, il existe $M_{c} \in \mathbb{R^*}$ tel que $\forall (x_1,x_2) \in \mathbb{R}, \|(x_1,x_2)\| \ge M_{c} => f(x_1,x_2) \ge c$.  
Ou encore, $\forall (x_1,x_2) \in \mathbb{R}, f(x_1,x_2) \le c => \|(x_1,x_2)\| \le M_{c}$.   
Donc $M_{c}$ est un majorant des éléments de $C$. Donc $C$ est borné.  

__Conclusion__ : $C$ est borné et fermé, c'est donc un compact de $\mathbb{R^2}$. 


## **Question 2 :**

Comment interpréter géométriquement le terme $p(x_1,x_2)$ ?

#### **Réponse :**

Au point $x_{0}$, le gradient de $f$ s'écrit $\nabla f(x_0) = (\partial_1 f(x_0) , \partial_2 f(x_0))$.   
On peut donc voir que : 

$$
\forall x = (x_1,x_2) \in \mathbb{R^2},
\begin{vmatrix}\frac{\nabla f(x_0)}{\|\nabla f(x_0)\|} & x - x_0  
\end{vmatrix}
= 
\frac{1}{\|\nabla f(x_0)\|} 
\begin{vmatrix}\partial_1 f(x_0) & x_1 - x_{10}\\
\partial_2 f(x_0) & x_2-x_{20}
\end{vmatrix}
=
-p(x_1,x_2)
$$

Ainsi, $p(x_1,x_2)$ représente l'opposé de l'aire du parallèlogramme engendré par les vecteurs $\frac{\nabla f(x_0)}{\|\nabla f(x_0)}$ et $x-x_0$. 

## **Question 3 :**

Montrer que dans un voisinage ouvert de $x_0$, on peut paramétriser l'ensemble de niveau $c:=f(x_0)$ au moyen de $p(x_1,x_2),$ c'est-à-dire qu'il existe un $\varepsilon > 0$ et une fonction (continûment différentiable) $\gamma :\left]-\varepsilon,\varepsilon \right[ \to \mathbb{R}^2$ tels que dans un voisinage ouvert de $x_0,$ $f(x_1,x_2) = c$ si et seulement si $(x_1, x_2) = \gamma(t)$ où $t = p(x_1, x_2)$.

### **Réponse :**

Considérons la fonction $g : \mathbb{R^2}\times\mathbb{R} \to \mathbb{R^2}$ telle que $\forall (x,t) \in \mathbb{R^2}\times\mathbb{R}, g(x,t) = (f(x) - c, p(x) - t)$. On notera $x = (x1,x2) \in \mathbb{R^2}$

- $f$ et $p$ sont continûment différentiables sur $\mathbb{R^2}$.   
$t \in \mathbb{R} \to -t$ est de classe $C^1$ sur $\mathbb{R}$.   
Donc **g est continûment différentiable** sur $\mathbb{R^2}\times\mathbb{R}$.

- $g(x_0, 0) = (f(x_0) - c, p(x_0)) = 0$ car $p(x_0) = 0$ et $f(x_0) = c$ par définition. 

- Calculons $\partial_x g(x,t)$ en un point $(x,t)$ quelconque.
On s'intéresse à la dérivée partielle par rapport à $x$, qui est un vecteur de $\mathbb{R^2}$. Cela revient à prendre les deux premières colonnes de la matrice jacobienne de $g$, c'est-à-dire:
$$ \forall (x,t) \in \mathbb{R^2}\times\mathbb{R}, \partial_x g(x,t) = \begin{bmatrix}\partial_1 (f(x_1,x_2) -c) & \partial_2 (f(x_1,x_2) -c)
\\ \partial_1 (p(x_1,x_2) - t) & \partial_2(p(x_1,x_2) - t)
\end{bmatrix}   
= \begin{bmatrix}\partial_1 f(x_1,x_2) & \partial_2 f(x_1,x_2)
\\ \partial_1 p(x_1,x_2) & \partial_2 p(x_1,x_2)
\end{bmatrix}$$
Le déterminant de cette matrice en $x_0$ vaut 
$$det = \partial_1 f(x_0) \partial_2 p(x_0) - \partial_1 p(x_0) \partial_2 f(x_0) 
= \frac{1}{\|\nabla f(x_0)\|}  (-(\partial_1 f(x_0))^2 - (\partial_2 f(x_0))^2) = -1$$

Or, la fonction déterminant est continue, donc on peut trouver un voisinage *U* de $x_0$ tel que la déterminant ne s'annule pas sur ce voisinage. On en déduit que **$\partial_x g$ est inversible sur $U\times\mathbb{R}$.**

On peut alors appliquer le Théorème des fonctions implicites à la fonction *g* autour du point $(x_0, 0)$, en lequel la fonction s'annule - en se restreignant à $U\times\mathbb{R}$ - et donc :   
Il existe des voisinages ouverts $V$ de $x_0$ et $W$ de $t=0$, ainsi qu'une unique fonction implicite $\gamma : 
- W \to \mathbb{R^2}$ tel que $\forall (x,t) \in V \times W , g(x,t) = 0 <=> x = \gamma(t)$. $W$ est un voisinage ouvert de $t=0$, il est donc bien de la forme $]-\varepsilon, \varepsilon[$ où $\varepsilon \in \mathbb{R^*_+}$.
- Par définition de $g$, l'équivalence se réécrit : $\forall (x,t) \in V \times W, f(x) = c <=> x = \gamma(t)$, où $t = p(x)$. 

On a donc bien le résultat demandé.  

## **Question 4 :**

**Réponse :**

- $\forall t \in ]-\varepsilon , \varepsilon[, p(y(t)) = t$. Or, $p$ est différentiable sur $\mathbb{R^2}$ et $\gamma$ est dérivable sur  $]-\varepsilon , \varepsilon[$. On peut donc appliquer la règle de différentiation en chaîne, ce qui donne :
$\forall t \in ]-\varepsilon , \varepsilon[, dp(\gamma(t)).\gamma'(t) = 1$. 
On en déduit que $\gamma$ **ne peut s'annuler sur l'ouvert** $]-\varepsilon , \varepsilon[$.

- $\forall t \in ]-\varepsilon , \varepsilon[, f(\gamma(t)) = c$ d'après la question précédente.   
Donc en différentiant la relation, on a :
$d(fo\gamma)(t) = d(c) = 0$.   
Or, 
$$
d(fo\gamma)(t) = df(\gamma(t)).\gamma'(t) = \ <\nabla f(\gamma(t) \ ,\ \gamma'(t)> = 0.$$


**Question 6 :**

Pour trouver $(x_1,y_1)$ à droite de $\nabla f(x_0,y_0)$ tel que $f(x_1,y_1) = c$, on peut implémenter l'algorithme de Newton sur le cercle $C_0$ de rayon $\delta$ et de centre $(x_0,y_0)$. Le point initial est choisi de sorte que $(x_1,y_1)$ soit bien à droite du gradient, on choisira donc de lancer l'algorithme en partant du point $(x_{1}', y_{1}')$ situé sur le cercle $C_0$, tel que l'angle entre les vecteurs $(x_1' - x_0, y_1' - y_0)$ et $\nabla f(x_0,y_0)$ soit de $+ \frac{\pi}{2}$. Ainsi, si on choisit $\delta$ suffisamment petit, on obtiendra un unique point $(x_1,y_1)$, en supposant la fonction suffisamment régulière au voisinage du point $(x_0,y_0)$.  

**Question 7 :**

La comparaison avec le premier segment est peu risquée, car les courbes de niveau "auto-intersectantes" sont rares. Prenons l'exemple de la fonction de Rosenbrock. En annulant les dérivées partielles, on constate que l'ensemble des points critiques est $\{(0.5, 0) ; (1, -1) ; (1,1) \}$. En particulier, le point $(0.5,0)$ n'est pas un extremum, c'est un col.   
De façon plus générale, les courbes auto-interctantes se coupent en un col, et l'ensmble des cols est au plus dénombrable, donc négligeable.


## **Question 8 :**

**Réponse :**

