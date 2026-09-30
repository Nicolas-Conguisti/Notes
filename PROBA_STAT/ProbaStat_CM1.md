# Probas / stats

## Évaluations

2 évaluations :
- 1 partiel
- 1 examen

### Contrôle
- **Cours :** 7/8 pts
- **Exos élémentaires :** 7/8 pts
- **Exos plus difficiles :** reste

## Au programme :
- Dénombrement
- Probabilités
- Variables aléatoires (moyenne, variance, inégalités)
- Théorème limites, méthode Monte-Carlo, méthode probabiliste

---

## Cours 1 : Dénombrement

Dans un univers équiprobable $\Omega$, la probabilité d'un événement $A$ repose sur la **règle de Laplace** :

$$P(A) = \frac{\text{Card}(A)}{\text{Card}(\Omega)}$$

Le dénombrement revient à calculer le nombre d'éléments d'un ensemble fini $E$, c'est-à-dire son **cardinal**, noté :

$$\text{Card}(E) = \#E$$

*Exemple :* Soit $E = \{a, b, c, d\}$. L'ensemble contient $4$ éléments distincts, donc $\text{Card}(E) = 4$.

*Notation :* $E = \{1, 3, 2\}$

---

### 1. Théorie des ensembles

#### Inclusion et Égalité

**Définition (Inclusion) :** Soient $A, B$ deux ensembles. On dit que $A \subset B$ si :

$$\forall x \in A, \ x \in B$$

*Exemple :* $A = \{1, 2\}$, $B = \{2, 1, 3\} \implies A \subset B$

**Définition (Égalité) :** Deux ensembles $A, B$ sont égaux si $A \subset B$ et $B \subset A$. On note $A = B$.

> **Méthode :** Pour prouver $A = B$, on montre la double inclusion ($A \subset B$ puis $B \subset A$).

*Exemple :* $B = \{2, 1, 3\}$ et $E = \{1, 3, 2\} \implies E = B$

---

### 2. Opérations sur les ensembles

#### Définitions
- **Intersection :** $A \cap B = \{x \,;\, x \in A \text{ et } x \in B\}$
- **Union :** $A \cup B = \{x \,;\, x \in A \text{ ou } x \in B\}$
- **Complémentaire :** $\overline{B}$ (ou $E \setminus B$) représente l'ensemble des éléments de $E$ qui ne sont pas dans $B$.

#### Distributivité
*(Attention : $(A \cup B) \cap C \neq A \cup (B \cap C)$ en général)*

**Fait :** $A \cap (B \cup C) = (A \cap B) \cup (A \cap C)$

##### Preuve par double inclusion ($G = D$) :
Soient $G = A \cap (B \cup C)$ et $D = (A \cap B) \cup (A \cap C)$.

1. **$G \subset D$ :** Soit $x \in G$, donc $x \in A$ et $x \in (B \cup C)$.
   - 1er cas : $x \in B \implies x \in A \cap B \implies x \in D$.
   - 2ème cas : $x \notin B \implies x \in C$ (car $x \in B \cup C$) $\implies x \in A \cap C \implies x \in D$.
2. **$D \subset G$ :** $B \subset B \cup C \implies (A \cap B) \subset A \cap (B \cup C)$, et de même pour $C$. Donc $D \subset G$.

---

### 3. Produit cartésien et Listes

**Définition :** Soient $A_1, \dots, A_n$ $n$ ensembles.

$$A_1 \times A_2 \times \dots \times A_n = \{(a_1, \dots, a_n) \,;\, a_i \in A_i\}$$

*Exemple :* $A = \{1, 2, 3\}$, $B = \{x, y\}$
$$A \times B = \{(1, x), (1, y), (2, x), (2, y), (3, x), (3, y)\}$$

> **Rappel :** Dans une liste ($n$-uplet), l'ordre compte : $(1, 2) \neq (2, 1)$. Donc $A \times B \neq B \times A$.

