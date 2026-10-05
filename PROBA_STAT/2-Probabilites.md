## Cours 2 : Vocabulaire des probabilités

On travaille avec des expériences aléatoires, c'est-à-dire des expériences dont on ne peut pas prédire le résultat avec certitude a priori.

---

### 1. Définitions fondamentales

**Définition (Univers, Événement) :**
- L'ensemble de tous les résultats possibles d'une expérience aléatoire est appelé l'**univers**, généralement noté $\Omega$.
- Un **événement élémentaire** est une issue unique de l'expérience, notée $\{\omega\}$ avec $\omega \in \Omega$.
- Un **événement** est une partie (un sous-ensemble) de l'univers : $A \subset \Omega$.

---

### 2. Exemple d'application : Lancer de deux dés

On considère le lancer de $2$ dés discernables à $6$ faces : $1$ rouge et $1$ blanc.

#### A. Description de l'univers
L'univers s'écrit sous forme de couples ordonnés $(f_1, f_2)$ où $f_1$ représente la face du premier dé (rouge) et $f_2$ celle du second (blanc) :

$$\Omega = \{(f_1, f_2) \ ; \ f_i \in \{1, \dots, 6\}\} = \{1, \dots, 6\}^2$$

Son cardinal (nombre total d'issues possibles) est :

$$\text{Card}(\Omega) = 6 \times 6 = 36$$

#### B. Description d'un événement
Soit l'événement $A$ : « au moins un des deux dés tombe sur $6$ ».

L'événement $A$ s'écrit comme l'union de deux sous-ensembles :
- $A_1$ : « le premier dé donne $6$ » $\implies A_1 = \{(6, i) \ ; \ i \in \{1, \dots, 6\}\}$
- $A_2$ : « le second dé donne $6$ » $\implies A_2 = \{(i, 6) \ ; \ i \in \{1, \dots, 6\}\}$

$$A = A_1 \cup A_2 \quad \text{avec} \quad A_1 \cap A_2 = \{(6, 6)\} \neq \emptyset$$

*(L'issue $(6, 6)$ appartient aux deux sous-ensembles, donc leur intersection n'est pas vide.)*

#### C. Remarques importantes
- Si l'on s'intéressait uniquement au résultat du dé rouge, on aurait pu choisir un univers plus restreint : $\Omega' = \{1, \dots, 6\}$.
- **Attention :** Il n'y a pas un choix d'univers unique pour une expérience. On choisit toujours l'univers le plus simple et le plus adapté aux questions posées.
- Les événements $A, B$ étant des sous-ensembles de $\Omega$ ($A \subset \Omega$, $B \subset \Omega$), on leur applique le langage des ensembles :
    - **Intersection $A \cap B$ :** l'événement « $A$ ET $B$ se réalisent ».
    - **Union $A \cup B$ :** l'événement « $A$ OU $B$ (ou les deux) se réalise ».
    - **Événements incompatibles :** deux événements $A$ et $B$ sont dits disjoints (ou incompatibles) si $A \cap B = \emptyset$.

---

### 3. Exercice d'application

**Énoncé :** On effectue trois lancers successifs d'une pièce de monnaie équilibrée (Pile $P$ et Face $F$).

1. **Décrire l'univers $\Omega$ :**
   $$\Omega = \{P, F\}^3 = \{(P,P,P), (P,P,F), (P,F,P), (P,F,F), (F,P,P), (F,P,F), (F,F,P), (F,F,F)\}$$
   $$\text{Card}(\Omega) = 2^3 = 8$$

2. **Décrire l'événement $B$ : « obtenir exactement 2 Piles » :**
   $$B = \{(P, P, F), (P, F, P), (F, P, P)\}$$
   $$\text{Card}(B) = 3$$

---

### 4. Généralisation : $n$ tirages successifs

On effectue $n$ tirages successifs à Pile ($P$) ou Face ($F$). L'univers est $\Omega = \{P, F\}^n$, de cardinal $\text{Card}(\Omega) = 2^n$.

On souhaite déterminer le cardinal de l'événement $A$ : « obtenir exactement $k$ fois Pile » (avec $0 \le k \le n$).

Un élément de $A$ s'écrit sous la forme d'un $n$-uplet $(P, F, P, P, \dots)$ contenant exactement $k$ fois la lettre $P$ et $(n-k)$ fois la lettre $F$.

> **Méthode :** Choisir un tel $n$-uplet revient à choisir l'emplacement des $k$ lettres $P$ parmi les $n$ positions disponibles. Le nombre de choix possibles est donné par le coefficient binomial :
> $$\text{Card}(A) = \#A = \binom{n}{k}$$

---

## Cours 3 : Probabilités sur un univers fini

### 1. Définition d'une probabilité

Soit $\Omega = \{\omega_1, \dots, \omega_N\}$ un univers fini de cardinal $\#\Omega = N$.

On note $\mathcal{P}(\Omega)$ l'ensemble de toutes les parties de $\Omega$. Une **probabilité** $\mathbb{P}$ est une application :

$$\mathbb{P} : \mathcal{P}(\Omega) \longrightarrow [0, 1]$$

Elle vérifie les deux axiomes fondamentaux :

1. **Additivité sur des événements incompatibles :**
   $$\mathbb{P}(A \cup B) = \mathbb{P}(A) + \mathbb{P}(B) \quad \text{si } A \cap B = \emptyset$$

2. **Masse totale (Normalisation) :**
   $$\mathbb{P}(\Omega) = 1$$

---

### 2. Probabilité élémentaire et loi de probabilité

Définir une probabilité $\mathbb{P}$ sur un univers fini $\Omega$ revient à attribuer à chaque événement élémentaire $\{\omega_i\}$ un nombre réel $p_i = \mathbb{P}(\{\omega_i\})$, appelé probabilité élémentaire.

- Pour tout $i \in \{1, \dots, N\}$, $p_i \in [0, 1]$.
- La somme des probabilités élémentaires vaut 1 :
  $$\sum_{i=1}^{N} \mathbb{P}(\{\omega_i\}) = \sum_{i=1}^{N} p_i = \mathbb{P}(\Omega) = 1$$

Pour tout événement non vide $A = \{\omega_{i_1}, \dots, \omega_{i_k}\}$, sa probabilité est la somme des probabilités des événements élémentaires qui le composent :

$$\mathbb{P}(A) = \sum_{j=1}^{k} \mathbb{P}(\{\omega_{i_j}\})$$

Par convention, pour l'événement impossible : $\mathbb{P}(\emptyset) = 0$.

> **Propriété (Événement contraire) :**
> Tout événement $A$ et son contraire $\overline{A}$ forment une partition de $\Omega$ ($A \cup \overline{A} = \Omega$ et $A \cap \overline{A} = \emptyset$).
> Par additivité : $\mathbb{P}(A \cup \overline{A}) = \mathbb{P}(A) + \mathbb{P}(\overline{A}) = \mathbb{P}(\Omega) = 1$, d'où :
> $$\mathbb{P}(\overline{A}) = 1 - \mathbb{P}(A)$$

---

### 3. Probabilité uniforme (Équiprobabilité)

**Définition :**
Soit $\Omega = \{\omega_1, \dots, \omega_N\}$ un univers fini. Lorsqu'aucun résultat n'est favorisé, tous les événements élémentaires ont la même probabilité :

$$p_1 = p_2 = \dots = p_N = \frac{1}{\text{Card}(\Omega)} = \frac{1}{N}$$

On dit qu'il y a **équiprobabilité** (ou probabilité uniforme). Dans ce cadre, pour tout événement $A \subset \Omega$ :

$$\mathbb{P}(A) = \frac{\text{Nombre de cas favorables}}{\text{Nombre de cas possibles}} = \frac{\#A}{\#\Omega} = \frac{\text{Card}(A)}{\text{Card}(\Omega)}$$

---

### 4. Exemples d'application

**Énoncé :** On tire $n$ fois de suite une pièce équilibrée à Pile ou Face.

#### A. Probabilité d'obtenir exactement 1 fois Face
1. **Choix de l'univers :**
   $\Omega = \{P, F\}^n$ muni de la probabilité uniforme (chaque séquence a la même probabilité $1/2^n$).
   $$\text{Card}(\Omega) = 2^n$$

2. **Calcul de $\mathbb{P}(A)$ pour $A$ : « obtenir exactement 1 fois Face » :**
   L'événement $A$ contient les $n$-uplets ayant 1 seul $F$ et $(n-1)$ lettres $P$. Le $F$ peut être placé à $n$ positions différentes.
   $$\text{Card}(A) = \binom{n}{1} = n$$

   D'où :
   $$\mathbb{P}(A) = \frac{\text{Card}(A)}{\text{Card}(\Omega)} = \frac{n}{2^n}$$

#### B. Probabilité de tomber au moins une fois sur Face
Soit l'événement $A$ : « obtenir au moins une fois Face ».

L'événement contraire $\overline{A}$ est « n'obtenir aucun Face », c'est-à-dire n'obtenir que des Piles :

$$\overline{A} = \{(P, P, \dots, P)\}$$

On a $\text{Card}(\overline{A}) = 1$, donc $\mathbb{P}(\overline{A}) = \frac{1}{2^n}$.

En utilisant la propriété de l'événement contraire :

$$\mathbb{P}(A) = 1 - \mathbb{P}(\overline{A}) = 1 - \frac{1}{2^n}$$

---

### 5. Formule du criblage (Propriété de l'union)

#### A. Exemple concret
À la plage :
- Il pleut $1$ jour sur $9$ : $\mathbb{P}(P) = \frac{1}{9}$
- Il y a des méduses $1$ jour sur $6$ : $\mathbb{P}(M) = \frac{1}{6}$
- Il y a à la fois de la pluie et des méduses $1$ jour sur $12$ : $\mathbb{P}(M \cap P) = \frac{1}{12}$

Quelle est la probabilité d'être à la plage sans méduses ni pluie ?

On cherche $\mathbb{P}(\overline{M} \cap \overline{P})$. D'après les lois de De Morgan, $\overline{M} \cap \overline{P} = \overline{M \cup P}$ (le contraire de « pluie ou méduses »), d'où :

$$\mathbb{P}(\overline{M} \cap \overline{P}) = 1 - \mathbb{P}(M \cup P)$$

Calcul de $\mathbb{P}(M \cup P)$ :

$$\mathbb{P}(M \cup P) = \mathbb{P}(M) + \mathbb{P}(P) - \mathbb{P}(M \cap P) = \frac{1}{6} + \frac{1}{9} - \frac{1}{12} = \frac{6 + 4 - 3}{36} = \frac{7}{36}$$

D'où :

$$\mathbb{P}(\overline{M} \cap \overline{P}) = 1 - \frac{7}{36} = \frac{29}{36}$$

#### B. Proposition générale (Formule du criblage pour deux ensembles)
> **Proposition :** Soient $A, B \subset \Omega$,
> $$\mathbb{P}(A \cup B) = \mathbb{P}(A) + \mathbb{P}(B) - \mathbb{P}(A \cap B)$$

**Démonstration :**
On décompose $A \cup B$ en union de sous-ensembles disjoints : $A \cup B = (A \setminus B) \cup B$.
Par additivité : $\mathbb{P}(A \cup B) = \mathbb{P}(A \setminus B) + \mathbb{P}(B)$.

De même, $A$ se décompose en union disjointe : $A = (A \setminus B) \cup (A \cap B)$.
D'où $\mathbb{P}(A) = \mathbb{P}(A \setminus B) + \mathbb{P}(A \cap B)$, ce qui donne $\mathbb{P}(A \setminus B) = \mathbb{P}(A) - \mathbb{P}(A \cap B)$.

En remplaçant :

$$\mathbb{P}(A \cup B) = \mathbb{P}(A) - \mathbb{P}(A \cap B) + \mathbb{P}(B)$$

---

### 6. Produit d'espaces probabilisés

Lorsque l'on combine deux expériences aléatoires indépendantes :

Soient deux espaces probabilisés $(\Omega_1, \mathbb{P}_1)$ et $(\Omega_2, \mathbb{P}_2)$.
On définit l'espace produit $(\Omega_1 \times \Omega_2, \mathbb{P}_1 \otimes \mathbb{P}_2)$ où la probabilité produit vérifie, pour tout $(\omega_1, \omega_2) \in \Omega_1 \times \Omega_2$ :

$$(\mathbb{P}_1 \otimes \mathbb{P}_2) (\{(\omega_1, \omega_2)\}) = \mathbb{P}_1(\{\omega_1\}) \times \mathbb{P}_2(\{\omega_2\})$$

> **Remarque :** Si $\mathbb{P}_1$ et $\mathbb{P}_2$ sont des probabilités uniformes sur $\Omega_1$ et $\Omega_2$, alors la probabilité produit $\mathbb{P}_1 \otimes \mathbb{P}_2$ est aussi la probabilité uniforme sur l'espace produit $\Omega_1 \times \Omega_2$.

---

## Cours 4 : Probabilités conditionnelles

### 1. Exemple introductif : Lancer de deux dés

On lance deux dés équilibrés à $6$ faces. On s'intéresse aux événements :
- $A$ : « la somme des deux faces vaut $8$ »
- $B$ : « obtenir au moins un $3$ »

#### A. Étude des événements dans l'univers global $\Omega$
- **Univers :** $\Omega = \{1, \dots, 6\}^2$, avec $\text{Card}(\Omega) = 36$ (équiprobabilité).
- **Événement $B$ :** $B = \{(3, i) \ ; \ i \in \{1,\dots,6\}\} \cup \{(j, 3) \ ; \ j \in \{1,\dots,6\}\}$.
  Par formule de l'union : $\text{Card}(B) = 6 + 6 - 1 = 11$ (en retirant le doublon $(3,3)$).
  $$\mathbb{P}(B) = \frac{11}{36}$$
- **Événement $A$ :**
  $$A = \{(2, 6), (3, 5), (4, 4), (5, 3), (6, 2)\}$$
  $$\text{Card}(A) = 5 \implies \mathbb{P}(A) = \frac{5}{36}$$

#### B. Probabilité de $B$ sachant $A$
Si l'on sait que l'événement $A$ est réalisé, $A$ devient notre **nouvel univers de référence**.

- Dans cet univers restreint $A$, les issues qui réalisent aussi $B$ sont celles de l'intersection $A \cap B$ :
  $$A \cap B = \{(3, 5), (5, 3)\} \implies \text{Card}(A \cap B) = 2$$

La probabilité d'obtenir au moins un $3$ sachant que la somme vaut $8$ est donc :

$$\frac{\text{Card}(A \cap B)}{\text{Card}(A)} = \frac{2}{5}$$

En divisant le numérateur et le dénominateur par $\text{Card}(\Omega) = 36$, on retrouve :

$$\frac{\text{Card}(A \cap B) / 36}{\text{Card}(A) / 36} = \frac{\mathbb{P}(A \cap B)}{\mathbb{P}(A)}$$

---

### 2. Définition générale

> **Définition :**
> Soit $A \subset \Omega$ un événement de probabilité non nulle ($\mathbb{P}(A) > 0$).
> La **probabilité conditionnelle** de $B$ sachant $A$, notée $\mathbb{P}_A(B)$ ou $\mathbb{P}(B \mid A)$, est définie par :
> $$\mathbb{P}_A(B) = \frac{\mathbb{P}(A \cap B)}{\mathbb{P}(A)}$$

> **Propriété fondamentale :**
> Pour un événement $A$ fixé tel que $\mathbb{P}(A) > 0$, l'application :
> $$\mathbb{P}_A : \mathcal{P}(\Omega) \longrightarrow [0, 1], \quad B \longmapsto \mathbb{P}_A(B)$$
> définit **une véritable probabilité** sur $\Omega$.
>
> **Démonstration des axiomes :**
> 1. **Masse totale :**
     >    $$\mathbb{P}_A(\Omega) = \frac{\mathbb{P}(A \cap \Omega)}{\mathbb{P}(A)} = \frac{\mathbb{P}(A)}{\mathbb{P}(A)} = 1$$
> 2. **Additivité :** Si $B_1 \cap B_2 = \emptyset$, alors $(A \cap B_1) \cap (A \cap B_2) = \emptyset$. Ainsi :
     >    $$\mathbb{P}_A(B_1 \cup B_2) = \frac{\mathbb{P}(A \cap (B_1 \cup B_2))}{\mathbb{P}(A)} = \frac{\mathbb{P}((A \cap B_1) \cup (A \cap B_2))}{\mathbb{P}(A)} = \frac{\mathbb{P}(A \cap B_1) + \mathbb{P}(A \cap B_2)}{\mathbb{P}(A)} = \mathbb{P}_A(B_1) + \mathbb{P}_A(B_2)$$

Par conséquent, toutes les propriétés usuelles d'une probabilité s'appliquent à $\mathbb{P}_A$ (par exemple : $\mathbb{P}_A(\overline{B}) = 1 - \mathbb{P}_A(B)$).

---

### 3. Formules fondamentales

#### A. Formule des probabilités composées
De la définition de la probabilité conditionnelle, on déduit :

$$\mathbb{P}(A \cap B) = \mathbb{P}(A) \times \mathbb{P}_A(B)$$

De manière symétrique (si $\mathbb{P}(B) > 0$) :

$$\mathbb{P}(A \cap B) = \mathbb{P}(B) \times \mathbb{P}_B(A)$$

#### B. Formule de Bayes (forme simple)
En égalisant les deux expressions de $\mathbb{P}(A \cap B)$, on obtient la **formule de Bayes** :

$$\mathbb{P}_A(B) = \frac{\mathbb{P}_B(A) \times \mathbb{P}(B)}{\mathbb{P}(A)}$$