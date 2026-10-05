## Cours 2 : Vocabulaire des probabilités

On travaille avec des expériences dont on ne connaît pas le résultat a priori.

---

### 1. Définitions fondamentales

**Définition (Événement, Univers) :**
- Un **événement** est le résultat d'une expérience aléatoire.
- L'ensemble des résultats possibles est appelé l'**univers**.
- Un événement est une **partie (un sous-ensemble) de l'univers**.

---

### 2. Exemple d'application : Lancer de deux dés

On considère le lancer de $2$ dés à $6$ faces : $1$ rouge et $1$ blanc.

#### A. Description de l'univers
L'univers s'écrit sous forme de couples d'éléments :

$$\Omega = \{(f_1, f_2) \ ; \ f_i \in \{1, \dots, 6\}\} = \{1, \dots, 6\}^2$$

Son cardinal est :

$$\text{Card}(\Omega) = 36$$

#### B. Description d'un événement
Soit l'événement $A$ : « au moins un des deux dés tombe sur $6$ ».

L'événement $A$ s'écrit comme l'union de deux sous-ensembles :

$$A = \{(6, i) \ ; \ i \in \{1, \dots, 6\}\} \cup \{(i, 6) \ ; \ i \in \{1, \dots, 6\}\}$$

En posant $A_1$ le sous-ensemble où le premier dé vaut $6$ et $A_2$ le sous-ensemble où le second dé vaut $6$ :

$$A = A_1 \cup A_2 \quad \text{avec} \quad A_1 \cap A_2 \neq \emptyset$$

*(L'élément $(6, 6)$ appartient aux deux sous-ensembles, donc leur intersection n'est pas vide.)*

#### C. Remarques importantes
- Si l'on s'intéressait uniquement au résultat du dé rouge, on aurait pu choisir l'univers $\{1, \dots, 6\}$.
- **Attention :** Il n'y a pas un choix d'univers unique. Il faut veiller à choisir un univers « facile » à manipuler selon le problème.
- On note souvent l'univers $\Omega$. Les événements $A, B$ sont des sous-ensembles de $\Omega$ ($A \subset \Omega$, $B \subset \Omega$), sur lesquels on effectue des opérations comme l'intersection $A \cap B$ ou l'union $A \cup B$.

---

### 3. Exercice d'application

**Énoncé :** On effectue trois lancers successifs d'une pièce de monnaie (Pile $P$ et Face $F$).

1. **Décrire l'univers $\Omega$ :**
   $$\Omega = \{P, F\}^3 = \{(P,P,P), (P,P,F), (P,F,P), (P,F,F), (F,P,P), (F,P,F), (F,F,P), (F,F,F)\}$$
   $$\text{Card}(\Omega) = 2^3 = 8$$

2. **Décrire l'événement $B$ : « obtenir exactement 2 piles » :**
   $$B = \{(P, P, F), (P, F, P), (F, P, P)\}$$
   $$\text{Card}(B) = 3$$

### 4. Généralisation : $n$ tirages successifs

On effectue $n$ tirages successifs à Pile ($P$) ou Face ($F$). L'univers est $\Omega = \{P, F\}^n$.

On souhaite déterminer le cardinal de l'événement $A$ : « obtenir exactement $k$ fois Pile ».

Un élément de $A$ s'écrit sous la forme d'un $n$-uplet $(P, F, P, P, \dots)$ contenant exactement $k$ fois la lettre $P$.

> **Méthode :** Le nombre de façons de placer ces $k$ Piles parmi les $n$ emplacements disponibles est donné par le coefficient binomial :
> $$\text{Card}(A) = \#A = \binom{n}{k}$$

---

## Cours 3 : Probabilités sur un univers fini

### 1. Définition d'une probabilité

Soit $\Omega = \{\omega_1, \dots, \omega_N\}$ un univers fini de cardinal $\#\Omega = N$.

Une **probabilité** $\mathbb{P}$ (ou $P$) est une application définie de l'ensemble des parties $\mathcal{P}(\Omega)$ vers l'intervalle $[0, 1]$ :

$$\mathbb{P} : \mathcal{P}(\Omega) \longrightarrow [0, 1]$$

Elle vérifie les deux axiomes fondamentaux :

1. **Additivité sur des événements disjoints :**
   $$\mathbb{P}(A \cup B) = \mathbb{P}(A) + \mathbb{P}(B) \quad \text{si } A \cap B = \emptyset$$

2. **Masse totale :**
   $$\mathbb{P}(\Omega) = 1$$

---

### 2. Probabilité élémentaire et loi de probabilité

Définir la fonction $\mathbb{P}$ revient à attribuer à chaque événement élémentaire $\{\omega_i\}$ une probabilité $p_i = \mathbb{P}(\{\omega_i\})$.