---

### 4. Méthodes de calcul du cardinal

#### A. Union disjointe (Partition)
Si $E = \bigcup_{i=1}^{n} A_i$ avec $A_i \cap A_j = \emptyset$ pour tout $i \neq j$ :

$$\text{Card}(E) = \sum_{i=1}^{n} \text{Card}(A_i)$$

#### B. Cas d'ensembles non disjoints
Si $A \cap B \neq \emptyset$, on retire l'intersection comptée deux fois :

$$\text{Card}(A \cup B) = \text{Card}(A) + \text{Card}(B) - \text{Card}(A \cap B)$$

##### Preuve :
En posant $A \setminus B = \{x \in A \,;\, x \notin B\}$ :
1. $A \cup B = (A \setminus B) \cup B$ (union disjointe) $\implies \text{Card}(A \cup B) = \text{Card}(A \setminus B) + \text{Card}(B)$
2. $A = (A \cap B) \cup (A \setminus B)$ (union disjointe) $\implies \text{Card}(A) = \text{Card}(A \cap B) + \text{Card}(A \setminus B)$
3. D'où $\text{Card}(A \setminus B) = \text{Card}(A) - \text{Card}(A \cap B)$, ce qui donne la formule.

---

### 5. Applications, Image réciproque et Bijections

#### A. Image réciproque et Découpage par cas
Soit une fonction $f : E \to \{1, \dots, n\}$.
L'**image réciproque** d'un élément $i$, notée $f^{-1}(\{i\})$, est l'ensemble de tous les éléments de départ qui atterrissent sur $i$ par la fonction $f$ :

$$f^{-1}(\{i\}) = \{x \in E \,;\, f(x) = i\}$$

> **Exemple concret :** Soit $E$ un groupe d'élèves et $f$ l'application qui associe à chaque élève sa note à un devoir (de $1$ à $20$).
> $f^{-1}(\{20\})$ est simplement l'ensemble des élèves qui ont eu $20/20$.

Puisque chaque élément de $E$ a une et une seule image par $f$, regrouper les éléments de $E$ selon leur résultat divise $E$ en paquets disjoints (une partition) :

$$\text{Card}(E) = \sum_{i=1}^{n} \text{Card}\left(f^{-1}(\{i\})\right)$$

*Signification :* Pour compter le nombre total d'élèves ($\text{Card}(E)$), on peut compter combien ont eu $1/20$, combien ont eu $2/20$, etc., et tout additionner.

#### B. Propriétés d'une application $f : A \to B$ et taille des ensembles

On compare la taille (le cardinal) des ensembles de départ $A$ et d'arrivée $B$ selon les propriétés de la fonction :

- **Injective :** Chaque élément de $B$ a **au plus un** antécédent dans $A$ (deux éléments distincts au départ ont des images différentes).
  $$\text{Card}(A) \leq \text{Card}(B)$$
- **Surjective :** Chaque élément de $B$ a **au moins un** antécédent dans $A$ (tout le monde dans $B$ est atteint par la fonction).
  $$\text{Card}(A) \geq \text{Card}(B)$$
- **Bijective :** Chaque élément de $B$ a **exactement un** antécédent dans $A$ (Injective ET Surjective).
  $$\text{Card}(A) = \text{Card}(B)$$

> **À quoi ça sert ?** Si on arrive à construire une bijection entre un ensemble compliqué $A$ et un ensemble simple $B$ dont on connaît la taille, alors $\text{Card}(A) = \text{Card}(B)$. C'est l'un des outils majeurs du dénombrement.

---

### 6. Cardinaux usuels à connaître

#### A. Produit cartésien
$$\text{Card}(A \times B) = \text{Card}(A) \times \text{Card}(B)$$