- Pour tout $i \in \{1, \dots, N\}$, $p_i \in [0, 1]$.
- La somme des probabilités élémentaires vaut 1 :
  $$\sum_{i=1}^{N} \mathbb{P}(\{\omega_i\}) = \sum_{i=1}^{N} p_i = \mathbb{P}(\Omega) = 1$$

Pour tout événement $A = \{\omega_{i_1}, \dots, \omega_{i_k}\}$, sa probabilité est la somme des probabilités des événements élémentaires qui le composent :

$$\mathbb{P}(A) = \sum_{j=1}^{k} \mathbb{P}(\{\omega_{i_j}\})$$

> **Remarque (Événement contraire) :**
> Puisque $\Omega = A \cup \overline{A}$ avec $A \cap \overline{A} = \emptyset$, on a $\mathbb{P}(\Omega) = \mathbb{P}(A) + \mathbb{P}(\overline{A}) = 1$. D'où :
> $$\mathbb{P}(\overline{A}) = 1 - \mathbb{P}(A)$$

---

### 3. Probabilité uniforme (Équiprobabilité)

**Définition :**
Soit $\Omega = \{\omega_1, \dots, \omega_N\}$. Si tous les événements élémentaires ont la même chance de se réaliser, on définit la **probabilité uniforme** sur $\Omega$ par :

$$\mathbb{P}(A) = \frac{\#A}{\#\Omega} = \frac{\text{Card}(A)}{\text{Card}(\Omega)}$$

---

### 4. Exemple d'application

**Énoncé :** On tire $n$ fois de suite à Pile ou Face. Quelle est la probabilité de l'événement $A$ : « obtenir exactement $1$ fois Face » ?

1. **Choix de l'univers :**
   On prend $\Omega = \{P, F\}^n$ muni de la probabilité uniforme. Chaque $n$-uplet a autant de chance de sortir qu'un autre (par exemple, $(P, P, \dots, P)$ a la même probabilité que $(P, F, \dots, P)$).
   $$\text{Card}(\Omega) = 2^n$$

2. **Calcul de $\mathbb{P}(A)$ :**
   L'événement $A$ correspond aux $n$-uplets contenant exactement un $F$ et $(n-1)$ fois $P$. Il y a $n$ emplacements possibles pour positionner la lettre $F$.
   $$\text{Card}(A) = \binom{n}{1} = n$$

   D'où la probabilité :
   $$\mathbb{P}(A) = \frac{\text{Card}(A)}{\text{Card}(\Omega)} = \frac{n}{2^n}$$

#### 3. Probabilité de tomber au moins une fois sur Face
Soit l'événement $A$ : « obtenir au moins une fois Face ».

L'événement contraire $\overline{A}$ correspond à « n'obtenir aucun Face », c'est-à-dire obtenir uniquement des Piles :

$$\overline{A} = \{(P, \dots, P)\}$$

On a $\text{Card}(\overline{A}) = 1$, d'où :

$$\mathbb{P}(\overline{A}) = \frac{1}{2^n}$$

En utilisant la propriété de l'événement contraire ($\mathbb{P}(A) + \mathbb{P}(\overline{A}) = 1$) :

$$\mathbb{P}(A) = 1 - \mathbb{P}(\overline{A}) = 1 - \frac{1}{2^n}$$

---

### 5. Formule du criblage (Propriété de l'union)

#### A. Exemple concret
À la plage :
- Il pleut $1$ jour sur $9$ : $\mathbb{P}(P) = \frac{1}{9}$
- Il y a des méduses $1$ jour sur $6$ : $\mathbb{P}(M) = \frac{1}{6}$
- Il y a à la fois de la pluie et des méduses $1$ jour sur $12$ : $\mathbb{P}(M \cap P) = \frac{1}{12}$

Quelle est la probabilité d'être à la plage sans méduses ni pluie ?

On cherche $\mathbb{P}(\overline{M} \cap \overline{P})$. Par les lois de De Morgan, $\overline{M} \cap \overline{P} = \overline{M \cup P}$, donc :

$$\mathbb{P}(\overline{M} \cap \overline{P}) = 1 - \mathbb{P}(M \cup P)$$

Calcul de $\mathbb{P}(M \cup P)$ :

$$\mathbb{P}(M \cup P) = \mathbb{P}(M) + \mathbb{P}(P) - \mathbb{P}(M \cap P) = \frac{1}{6} + \frac{1}{9} - \frac{1}{12} = \frac{6}{36} + \frac{4}{36} - \frac{3}{36} = \frac{7}{36}$$

D'où :

$$\mathbb{P}(\overline{M} \cap \overline{P}) = 1 - \frac{7}{36} = \frac{29}{36}$$

#### B. Proposition générale
> **Proposition :** Soient $A, B \subset \Omega$,
> $$\mathbb{P}(A \cup B) + \mathbb{P}(A \cap B) = \mathbb{P}(A) + \mathbb{P}(B)$$
> Soit sous la forme usuelle :
> $$\mathbb{P}(A \cup B) = \mathbb{P}(A) + \mathbb{P}(B) - \mathbb{P}(A \cap B)$$

**Démonstration :**
On décompose $A \cup B$ en union disjointes : $A \cup B = (A \setminus B) \cup B$.
Donc $\mathbb{P}(A \cup B) = \mathbb{P}(A \setminus B) + \mathbb{P}(B)$.

Or, $A = (A \setminus B) \cup (A \cap B)$ (union disjointe), d'où $\mathbb{P}(A) = \mathbb{P}(A \setminus B) + \mathbb{P}(A \cap B)$, ce qui donne $\mathbb{P}(A \setminus B) = \mathbb{P}(A) - \mathbb{P}(A \cap B)$.

En remplaçant :

$$\mathbb{P}(A \cup B) = \mathbb{P}(A) - \mathbb{P}(A \cap B) + \mathbb{P}(B)$$

---

### 6. Produit d'espaces probabilisés

Comment apparaissent les probabilités lors de la combinaison de plusieurs expériences ?

Soient deux espaces probabilisés $(\Omega_1, \mathbb{P}_1)$ et $(\Omega_2, \mathbb{P}_2)$.
On définit l'espace produit $(\Omega_1 \times \Omega_2, \mathbb{P}_1 \otimes \mathbb{P}_2)$ où la probabilité produit vérifie :

$$\mathbb{P}_1 \otimes \mathbb{P}_2 (\{(\omega_1, \omega_2)\}) = \mathbb{P}_1(\{\omega_1\}) \cdot \mathbb{P}_2(\{\omega_2\})$$

> **Remarque :** Si $\mathbb{P}_1$ et $\mathbb{P}_2$ sont des probabilités uniformes, alors $\mathbb{P}_1 \otimes \mathbb{P}_2$ est également une probabilité uniforme sur $\Omega_1 \times \Omega_2$.

---

## Cours 4 : Probabilités conditionnelles

### 1. Résolution de l'exemple du lancer de dés

On lance deux dés. On s'intéresse aux événements :
- $A$ : « la somme des deux faces vaut $8$ »
- $B$ : « obtenir au moins un $3$ »

#### A. Étude des événements
- **Univers :** $\Omega = \{1, \dots, 6\}^2$, avec $\text{Card}(\Omega) = 36$.
- **Événement $B$ :** $B = \{(3, i) \ ; \ i \in \{1,\dots,6\}\} \cup \{(j, 3) \ ; \ j \in \{1,\dots,6\}\}$.
  $$\text{Card}(B) = 6 + 6 - 1 = 11 \implies \mathbb{P}(B) = \frac{11}{36}$$
- **Événement $A$ :**
  $$A = \{(2, 6), (3, 5), (4, 4), (5, 3), (6, 2)\}$$
  $$\text{Card}(A) = 5 \implies \mathbb{P}(A) = \frac{\text{Card}(A)}{\text{Card}(\Omega)} = \frac{5}{36}$$

#### B. Calcul de la probabilité sachant $A$
On cherche la probabilité d'avoir au moins un $3$ ($B$) **sachant que** la somme vaut $8$ ($A$).

En se restreignant à $A$ comme « nouvel univers » :
- Les cas favorables dans $A$ qui contiennent un $3$ sont $(3, 5)$ et $(5, 3)$, soit l'intersection $B \cap A$.
- $\text{Card}(B \cap A) = 2$.

La probabilité recherchée est donc :

$$\frac{\text{Card}(B \cap A)}{\text{Card}(A)} = \frac{2}{5} = \frac{\mathbb{P}(B \cap A)}{\mathbb{P}(A)}$$

---

### 2. Définition générale

> **Définition :**
> Soit $A \subset \Omega$ un événement tel que $\mathbb{P}(A) > 0$.
> La **probabilité conditionnelle** de $B \subset \Omega$ sachant $A$, notée $\mathbb{P}_A(B)$ (ou $\mathbb{P}(B \mid A)$), est donnée par :
> $$\mathbb{P}_A(B) = \frac{\mathbb{P}(A \cap B)}{\mathbb{P}(A)}$$

> **Remarque :**
> Pour un événement $A$ fixé ($\mathbb{P}(A) > 0$), l'application $\mathbb{P}_A : \mathcal{P}(\Omega) \to [0, 1]$ définit une **nouvelle probabilité** sur $\Omega$.
>
> En effet, elle vérifie les axiomes d'une probabilité :
>