*Exemple :* On choisit une tenue composée d'un t-shirt et d'un pantalon.
- Ensemble des t-shirts : $A = \{\text{rouge}, \text{bleu}, \text{vert}\}$ ($\text{Card}(A) = 3$)
- Ensemble des pantalons : $B = \{\text{jean}, \text{short}\}$ ($\text{Card}(B) = 2$)

L'ensemble des tenues possibles est $A \times B$. On a donc :
$$\text{Card}(A \times B) = 3 \times 2 = 6 \text{ tenues différentes.}$$

##### Preuve :
Soit $f : A \times B \to A, (a, b) \mapsto a$.
$f^{-1}(\{a\}) = \{a\} \times B$, donc $\text{Card}(f^{-1}(\{a\})) = \text{Card}(B)$.
$$\text{Card}(A \times B) = \sum_{a \in A} \text{Card}(B) = \text{Card}(A) \times \text{Card}(B)$$

#### B. Ensemble des fonctions $\mathcal{F}(A, B)$
Soient $\text{Card}(A) = n$ et $\text{Card}(B) = p$.

$$\text{Card}\left(\mathcal{F}(A, B)\right) = \text{Card}(B)^{\text{Card}(A)} = p^n$$

*Exemple :* On répond à un QCM de $4$ questions ($A = \{Q_1, Q_2, Q_3, Q_4\}$), où chaque question propose $3$ réponses possibles ($B = \{a, b, c\}$). \
Remplir une grille de réponses revient à définir une fonction de $A$ dans $B$ (associer une réponse à chaque question) :
- $\text{Card}(A) = 4$
- $\text{Card}(B) = 3$

Le nombre total de grilles de réponses possibles est :
$$\text{Card}\left(\mathcal{F}(A, B)\right) = 3^4 = 81 \text{ grilles différentes.}$$

*Cas particuliers :*
- Si $B = \{1\} \implies 1^n = 1$
- Si $A = \{1\} \implies p^1 = p$

##### Preuve :
Soit $A = \{a_1, \dots, a_n\}$. L'application $F : f \mapsto (f(a_1), \dots, f(a_n))$ est une bijection de $\mathcal{F}(A, B)$ vers $B^n$.
Donc $\text{Card}(\mathcal{F}(A, B)) = \text{Card}(B^n) = p^n$.

#### C. Ensemble des parties $\mathcal{P}(E)$
L'ensemble des sous-ensembles de $E$ contient l'ensemble vide $\emptyset$ et $E$ lui-même.

$$\text{Card}\left(\mathcal{P}(E)\right) = 2^{\text{Card}(E)}$$

*Exemple :* $E = \{1, 2, 3\} \implies \mathcal{P}(E) = \{\emptyset, \{1\}, \{2\}, \{3\}, \{1, 2\}, \{1, 3\}, \{2, 3\}, \{1, 2, 3\}\}$ (8 éléments = $2^3$).

##### Preuve :
On associe à chaque partie $A \subset E$ sa fonction indicatrice $\mathbb{1}_A : x \mapsto 1$ si $x \in A$, $0$ sinon.
C'est une bijection entre $\mathcal{P}(E)$ et $\mathcal{F}(E, \{0, 1\})$, d'où le résultat $2^{\text{Card}(E)}$.

#### D. Bijections (Permutations) $\text{Bij}(A, A)$
Si $\text{Card}(A) = n$ :

$$\text{Card}\left(\text{Bij}(A, A)\right) = n! = n \times (n-1) \times \dots \times 1$$

##### Preuve :
On fixe le choix du premier élément $a_1$ parmi $n$ possibilités :

| $a_1$ | nombre de bijections restantes |
| :---: | :--- |
| $1$ | $(n-1)!$ |
| $2$ | $(n-1)!$ |
| $\vdots$ | $\vdots$ |
| $n$ | $(n-1)!$ |

$$\text{Card}\left(\text{Bij}(A, A)\right) = \sum_{i=1}^{n} (n-1)! = n \times (n-1)! = n!$$